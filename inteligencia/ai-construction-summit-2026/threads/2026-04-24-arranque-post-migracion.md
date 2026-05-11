---
slug: 2026-04-24-arranque-post-migracion
proyecto: AI Construction Summit 2026
fecha: 2026-04-24
tipo: estrategia
---

## Objetivo del hilo

Arrancar la nueva sesion del AI Construction Summit 2026 usando el esquema actualizado de `strategic-project` y `project-thread-assistant`.

## Resumen ejecutivo

- El proyecto fue migrado a `inteligencia/ai-construction-summit-2026/`.
- El hilo historico principal quedo disponible para context pull.
- Este archivo queda como hilo activo para documentar decisiones, bloqueos, oportunidades y proximos pasos desde el arranque post-migracion.

## Estado del proyecto en este momento

- Memoria estrategica inicial creada: `PROJECT.md`, `memory/`, `signals/` y `threads/`.
- Variables, tensiones, decisiones y hechos base cargados desde el hilo anterior.
- Falta actualizar con datos reales al dia: sede, sponsors, tickets, landing, agenda y proveedores.

## Avances detectados

- Proyecto inicializado con registry global.
- Thread historico migrado al schema nuevo.
- Credenciales redactadas del hilo viejo.
- Scheduler `\AECODE Summit Notion Sync` verificado en estado `Listo`.
- Scripts `scripts/notion_summit_sync.py` y `scripts/run_notion_summit_sync.bat` verificados en disco.
- Se ingesto el brief DOCX `BRIEF 4 - ACADEMICO, CONTENIDO Y PROGRAMA` y se extrajo a `brief-academico-extract.md`.
- Se creo el HTML operativo `inteligencia/ai-construction-summit-2026/analysis/plan-academico-area-4.html` con rutas, cronograma, ejes, speaker roster, certificados, dependencias y contingencias.
- Se reforzo el HTML con 21 acciones concretas por ruta, una capa de naming academico y ejes mas actuales/vendibles.
- Se actualizo el plan con benchmark externo AEC/ConTech/AI: BuiltWorlds Construction Tech, BuiltWorlds AI/ML, GWF AEC Summit, EC3 tracks y AIA LA Technology Conference.
- Se cambio el enfoque de "ejes tematicos" a "mapa de conversaciones" y la agenda se reestructuro como secuencia de escenas academicas.
- Se reemplazo el concepto ambiguo de "dossier academico" por "carpeta maestra academica", entendida como fuente unica para Marketing, Web, App, AV, Edecanes y Producto.
- Se retiro del HTML la seccion de preguntas Magnus; esas preguntas quedan como proceso de trabajo por chat, no como contenido del entregable.
- Se reemplazaron nombres personales en owners por areas/roles para evitar reacciones internas y mantener el plan institucional.
- Se retiro la seccion de fuentes/referencias del HTML para dejar el entregable limpio.
- Se agregaron desplegables operativos por cada una de las 7 rutas, con 42 micro-pasos accionables.
- Se reemplazo la seccion de acciones tipo tabla por un checklist vertical: 7 rutas desplegables, 21 grupos de tareas y 63 checkboxes operativos.
- Se genero version Word editable del plan academico en `analysis/plan-academico-area-4.docx`, convirtiendo los desplegables en secciones y preservando 63 tareas tipo checklist.
- Se ingesto el brief PDF `Area7 MKT Difusion Summit2026.pdf` y se extrajo a `analysis/area7-mkt-difusion-summit2026-extract.md`.
- Se creo el plan operativo de Marketing y Difusion en `analysis/marketing/plan-marketing-area-7.md`, con meta recomendada de 3,000 registros presenciales, funnel, dependencias, restricciones, plan diario de 3 semanas, Gantt, canales y checklists.
- Se genero version Word editable del plan de Marketing en `analysis/marketing/plan-marketing-area-7.docx`.
- Se genero visualizador HTML del plan de Marketing en `analysis/marketing/plan-marketing-area-7.html`, con 7 rutas desplegables y 49 tareas tipo checklist.
- Se actualizo el plan academico HTML con dos secciones nuevas: `Plan academico al milimetro` para las primeras 3 semanas y `Durante el evento: control academico de la experiencia`, con objetivos propios del area academica.
- Se regenero el Word academico `analysis/plan-academico-area-4.docx` para reflejar las nuevas secciones operativas.
- Se convirtio el aprendizaje de ejecucion en mejora de skill: `magnus-thinker` ahora referencia `references/execution-plans.md` para planes de ejecucion, checklists, Gantt, durante/post y granularidad por area.
- Se ingesto el brief DOCX `BRIEF 5 - DESARROLLO WEB AECODE` y se extrajo a `analysis/brief-5-desarrollo-web-aecode-extract.md`.
- Se creo analisis de cruces y vacios entre Web/App, Marketing y Academico en `analysis/cruces-vacios-web-marketing-academico.md`.

