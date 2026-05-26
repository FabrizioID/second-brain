# Hilo: Agente /ref ADS — WhatsApp → Sheets + Drive

**Fecha:** 2026-05-17  
**Tags:** #n8n #aecodito #whatsapp #marketing #referencias-ads #evolution-api #google-drive  
**Estado:** ✅ Funcional (pendiente refinamiento NLP y pruebas de imagen en prod)

---

## Objetivo

Capturar referencias de anuncios ADS desde el grupo de WhatsApp de marketing, guardarlas en Google Sheets y subir las imágenes/videos a Google Drive. El equipo envía links, imágenes y texto natural desde WhatsApp y el bot estructura todo automáticamente.

---

## Arquitectura implementada

### Flujo en Aecodito (workflow master Ma67AAArvHx4wX15)

```
Webhook → Parsear → Dedup → Detectar Comando
  ↓ (si /ref o sesión activa)
Tipo de Comando → Es Ref ADS? → Gestionar Sesion Ref
  ↓ (si campos completos)
Guardar Ref? → Ejecutar Guardado Refs (sub-workflow)
  ↓
Enviar Respuesta Comando
```

### Nodos nuevos agregados a Aecodito
- **Detectar Comando**: añadido check de sesión activa + `'ref'` en comandosValidos
- **Tipo de Comando**: añadido `necesitaRefAds` + paso de `esImagen`, `messageKey`, `messageContent`
- **Es Ref ADS?** (IF): detecta `necesitaRefAds`
- **Gestionar Sesion Ref** (Code): lógica completa de sesión scratchpad
- **Guardar Ref?** (IF): detecta `accion === 'guardar'`
- **Ejecutar Guardado Refs** (ExecuteWorkflow): llama sub-workflow `wfHPoqIpdBKeuza6`

### Sub-workflow: Refs ADS - Guardar Referencia (wfHPoqIpdBKeuza6)
```
Trigger → Preparar Datos → Hay Media?
  → Sí: Descargar Media → Preparar Binary → Subir a Drive → Agregar Link Drive → Limpiar para Sheets
  → No: Limpiar para Sheets
→ Guardar en Sheets → Respuesta Final
```

---

## Comportamiento del agente

### Modo scratchpad (sesión abierta)
1. Usuario envía `/ref` → abre sesión
2. Envía mensajes sueltos (imagen, link, texto, formato, curso) → bot acumula
3. Cuando tiene **link/imagen + red social + formato + referencia** → auto-guarda y cierra
4. `/fin` → guarda lo que haya y cierra la sesión

### Extracción de campos
- **URL**: regex directo
- **Red social**: keywords + dominio del link
- **Formato**: keywords (Reel, Carrusel, Flyer, etc.) + Gemini para texto libre
- **Referencia (curso/producto)**: Gemini para razonamiento NLP
- **Imagen/video**: detecta `esImagen`/`esDocumento` → descarga via Evolution API → sube a Drive

### Capa IA (Gemini)
Después de la detección por regex, si quedan campos vacíos y hay texto, se llama a `gemini-2.0-flash` para extraer campos desde lenguaje natural. Fallback silencioso al regex si Gemini falla.

---

## Recursos

| Recurso | ID/URL |
|---|---|
| Sheet Referencias Ads | `1V97yMW8h5t22hJO7Hl_VZpdtmofBpxkr716QOGKrNX4` |
| Drive carpeta principal | `1PiTD2q5Kt2xbPiRz3zaJIBtJSL7MfsOG` |
| Drive subcarpeta Fotos y Videos | `1jQp6bnR6UvpXU7pm6DGiDqifyIsqxrRJ` |
| Aecodito workflow | `Ma67AAArvHx4wX15` |
| Sub-workflow guardado | `wfHPoqIpdBKeuza6` |

---

## Issues conocidos / Pendientes

- [ ] Probar flujo completo con imagen real en prod (subworkflow Drive OK en tests individuales)
- [ ] El campo Referencia a veces captura texto residual del campo Formato — la capa Gemini debe resolverlo
- [ ] Implementar subida de videos (actualmente solo imágenes detectadas con `esImagen`)
- [ ] Timeout de sesión: 10 min → considerar si es suficiente para el flujo del equipo

---

## Bugs corregidos en la sesión

1. `/ref` nuevo se trataba como `ref-session` si había sesión activa → fix: bypass del check de sesión para comandos `/ref`
2. `textoLimpio` usado antes de ser definido → fix: reordenar bloque de extracción
3. Imágenes sin caption ignoradas (`ignorar: true`) → fix: `esMedia` bypasea el check de `ignorar`
4. Formato = "/ref" por el fallback de texto → fix: filtros de exclusión + Gemini
5. autoMapInputData creaba columnas duplicadas → fix: Code Node "Limpiar para Sheets"
