# Cruces y vacios - Web/App vs Marketing vs Academico

Fecha: 2026-04-24  
Base: Brief 5 Desarrollo Web AECODE + planes Area 4 Academico y Area 7 Marketing

## Hallazgo central

Web/App no es solo un soporte tecnico. En el brief aparece como el sistema nervioso del Summit: registro, QR, check-in, agenda, speakers, sponsors, streaming, Aecodito, juegos, networking, certificados, Premium y post-evento. Eso crea solapes fuertes con Marketing, Academico, Sponsors, Logistica, Legal y Direccion.

El mayor riesgo no es que falte trabajo. Es que muchas piezas dependan de Web/App, pero nadie sea owner del flujo completo.

## Choques principales

| Cruce | Que choca | Riesgo | Decision necesaria |
|---|---|---|---|
| Web/App vs Marketing | Marketing quiere lanzar campanas ya; Web necesita landing/formulario, eventos, UTMs, pixel y QA. | Ads corriendo hacia una landing incompleta o sin medicion. | Definir MVP de landing temporal antes de campana fuerte. |
| Web/App vs Academico | App necesita agenda, tracks, speakers, horarios, salas, bios y fotos; Academico aun esta validando. | Cargar datos tentativos y luego rehacer app/web. | Separar agenda publicable v1 de agenda operativa interna. |
| Web/App vs Logistica | Check-in QR offline y acceso dependen de flujo fisico de entrada. | App funciona, pero puerta colapsa por mala operacion. | Owner unico de check-in: Tecnologia + Logistica + Operaciones. |
| Web/App vs Marketing | Marketing quiere registro presencial, virtual, interesado y leads por curso; Web habla de registro/compra/tier. | Campos duplicados, bases partidas, leads no segmentables. | Diccionario unico de datos y formularios. |
| Web/App vs Sponsors | App incluye mapa, QR por stand, puntos, sorteos, perfiles de sponsor. Sponsors debe entregar logos, niveles, premios y dinamicas. | Leaderboard/pasaporte no se puede configurar a tiempo. | Fecha limite para sponsors y mecanicas. |
| Web/App vs Academico/Marketing | Aecodito debe responder agenda, speakers, salas, premium y cambios en vivo. | Chatbot da respuestas viejas o inventa si no hay fuente unica. | Fuente unica de verdad + proceso de actualizacion. |
| Web/App vs Legal | Registro, datos, imagen, networking, QR, contactos, premium y certificados implican permisos. | Riesgo de privacidad y uso de datos. | Legal debe validar consentimiento y politicas antes de lanzamiento. |
| Web/App vs Produccion | Streaming, Q&A, encuesta en vivo y resultados en pantalla LED cruzan app, AV y escenario. | Funcionalidad prometida que no se puede operar en vivo. | Definir si Q&A/quiz son app, Zoom, YouTube, Kahoot o manual. |

## Actividades solapadas

| Actividad | Areas que la mencionan | Problema | Owner sugerido |
|---|---|---|---|
| Registro y captura de datos | Marketing, Web/App, Tecnologia, Direccion | Todos lo necesitan; nadie gobierna todo el embudo. | Owner de Revenue/Data o Operaciones Digitales |
| Confirmacion por email/WhatsApp | Marketing, Web/App | Marketing piensa nurture; Web piensa transaccional. | Marketing define copy; Web automatiza envio; Data mide |
| Agenda en web/app | Academico, Web/App, Marketing | Academico define, Web carga, Marketing comunica. | Academico es source; Web implementa; Marketing adapta |
| Speaker profiles | Academico, Marketing, Web/App | Bio/foto/tema/redes se piden en varios formatos. | Academico recolecta; Marketing normaliza copy; Web carga |
| QR/check-in | Web/App, Logistica, Operaciones, Marketing | Tecnologia puede construirlo, pero no operar puerta sola. | Logistica/Operaciones con soporte Web/App |
| Pasaporte/leaderboard/juegos | Marketing, Web/App, Sponsors, Logistica | Marketing lo plantea como activacion; Web como producto digital. | Marketing diseña mecanica; Web implementa; Sponsors provee premios |
| Certificados | Academico, Web/App, Marketing, Legal | Criterio, diseño, emision y datos estan repartidos. | Academico criterio; Legal valida; Marketing diseña; Web emite |
| Post-evento premium | Marketing, Web/App, Producto/Premium | App propone upsell contextual; Marketing tambien campaña post. | Producto/Premium define oferta; Marketing comunica; Web ejecuta |
| Aecodito | Web/App, Academico, Marketing, Logistica | Necesita contexto de todas las areas y actualizacion en vivo. | Web implementa; Operaciones mantiene base; areas alimentan |

