# MASTER_IDEAS - Motor de Inteligencia Cross-Proyecto

> Leer este archivo al inicio de una sesion. No es la memoria completa: es el mapa de conexiones, riesgos y oportunidades entre proyectos.

## Protocolo

1. Leer este archivo para detectar conexiones cross-proyecto.
2. Abrir `inteligencia/_registry.md` para ubicar el proyecto activo.
3. Leer `inteligencia/<proyecto>/threads/_index.md`.
4. Seleccionar maximo 4 threads relevantes por tags.
5. Leer `memory/` solo cuando haga falta validar hechos, decisiones, tensiones o criterios estables.

## Regla De Separacion

- `MASTER_IDEAS.md`: solo senales cross-proyecto.
- `PROJECT.md`: identidad, proposito y variables principales de un proyecto.
- `threads/*.md`: memoria de sesiones o eventos independientes.
- `memory/*.md`: facts, decisions, tensions, variables y criterios estables.
- `analysis/*.md`: fuentes textuales, extractos y entregables de apoyo.

## Proyectos Activos

| Proyecto | Estado | Ruta | Ultima actualizacion | Lectura inicial |
|---|---|---|---|---|
| AI Construction Summit 2026 | activo | `inteligencia/ai-construction-summit-2026/` | 2026-05-11 | `threads/_index.md` + `memory/tensions.md` |
| AECODE | activo - Fase 3 | `inteligencia/aecode/` | 2026-05-06 | `threads/_index.md` |
| GEN+ | activo | `inteligencia/gen-plus/` | 2026-05-21 | `threads/_index.md` |
| I Lanza Training | activo | `inteligencia/i-lanza-training/` | 2026-05-06 | `threads/_index.md` |
| INGECONCRETO | activo | `inteligencia/ingeconcreto/` | 2026-05-06 | `threads/_index.md` |
| Tesis Juan Carlos Arteaga | activo | `inteligencia/tesis-juan-carlos-arteaga/` | 2026-05-06 | `threads/_index.md` |

## AI Construction Summit 2026

**Estado:** activo  
**Ruta:** `inteligencia/ai-construction-summit-2026/`

### Variables Criticas

- El evento es el flywheel de AECODE: evento -> comunidad -> educacion -> autoridad -> sponsors -> expansion LATAM.
- Sede CIP confirmada; ya no debe tratarse como bloqueo.
- Sponsors siguen siendo variable critica: meta USD 15K-20K, avance real no cargado.
- Precios de sponsors 2026 tienen contradiccion documental: memoria previa vs brochure nuevo. Validar antes de cotizar.
- Web/landing/CRM/pasarela siguen como dependencia de conversion y tracking.
- Agenda 2025 ya esta recuperada como baseline historico; agenda 2026 real aun requiere cierre con speakers confirmados.
- El lenguaje que vende a audiencia AEC no es "IA/GPT/agentes"; es productividad, costos, obra, control, riesgo, clientes y ventaja competitiva.

### Activos

- Estructura Notion operativa con 15 areas, portal y sync local.
- Brochure 2025 recuperado con agenda historica real.
- Brochure sponsors 2026 recuperado como fuente comercial, con pendiente de reconciliacion de precios.
- Ejes tematicos 2026 documentados como entregable academico gestionable.
- La capa estrategica de ejes no siempre coincide con el nombre publico de campaña; para piezas visuales revisar `memory/ejes-publicos-2026.md`.
- Prueba social 2025: +40 speakers/panelistas, +350 asistentes y +20 colaboradores/sponsors.

### Threads Clave

- `2026-05-11-ingesta-brochures-2025-2026`: fuentes locales, agenda 2025 y brochure sponsors 2026.
- `2026-04-29-notion-academico-ejes-tematicos`: ruta canon de Notion para contenidos academicos.
- `2026-04-27-mensajeria-comercial-y-automatizacion`: criterio comercial para decisores no tecnicos y aprendizaje n8n.
- `2026-04-24-arranque-post-migracion`: cruces inter-area y riesgos A1/A2/A5/A6/A7/A10.

## AECODE

**Estado:** activo - Fase 3  
**Ruta:** `inteligencia/aecode/`

### Variables Criticas

