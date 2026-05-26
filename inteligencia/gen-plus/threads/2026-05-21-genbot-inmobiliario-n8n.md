---
slug: 2026-05-21-genbot-inmobiliario-n8n
proyecto: genplus
fecha: 2026-05-21
tipo: sintesis
---

## Objetivo del hilo
Construir y depurar el bot WhatsApp inmobiliario GEN+ Genbot completo: registro de propiedades con Vision IA, flujo lote/masivo, One Page HTML, premium con gpt-image-2, y preparar migración al VPS Hostinger.

## Resumen ejecutivo
- Bot funcional en n8n Cloud (KvwaMUInjffC74Wg): flujos individual, lote y premium operativos
- Vision IA (Gemini 2.5 Flash) extrae datos de flyers y los guarda en Sheets/Drive automáticamente
- VPS Hostinger con n8n listo pero Evolution API pendiente de credenciales EasyPanel para nuevo número WhatsApp

## Estado del proyecto en este momento
- **Workflow**: `KvwaMUInjffC74Wg` en `aecode.app.n8n.cloud` — ACTIVO ✅
- **WhatsApp actual**: Evolution API `http://187.77.250.111:8080` v2.3.7, instancia `GenPlus` (número 51924102571)
- **Grupos target**: `120363425749021436@g.us` y `120363428571661752@g.us`
- **VPS actual**: `31.220.54.82` Lithuania — EasyPanel + n8n corriendo ✅ PERO Evolution API bloqueada por WhatsApp (datacenter europeo)
- **PENDIENTE**: Reinstalar VPS en Boston USA para desbloquear WhatsApp — borrará todo, se reconfigura desde cero
- **Stack VPS a recrear**: EasyPanel + n8n + postgres + Evolution API v2.3.7 en Boston

## Avances detectados
- Flujo `!genbot [foto/texto]` funciona: Vision extrae datos → Drive (4 carpetas) → Sheets → One Page HTML (HCTI) → Cloudinary (para premium)
- Flujo lote `!genbot lote / mensajes / !genbot fin`: imágenes se procesan individualmente con Vision en silencio, textos en batch
- Flujo premium `!genbot premium`: gpt-image-2 con foto real (Cloudinary edits) o sin foto (generations fallback)
- Arquitectura clave: `Gemini Vision → Merge Vision + Texto → Append Inventario Sheets` (Vision ANTES del Append para que los datos lleguen)
- Problema de race condition en n8n static data al enviar múltiples imágenes rápido — resuelto con cierre gracioso en `!genbot fin`

## Problemas o bloqueos
- **n8n Cloud Code nodes no permiten HTTP** (`require('https')` bloqueado, `fetch` silencioso) — impide llamar Vision desde Code nodes en lote
- **Google Sheets node 3er write falla silenciosamente** (0 rows returned) — bug de n8n Sheets v4.5 con múltiples updates al mismo row en misma ejecución
- **Race condition static data**: múltiples imágenes en lote activo llegan antes de que la primera guarde en static data
- **EasyPanel Swarm desync**: EasyPanel deploya con 0 réplicas internamente aunque Swarm corre 1 — hay que forzar con `docker service update --replicas 1` después de cada deploy
- **Redis disconnected mata proceso**: Evolution API v2.2.3 envía SIGTERM si Redis está habilitado pero no conecta — solución: `REDIS_ENABLED=false`
- **Prisma .env interno**: Evolution API tiene .env hardcodeado con `postgres:5432` y usuario `user:pass` — no overrideable con env vars simples, requiere que el servicio postgres se llame exactamente `postgres` y crear el usuario `user` manualmente

## Decisiones tomadas
- Flujo Vision: trigger desde `Gemini Vision` (Branch 2) → `Merge Vision + Texto` en vez de desde `Consolidar Datos Post-Upload` (Branch 1) — porque Branch 1 corre antes que Vision
- Lote con imágenes: imágenes NO se acumulan en cola, se procesan individualmente en silencio como `es_nueva_propiedad=true`
- Sheets updates: solo UN update por ejecución para evitar el bug del 3er write (Cloudinary ID update incluye todo)
- Prompt One Page: guarda `prompt_gpt + '|||' + cloudinary_id` — extractor premium lee solo la parte después de `|||`

## Soluciones o propuestas
- Vision en lote: imposible via Code node (HTTP bloqueado), solucionado haciendo que imágenes en lote = flujo individual completo
- Race condition: cuando `!genbot fin` encuentra cola vacía, cierra sesión graciosamente con mensaje positivo
- Google Sheets 3er write: consolidar en un solo update node que corre como 2do write (después de Append)
- Para VPS: usar EasyPanel GUI para desplegar Evolution API desde su marketplace

## Patrones detectados
- **Dependencia excesiva en n8n Cloud**: todas las restricciones (HTTP bloqueado, static data concurrency, Sheets bug) son limitaciones de la plataforma
- **Avance sin cierre**: múltiples iteraciones de fixes para Vision en lote — se llegó a solución pero sin verificación final del flag `es_imagen_en_lote`
- **Arquitectura frágil con branches paralelas**: n8n v1 procesa branches secuencialmente, no en paralelo — causa todos los timing issues de Vision