## Vacias o tareas huerfanas

1. **Owner del flujo completo de registro a asistencia real.**  
   Marketing genera demanda, Web captura, Logistica hace check-in, Direccion mira asistencia. Falta un responsable de punta a punta.

2. **Diccionario unico de datos.**  
   Web pide nombre, email, perfil, tier, documento, WhatsApp, modalidad; Marketing pide empresa, cargo, ciudad, interes; Academico necesita datos para certificados. Falta schema unico.

3. **Experiencia virtual.**  
   Marketing quiere registros virtuales; Web menciona streaming/Q&A/chat; Academico maneja agenda. Falta owner de experiencia virtual y reglas de acceso/certificado.

4. **Fuente unica de verdad para Aecodito.**  
   El brief dice que Aecodito no puede decir "no se", pero no define quien actualiza agenda, speakers, salas, sponsors, FAQs y cambios en vivo.

5. **Permisos legales para datos/contactos/networking.**  
   App propone directorio, QR de networking, contactos exportables, Premium matchmaking y uso post-evento. Falta validacion legal explicita antes de registro.

6. **Operacion de check-in fisico.**  
   QR offline es tecnologia, pero puerta necesita filas, scanners, roles, fallback manual, acreditacion, soporte y protocolo si el QR falla.

7. **Gobierno de cambios.**  
   Web propone freeze el 10 de julio. Academico tambien congela agenda. Falta una autoridad unica para aprobar excepciones.

8. **Panel admin.**  
   El brief menciona panel para cambios, ruleta, premios y agenda. Falta decidir quien lo usa, quien tiene permisos y que acciones quedan auditadas.

9. **QA de contenidos, no solo QA tecnico.**  
   Web puede probar carga y crashes, pero tambien debe probar si agenda, bios, sponsors, mapas y CTAs estan correctos.

10. **Soporte en vivo al usuario.**  
   Si nadie sabe usar app o no llega el QR, quien atiende: soporte app, staff entrada, edecanes, WhatsApp, Aecodito o mesa tecnica.

## Tensiones de alcance

- El brief Web/App parece de 16 semanas, pero estamos al 24 de abril y el evento es 17-18 de julio. Hay menos de 13 semanas reales. La app nativa completa con offline, wallet, streaming, networking, Aecodito, leaderboard, ruleta, bingo, photobooth, panel admin y Premium puede ser demasiado grande si no se prioriza.
- El brief habla de 1K inscritos objetivo, mientras Marketing propone 3,000 registros presenciales para asegurar asistencia real. Web/App debe dimensionarse para la meta nueva, no para 1K.
- App nativa "no negociable" puede chocar con tiempo real. Debe existir plan B PWA/web + QR email + pagina estatica de emergencia.

## Recomendacion de priorizacion MVP

No cortar ambicion, pero si ordenar:

1. Registro + base central + email/WhatsApp confirmacion.
2. QR unico + fallback por email + check-in operativo.
3. Landing rapida con tracking, UTMs y conversion.
4. Agenda basica + speakers + sponsors cargables desde fuente unica.
5. App/PWA con QR offline, agenda, mapa basico y notificaciones.
6. Aecodito con scope controlado: agenda, salas, FAQ, sponsors, soporte.
7. Juegos/leaderboard/ruleta solo si sponsors, premios y soporte estan cerrados.
8. Post-evento: grabaciones, certificados, premium y metricas.

## Decisiones urgentes

1. Quien es owner del flujo registro -> confirmacion -> QR -> check-in -> asistencia real.
2. Cual es la meta real de dimensionamiento: 1K inscritos o 3K presenciales + virtual.
3. App nativa completa, PWA o hibrido MVP + app si llega.
4. Que campos exactos va a tener la base unica.
5. Fecha limite para agenda/speakers/sponsors cargables.
6. Quien actualiza Aecodito y con que fuente.
7. Quien aprueba cambios despues del 10 de julio.
8. Que funcionalidades se prometen publicamente y cuales quedan como internas/no prometidas.