- Unidad central de producto: Skill dentro de arquitectura Ruta -> Cluster -> Skill -> Capsula.
- Audiencia compartida con el Summit: profesionales AEC que responden a lenguaje de obra, no a terminologia abstracta de IA.
- El hook no nombra la solucion; activa una tension reconocible del comportamiento actual del espectador.

### Activos

- Arquitectura pedagogica completa de skills.
- Criterios de hooks y guiones para audiencia BIM/AEC.
- Capacidad de convertir conocimiento tecnico en contenido que atraviesa resistencia perceptual.

### Necesidades

- Canal de distribucion con audiencia AEC real.
- Validacion de arquitectura de Skills con usuarios del sector.

## I Lanza Training

**Estado:** activo  
**Ruta:** `inteligencia/i-lanza-training/`

### Activos

- Slides full-image con branding GEN+.
- Kit de ejercicios: Gmail, Sheets + Gmail, NotebookLM + Gemini.
- Criterio validado: la plantilla es marco de marca, no limite creativo.

### Necesidades

- Confirmar estado de entrega de materiales.
- Confirmar si la sesion 02 ya se ejecuto o sigue pendiente.

## GEN+

**Estado:** activo  
**Ruta:** `inteligencia/gen-plus/`

### Activos

- Hilo maestro de agentes IA para AEC y presentacion comercial de 35 slides.
- Genbot inmobiliario documentado: bot WhatsApp con Vision IA, flujo lote/premium, Sheets/Drive/Cloudinary y One Page HTML.
- Agente /ref ADS para capturar referencias de anuncios desde WhatsApp hacia Sheets/Drive.

### Necesidades

- Verificar estado real del Genbot inmobiliario tras migracion Hostinger/EasyPanel.
- Cerrar bloqueo de infraestructura WhatsApp/Evolution API si sigue vigente.
- Validar en produccion el flag de imagen en lote y el flujo premium con API key activa.

## INGECONCRETO

**Estado:** activo  
**Ruta:** `inteligencia/ingeconcreto/`

### Variables Criticas

- Cliente corporativo GEN+ de ingenieria estructural/concreto.
- Propuesta activa GEN+_2603_07: training BIM de automatizacion por USD 2,400, 48h, 3 modulos.
- Certificacion AECODE aparece como valor agregado y posible primer caso B2B corporativo.

### Necesidades

- Confirmar si la propuesta fue aceptada, sigue en negociacion o quedo pausada.
- Confirmar numero de participantes y fecha de inicio.
- Documentar respuesta del cliente ante el certificado AECODE.

## Tesis Juan Carlos Arteaga

**Estado:** activo  
**Ruta:** `inteligencia/tesis-juan-carlos-arteaga/`

### Variables Criticas

- Tema: reemplazo de H2SO4 por CO2 capturado mediante aminas para control de pH en Central Termica de Ventanilla.
- Requiere APA7 estricto.
- El estandar de entrega es academico formal.

## Conexiones Detectadas

**[C1] Summit 2026 -> AECODE**

El Summit concentra una audiencia AEC real y temporal. Cualquier decision que debilite conversion, experiencia, agenda o captura de datos afecta directamente el pipeline de AECODE Fase 3.

**[C2] AECODE -> Summit 2026**

Los criterios de lenguaje de AECODE deben validar nombres publicos de ejes, tracks y mensajes del Summit. Si el texto suena a IA generica en vez de productividad/control/obra, probablemente no vende.

**[C3] Summit 2025 -> Summit 2026**

La agenda 2025 no debe copiarse: debe usarse como baseline operativo. La mejora 2026 debe venir de diseno de escenas, contrastes, demos, tension narrativa, sponsors integrados y mayor claridad para decisores.

**[C4] I Lanza -> Trainings AECODE**

El kit de ejercicios y formato full-image de I Lanza es reutilizable para trainings tecnicos, pero debe adaptarse a la audiencia y no copiarse como plantilla fija.

**[C5] INGECONCRETO -> AECODE**

INGECONCRETO puede validar AECODE como certificador B2B corporativo. Si el cliente percibe el certificado como diferencial, se vuelve proof-of-concept para vender certificacion a empresas tecnicas.

**[C6] GEN+ Genbot inmobiliario -> Producto comercial**

El Genbot inmobiliario cruza automatizacion WhatsApp, Vision IA y generacion comercial de fichas/One Page. Puede convertirse en caso demostrable para inmobiliarias si se cierra infraestructura y se limpia el flujo premium.