## Oportunidades detectadas
- VPS con n8n + Evolution API propio = independencia de n8n Cloud y más control sobre restricciones
- Lote masivo funcional = diferenciador para asesores que hacen reenvíos masivos de propiedades
- Vision extrae datos de cualquier flyer inmobiliario = captura incluso propiedades de competencia

## Aprendizajes reutilizables
- En n8n v1, branches de fan-out se procesan SECUENCIALMENTE (no en paralelo): la branch del Drive/Append corre antes que Vision
- Google Sheets node v4.5: solo 2 updates al mismo row en misma ejecución — el 3er falla silenciosamente (0 rows)
- n8n Cloud Code nodes: `require('https')` bloqueado, `fetch` nativo silencioso, `$helpers.httpRequest` disponible pero no siempre funciona
- Para sincronizar branches paralelas en n8n: mover el nodo downstream a la branch que termina DESPUÉS
- Static data en n8n es persistido al FINAL de la ejecución, no por nodo — concurrent executions tienen race conditions
- **EasyPanel + Docker Swarm**: EasyPanel usa Swarm pero su estado interno no sincroniza automáticamente — después de deploy siempre verificar con `docker service ls` y forzar réplicas si es 0/N
- **Evolution API v2.2.3 (atendai)**: requiere postgres con usuario `user` y password `pass` hardcodeados en Prisma — crear manualmente con `CREATE USER "user" WITH PASSWORD 'pass'` y `GRANT ALL ON SCHEMA public TO "user"`
- **EasyPanel reset de credenciales**: usar `docker exec <container_id> node -e "const lmdb = require('lmdb'); ..."` para modificar LMDB directamente
- **Redis en Evolution API**: `REDIS_ENABLED=false` para evitar SIGTERM; si se habilita, el hostname en Swarm es el nombre completo del servicio (ej: `1erautomatizacion_redis`)

## Preguntas abiertas
- ¿`es_imagen_en_lote` flag funciona correctamente en `Construir Respuesta Rápida`? (fix aplicado pero no verificado en producción)
- ¿HCTI free tier (50/mes) es suficiente o necesita plan pagado?
- ¿Cuándo recargar la API key de OpenAI para que gpt-image-2 edits funcione?
- ¿Cómo hacer que EasyPanel no resetee a 0 réplicas en cada deploy? (problema estructural pendiente)

## Próximos pasos
1. **INVESTIGAR**: Solución para conectar WhatsApp desde VPS Lituania — proxy residencial, WireGuard VPN hacia Brasil, o cambio de datacenter
2. **PENDIENTE CLIENTE**: Configurar credenciales en n8n VPS (Gemini, Google Sheets OAuth, Google Drive OAuth) + JID grupo + ID Sheets + activar workflow
3. Exportar workflow completo del n8n cloud e importar al VPS (bloqueado por 2FA — pendiente recuperar acceso)
4. Verificar flag `es_imagen_en_lote` en producción
5. Columna "Banos" (AL) en Sheets — eliminar manualmente
6. n8n VPS password temporal: `[REDACTED]` - credencial omitida en Second Brain canonico

## Estado infraestructura (2026-05-22)
- **Evolution API**: `http://187.77.250.111:8080` v2.3.7 — instancia `ClienteBot` (número 51929064479) ACTIVA
- **n8n VPS**: `https://1erautomatizacion-n8n.n7ixb7.easypanel.host` — workflow `clientefull01` importado, pendiente credenciales
- **Webhook**: ClienteBot → `https://1erautomatizacion-n8n.n7ixb7.easypanel.host/webhook/genplus-inmobi`
- **Bloqueo WhatsApp en VPS Lituania**: confirmado — datacenter Hostinger Europa bloqueado para nuevas conexiones WhatsApp a nivel de protocolo (keepalive falla)

## Tags temáticos
- automatizacion | whatsapp | n8n | inmobiliaria | vision_ia | sheets | drive | cloudinary | evolution_api | gemini | hcti | gpt_image

## Tags de patrón
- dependencia_excesiva | avance_sin_cierre

## Tags de señal
- aprendizaje | bloqueo | decision | riesgo

## Relaciones internas del hilo
- Bug Sheets 3er write → decisión de consolidar en un solo update node
- n8n branches secuenciales → decisión de mover HTML One Page a Branch 2 (después de Vision)
- HTTP bloqueado en Code nodes → decisión de imágenes lote = flujo individual
- Race condition static data → solución cierre gracioso en !genbot fin

## Señales exportables a otros proyectos
- **Para cualquier workflow n8n**: branches de fan-out son secuenciales, no paralelas — diseñar en consecuencia
- **Para automatizaciones con Sheets**: máximo 2 updates al mismo row en misma ejecución
- **Para bots WhatsApp con Vision**: Evolution API es el mejor middleware para manejar media encryption; Gemini 2.5 Flash es rápido y preciso para flyers inmobiliarios