## Problemas o bloqueos

- Pendiente confirmar estado real actual de las variables criticas.
- Riesgo de interfaz Academico-Marketing: Marketing necesita agenda, temas y speakers para vender antes de que Academico pueda confirmarlos con seguridad; se debe separar teaser/temas publicables de anuncios con nombres.
- Vacio operativo detectado: experiencia virtual, CRM/landing/data, owners de show rate y confirmacion de asistencia no tienen un dueno unico claro entre Marketing, Tecnologia, Operaciones y Direccion.
- Vacio operativo detectado: transferencia de momentos academicos a Marketing durante el evento requiere un rol explicito de enlace/bitacora, no solo buena voluntad entre areas.
- Riesgo de interfaz: certificados, permisos, PPTs y uso post-evento cruzan Academico, Marketing, Tecnologia y Legal; falta matriz RACI o fuente unica para evitar reprocesos.
- Riesgo de alcance Web/App: el brief plantea app nativa con QR offline, wallet, streaming, Aecodito, leaderboard, ruleta, bingo, photobooth, panel admin, certificados y Premium; puede exceder el tiempo real si no se define MVP.
- Vacio operativo detectado: no hay owner unico del flujo registro -> confirmacion -> QR -> check-in -> asistencia real -> base post-evento.
- Choque detectado: Web/App dimensiona 1K inscritos objetivo, mientras Marketing recomienda 3,000 registros presenciales + virtual para asegurar asistencia real.

## Decisiones tomadas

- Usar `inteligencia/ai-construction-summit-2026/threads/_index.md` como entrada para context pull.
- Mantener este archivo como hilo activo de arranque.
- Para el plan academico v1, tratar el area como guardian de reputacion tecnica: no disena piezas, pero define informacion, estructura, criterios, agenda, pauta, speaker quality y certificados.

## Soluciones o propuestas

- Empezar la sesion preguntando o verificando el estado real actual de las variables criticas.
- Priorizar una vista de mando: sede, sponsors, landing/CRM, agenda/speakers, B2C Premium y automatizacion.

## Patrones detectados

- `avance_sin_cierre`: la estructura existe y ahora toca cerrar datos reales y decisiones operativas.

## Oportunidades detectadas

- Usar la nueva memoria para razonar con continuidad y no reconstruir contexto en cada sesion.

## Aprendizajes reutilizables

- Migrar threads viejos a `inteligencia/<proyecto>/threads/` permite que Magnus haga context pull por tags y no por memoria suelta.
- En planes operativos del Summit, las rutas deben bajar a acciones verificables por fecha, owner y output; si no, quedan como arquitectura conceptual.
- En el area academica, los titulos de sesiones son parte del producto: deben vender aprendizaje, tension, actualidad y utilidad, no solo describir temas.
- El diseno academico debe operar con variables combinatorias y asimetricas: no solo elegir speaker/tema/formato, sino probar contrastes de edad, genero, seniority, industria, academia, tecnologia, robots/demos, local-internacional y energia narrativa.
- El lenguaje academico debe usar terminos reconocibles del mercado AEC global cuando vendan mejor: Digital Twins & Asset Intelligence, AI Readiness, Reality Capture & Jobsite Intelligence, Drawing Intelligence, Risk Analytics, Connected Ecosystems, Human-in-the-Loop.
- Para Marketing, la meta de registros debe considerar show rate, flujo feria y virtual; si se buscan 900-1,000 personas reales, el plan debe apuntar a unos 3,000 registros presenciales y separar la meta virtual.
- Marketing no debe operar como area de piezas, sino como sistema de demanda: landing/form, tracking, base caliente, ads, comunidad, aliados, WhatsApp, contenido y post-evento conectados.
- En cualquier area del Summit, el plan debe tener un tramo inmediato "al milimetro" y un protocolo "durante" adaptado a la funcion del area; no se debe copiar el mismo durante de Marketing a Academico, Logistica o Sponsors.

## Preguntas abiertas

- Cual es el estado actual de sede CIP?
- Cuantos sponsors estan cerrados o en negociacion?
- La landing/pasarela/CRM ya esta publicada?
- Quien toma ownership de B2C/Premium?
- En la agenda academica, el balance deseado es mas tecnico-aplicado o mas ejecutivo-visionario?
- Cuantos slots maximos de sponsors se aceptaran sin deteriorar la reputacion academica?
- El certificado Premium tendra horas academicas o sera constancia simple?

## Ingesta de briefs — sesion 2026-04-24 (segunda ronda)

Se ingirieron 4 briefs adicionales y se cruzaron con los 3 anteriores:

| Area | Brief ingestado |
|---|---|
| Area 1 - Modelo de Negocio y Presupuesto | Si |
| Area 2 - Sponsors, Comunicacion, Alianzas y Comercial | Si |
| Area 6 - Tecnologia, Automatizacion y Data | Si |
| Area 10 - Logistica y Produccion Audiovisual | Si |

**Areas cubiertas acumuladas: 7 de ~15** (1, 2, 4, 5, 6, 7, 10)

### Choques criticos detectados en el cruce

- **[C1]** Datos de leads: A2 promete a sponsors, A7 necesita para campanas, A6 centraliza en Postgres — sin politica de gobernanza del dato
- **[C2]** Stack tecnologico paralelo: A2 propone Apollo.io + Make.com + Typeform mientras A6 tiene n8n + Coord Studio — riesgo de sistemas desconectados
- **[C3]** Presupuesto sin aprobar (A1) mientras A2 y A6 tienen hitos esta semana (30 abr)
- **[C4]** A5 (Web) es cuello de botella el 13 mayo: desbloquea A6 + A7 + A2 simultaneamente
- **[C5]** Owner de sponsor el dia del evento: A2 asigna account owner, A10 asigna a Yulie — dos owners para el mismo sponsor
- **[C6]** Meta de registros sin armonizar: A2 dice 3,600 base, A5 dice 1K, A7 dice 3K

### Vacios operativos nuevos

- **[V1]** A1 (Presupuesto) tiene riesgos, dependencias y plan de accion en blanco — area mas incompleta
- **[V2]** Fabrizio aparece en 3 areas sin carga formal: A10 (timing escenario), A6 (go/no-go + capacitacion), sistema de inteligencia
- **[V3]** Alejandro es decisor en A1, A2, A6, A10 sin SLA de respuesta definido — cuello de botella humano
- **[V4]** Capacitacion IA de A6 empieza el 2 mayo; el modulo del Coord Studio es la sesion 3 (16 mayo), despues del deadline de adopcion del 13 mayo
- **[V5]** Flujo sponsor confirmado → logo → landing → pieza → publicacion no tiene owner end-to-end ni trigger automatico

## Proximos pasos

- Decidir que area ingestar a continuacion o trabajar un choque critico especifico.
- Prioridad recomendada: cerrar C3 (presupuesto) y C4 (fecha 13 mayo) antes de cualquier otra cosa.
- Si el usuario quiere, generar plan operativo HTML para Area 2 (Sponsors) o Area 6 (Tecnologia).

## Tags tematicos

- arranque
- memoria
- summit
- estrategia
- operaciones
- sponsors
- tecnologia
- logistica
- presupuesto

## Tags de patron

- avance_sin_cierre
- dependencia_excesiva
- falta_de_dueno

## Tags de senal

- aprendizaje
- decision
- riesgo
- bloqueo

## Relaciones internas del hilo

- Migracion de memoria -> habilita context pull -> reduce perdida de continuidad.

## Senales exportables a otros proyectos

- La migracion post-skill-update sirve como patron para convertir hilos `assistant/memory/chats/` en proyectos persistentes bajo `inteligencia/`.
