# Extracto DOCX - BRIEF 5 Desarrollo Web AECODE

ÁREA 5 · DESARROLLO WEB AECODE + APP
La web es el punto de entrada de todo asistente antes del evento. Su función principal es informar, convertir y no generar fricciones. No es una plataforma de contenido, es una máquina de registro. Debe funcionar sin errores desde el lanzamiento de la campaña hasta el cierre del evento.
Páginas críticas: Landing principal · Registro / compra de entrada · Sponsors · Agenda · Streaming · Post-evento
Flujos que no pueden fallar: Formulario de registro → confirmación por email → acceso al QR de check-in
La app es la herramienta central de experiencia durante los 2 días del evento. Es de uso intensivo en el venue, diseñada para 800+ usuarios simultáneos. No es un sitio web responsivo — es una app nativa pensada para una mano, en espacios con mucha gente, con conectividad intermitente.
Stack sugerido: React Native o Flutter · Next.js (web) · Supabase o Firebase · Stripe · FCM · API Claude (Aecodito)
Funcionalidades OFFLINE obligatorias: QR de check-in y agenda básica — no pueden depender de internet en puerta
Formulario: nombre, email, tipo de perfil (Ejecutivo, Ingeniero, Arquitecto, Startup, Estudiante, Otro) · Selección de tier Free o Premium · Generación instantánea de QR único · Exportable a Apple Wallet / Google Wallet · Email de confirmación automático con QR adjunto como fallback · Solicitud de permiso de notificaciones push con contexto claro.
QR en pantalla completa con alto contraste — carga en menos de 1 segundo · Diferenciado por color según tier (Free / Premium / VIP) · Funciona OFFLINE (generado localmente, sin internet en puerta) · Credencial digital activada con nombre visible post-escaneo · Mensaje de bienvenida personalizado.
Banner 'En vivo ahora' con acceso directo al streaming · Próximas 2 sesiones del día (favoritas primero) · Feed de notificaciones recientes: cambios de sala, sorteos, sesiones · Puntaje actual en el leaderboard · CTA de ruleta si aún no se giró ese día · Accesos rápidos: Agenda, Mapa, Networking, Aecodito.
Selector Día 1 / Día 2 · Tarjetas: hora, duración, sala, speaker, track (ordenadas cronológicamente) · Filtros por track: BIM, Automatización, Computer Vision, Robótica, IA Generativa, Supply Chain, Seguridad · Botón 'Guardar' → activa push 10 min antes · Indicador 'En vivo' en sesiones activas · Sesiones con quiz/encuesta marcadas con ícono especial.
Plano del CIP con 30+ stands ubicados, numerados y navegables con zoom · Diferenciados por nivel: Diamante / Gold / Silver · Tap en stand: perfil, productos, demo, contacto y 'Guardar empresa' · QR por stand (participar en sorteo, sumar puntos al leaderboard) · Listado alternativo filtrable por nombre · Stands con sorteo activo marcados con indicador especial.
Listado con foto, nombre y empresa · Filtrable por día o por track · Tap: bio completa, ponencia, redes sociales · Sesiones con horario y sala (tap directo a la agenda) · Botón 'Guardar contacto' → se agrega a Mis Contactos.
Perfil público configurable por el usuario · QR de networking para intercambio digital · Directorio de asistentes con filtros por sector, empresa y cargo · Mis Contactos: listado de QR escaneados durante el evento · PREMIUM: matchmaking automático por perfil e intereses · PREMIUM: agenda de reuniones 1:1 en zona VIP con mesas y horarios asignados.
Player de video (YouTube Live o Zoom embebido) · Info de sesión en curso: título, speaker, track, tiempo restante · Contador de personas viendo en vivo · Acceso al Q&A o chat · Encuesta en vivo como overlay (resultado en pantalla LED) · Quiz estilo Kahoot al final de la sesión (ranking en auditorio).
Botón flotante persistente en todas las pantallas · Responde preguntas del evento: agenda, horarios, salas, speakers · Orienta en el mapa · Gestiona agenda personal desde el chat · Recomienda contactos según perfil · Comunica alertas proactivamente · Ofrece membresía Premium con link de compra · Post-evento: presenta oferta Premium contextualizada según lo que vivió el usuario.
Motor: API de Claude (Anthropic) con contexto completo del evento inyectado. Aecodito NO puede responder 'no sé' sobre el Summit.
Leaderboard en tiempo real (home + zona de juegos) · Acciones que suman puntos: check-in, asistir a sesiones, escanear stands, conectar, girar ruleta, responder quiz, completar bingo · Top 3 al cierre del día 2 sube al escenario.
Ruleta: 1 giro por día (reset a 00:00 del día 2) · Premios configurables desde panel admin.
Bingo de networking: cartón con misiones para los 2 días (ej: 'Conoce a un CEO', 'Escanea 3 stands Gold', 'Foto con Aecodito').
Photobooth IA: generador de foto con filtro AECODE Summit 2026 desde la cámara del celular · Compartir a LinkedIn e Instagram con hashtag del evento.
Grabaciones organizadas por día y track · Free: acceso a 2–3 sesiones · Premium: acceso completo · Certificado de asistencia descargable en PDF · Mis contactos con opción de exportar o conectar en LinkedIn · Resumen de actividad: sesiones, stands, puntos · Oferta Premium via Aecodito contextualizada · Premium: acceso a comunidad privada, cursos y contenido por 12 meses.
1. Entendimiento del área y del rol
1. ¿Qué páginas o flujos son los más críticos para el Summit: registro, sponsors, agenda, acceso, post-evento?
Flujo de Registro por la web para el usuario, recopilar datos criticos(nombre completo, nro. doc. identidad, tipo de modalidad, wsp,correo) código OTP
Flujo del Acceso al evento para el staff: Scanner del QR y validación del acceso.
La agenda debe mostrar las horas de exposición de cada speaker, las dinámicas, los retos a realizarse para cargar a la app y web.
El listado de sponsor y las dinámicas a realizar deben estar definidas hasta cierta fecha para configurar la lógica de la suma de puntos(tomarse foto, grabar un video, adquirir merch)
2. ¿Qué errores de la web de la edición anterior no se pueden repetir?
El QR no puede fallar bajo ninguna circunstancia Crítico
Es el primer contacto físico del asistente con la app. Si falla ahí, pierde confianza en todo lo demás. Solución: QR generado y guardado localmente — funciona sin internet, sin servidor, sin excepción.
La app no puede ser solo "consulta de info"
Si el asistente solo entra a ver la agenda y la cierra, la app fracasó. Cada pantalla debe tener al menos una acción: guardar, escanear, responder, girar, conectar. El chatbot y los juegos existen exactamente por esto.
Una web responsiva no es una app de evento
Una web no tiene notificaciones push, no funciona offline, no accede a la cámara para escanear QR sin fricción, no se puede instalar en el home screen con un tap. Para este Summit, la experiencia nativa es no negociable.
3. ¿Qué información debe estar clarísima desde la primera pantalla sin hacer scroll?
Que el evento es gratuito
Lo nuevo de esta versión
Fecha y hora explicita
cta de inscripción
4. ¿Qué flujo debe funcionar perfecto sin excepción: registro, compra de entrada, confirmación, recordatorio pre-evento?
Registro
Compra de entrada
Confirmación de la compra
Acceso el dia del evento
Asistente aecodito(edecan)
Agenda
Dinámicas
Emisión de certificado asistencia
5. ¿Cómo definen ustedes que la web "funcionó bien" el 18 de julio?
Nadie le pregunta al staff cómo usar la app
Aecodito responde bien las 3 preguntas más frecuentes
Tasa de conversión a Premium post-event
los asistentes interactuan de manera facil con la agenda
visualizacion automatica de certificado desde su app o aecode plataforma
2. Herramientas, orden y automatizaciones operativas
No hablamos de grandes plataformas ni de agentes de IA complejos. Hablamos de lo operativo: cómo se organizan, cómo se comunican, cómo no se pierden cosas.
Herramientas de trabajo y organización:
1. ¿Qué stack o CMS están usando y quién tiene acceso de edición?
2. ¿Dónde documentan los cambios que se hacen en la web para que todo el equipo esté al tanto?
La documentación se realizará en notion, drive.
3. ¿Qué herramienta usan para detectar errores o caídas en la web en tiempo real?
Logs en consola
4. ¿Cómo van a hacer pruebas de carga antes del evento, considerando que puede haber picos de tráfico?
Pruebas de Estrés y de Carga con herramientas como Jmeter o K6
5. ¿Dónde está el registro de accesos, contraseñas y proveedores de hosting?
Toda la documentación técnica se encuentra registrado en el notion
Automatizaciones operativas (agentes de correo, recordatorios automáticos, formularios, flujos de notificación):
1. ¿Qué formularios de registro están conectados a qué base de datos o CRM? ¿Funciona en tiempo real o hay demora?
En la pasarela de pagos, esta conectado los registros pagados en la BD a al sheet segun modalidad, evento, datos del usuario.
2. ¿Qué notificaciones automáticas recibe alguien cuando hay un nuevo registro o una compra?
Ahora solo el correo, la notificación llega al correo de contacto.
Se implementará la notificación al wsp con un agente automatizado.
3. ¿Tienen activados recordatorios automáticos por email para asistentes registrados (confirmación, pre-evento, día del evento)?
Solo el correo de confirmacion
Se implementará notificación de recordatorio por correo y por wsp
4. ¿Qué alertas automáticas activan si la web cae, si el formulario falla o si hay un error de pago?
No se tiene actualmente una notificación que indique error.
Se propone implementar notificaciones para los logs
5. ¿Cómo automatizan la actualización de la agenda en la web cuando hay cambios de programa?
Inicialmente se propone mantener un orden ya definido dias antes para cargar la info y se mantenga tal cual. Sin embargo, para contingencias, se propone crear un panel donde permita actualizar el orden o cambios en fechas del programa.
3. Checklist del área — Lo construyen ustedes
Esta sección no tiene respuestas predefinidas. El equipo tiene que construir su propio checklist. Para cada momento, escriban las tareas concretas que no pueden faltar.
Checklist: Antes del evento — funcionalidad y contenido
Qué páginas deben estar publicadas, qué flujos probados, qué integraciones funcionando.
☐ Landing Summit con registro de usuario, notificación por correo y aviso a ventas
☐
☐ ________________________
☐ ________________________
☐ ________________________
Checklist: Semana previa — pruebas finales
Qué prueban por última vez antes de congelar cambios: formularios, pagos, links, velocidad.
☐ ________________________
☐ ________________________
☐ ________________________
☐ ________________________
☐ ________________________
Checklist: Durante el evento — monitoreo
Qué monitorean en tiempo real y cómo responden si algo falla.
☐ ________________________
☐ ________________________
☐ ________________________
☐ ________________________
☐ ________________________
Checklist: Después del evento — cierre web
Qué actualizan post-evento: página de gracias, recursos descargables, próxima edición.
☐ ________________________
☐ ________________________
☐ ________________________
☐ ________________________
☐ ________________________
4. Riesgos e imprevistos — Los identifican ustedes
No es un listado genérico. Ustedes tienen que pensar qué puede salir mal en SU área, en UN evento de 800 personas, con SU equipo. Por cada riesgo que identifiquen, describan también su plan B.
1. ¿Qué pasa si el formulario de registro cae el día que se lanza la campaña principal?
El formulario de registro cae el día del lanzamiento de campaña
Pico de tráfico masivo, servidor saturado, formulario no carga o no guarda datos
Activar formulario de emergencia en Google Forms o Tally Tech
Tiene el mismo campo que el formulario original. Se activa en menos de 5 minutos.
Prevención
Hacer un stress test con 500 registros simultáneos simulados 48h antes del lanzamiento
Tener el formulario de emergencia creado y probado — no se crea en el momento de la crisis
3. ¿Cómo manejan una caída total de la web durante el evento — tienen backup o página de emergencia?
Activar página de emergencia estática (HTML puro en CDN): agenda del día, mapa en imagen, info básica
No tiene backend — no puede caerse. Sirve desde Cloudflare o Netlify en menos de 1 minuto.
Comunicar el tiempo estimado de restauración — aunque sea "estamos trabajando, en 30 minutos actualizamos"
El silencio genera más pánico que un mensaje honesto de "estamos en ello".
La página de emergencia existe, está deployada y su link está guardado en el teléfono de cada coordinador
4. ¿Qué ocurre si hay cambios de agenda o información urgente que hay que publicar el mismo día del evento?
El sistema de notificaciones push debe estar probado — saber cuánto tarda en llegar a los dispositivos
Definir quién tiene permiso de publicar cambios en la app — máximo 2 personas con acceso al CMS el día del evento
5. ¿Qué pasa si otras áreas siguen pidiendo cambios en la web muy cerca del evento y eso genera errores?
Fecha de congelamiento de contenido: 10 de julio
Después de esa fecha, cero cambios en producción salvo errores críticos. Punto, sin excepciones.
Cualquier cambio solicitado después del 10 de julio va a una lista de espera post-evento
No se descarta — se agenda para después del 18. Esto mantiene al equipo enfocado y sin presión de última hora.
Si el cambio es genuinamente crítico (error de dato, información incorrecta), pasa por aprobación del director del evento — no del área que lo pide
El equipo Dev necesita los últimos 7 días para probar, no para implementar pedidos de otras áreas
Si el equipo está haciendo cambios a las 11pm del 16 de julio, el 17 nadie descansa tranquilo.
5. Dependencias y cruces con otras áreas
1. ¿Qué contenido necesitan del área Académica para la página de speakers y agenda?
Data: - Foto de cada speaker, fondo neutro o profesional. No fotos de redes sociales recortadas.
- Bio corta de cada speaker: Máximo 120 palabras, en tercera persona. Cargo actual, empresa, especialidad. Entregada en texto plano
- Título exacto de cada ponencia: El título definitivo — no "tentativo" ni "por confirmar"
- Programa definitivo con horarios: Día 1 y Día 2 completos: hora inicio, hora fin, título de sesión, speaker asignado, sala/auditorio, track temático.
- LinkedIn o web del speaker: URL exacta. Si no se entrega, no se agrega el botón de contacto en el perfil del speaker.
2. ¿Qué materiales necesitan de Sponsors para sus páginas o menciones en la web?
Logo en alta resolución: Formato SVG o PNG con fondo transparente.
Descripción de la empresa: Máximo 80 palabras. Qué hace la empresa y su relación con el sector AEC o IA. En texto plano.
URL del sitio web y redes: Link exacto al que apunta el botón
Nivel de sponsorship confirmado: Diamante / Gold / Silver — confirmado por el área comercial.
3. ¿Qué necesitan de Marketing para las landing pages de campañas de pauta?
Copy aprobado: Título, subtítulo y CTA definitivos — aprobados por Marketing antes de pasarlos a desarrollo. El equipo web no escribe copy de campaña.
Assets visuales: Imágenes o videos ya exportados en los tamaños correctos para web.
Pixel o eventos de conversión: Qué evento dispara la conversión: ¿clic en el botón? ¿envío del formulario? ¿llegada a la pantalla de confirmación? Definido antes del desarrollo.
Fecha de activación de la pauta: La landing debe estar lista y probada al menos 48h antes de que empiece a correr la pauta. No el mismo día.
4. ¿Qué integración necesitan del área de Tecnología para conectar registros a la base central?
6. Plan de acción por tramos de tiempo
Para cada tramo, escriban tareas concretas con responsable. No aspiraciones generales.
7. El 17 y 18 de julio — Operación hora a hora
Esta es la sección más importante. No puede haber ambigüedad sobre quién hace qué en cada momento. Si no saben la respuesta, ese es el bloqueo que tienen que resolver primero.
Protocolo de incidencias el día del evento:
1. ¿Cuál es el canal único de comunicación interna de su área durante el evento (WhatsApp, radio, app)?
2. ¿Quién es el responsable de escalar un problema si excede al área?
3. ¿Qué tipo de decisión puede tomar el área sola y cuál necesita validación central?
4. ¿Qué haces si falta un miembro del equipo el día del evento — quién cubre, cómo?
5. ¿Qué hace el área si ocurre un imprevisto técnico, logístico o de seguridad que afecte a su zona?
8. Después del evento — Cierre y seguimiento
El evento termina el 18 de julio, pero el área no. Definan desde ahora cómo cierran.
1. ¿Cuándo publican los recursos, grabaciones o materiales post-evento?
2. ¿Qué métricas de la web reportan al equipo central (visitas, registros, conversión)?
3. ¿Cuándo actualizan la web para la edición 3 y qué conservan de esta?
Cierre de la reunión — Lo que el área deja escrito hoy
Antes de terminar esta reunión, respondan esto juntos y déjenlo escrito.

## Tabla 1

| 800+ Asistentes presenciales | 1K+ Inscritos objetivo | 30+ Stands B2B | LATAM Streaming en vivo |

## Tabla 2

| 00 | CONTEXTO DEL PROYECTO Qué se está construyendo y por qué importa |

## Tabla 3

|  | Este área tiene a cargo dos productos digitales críticos del evento: la web oficial y la app móvil. Ambos son independientes pero comparten backend, datos y autenticación. El equipo de dev es responsable de que los 800+ asistentes puedan registrarse, ingresar, navegar y vivir el Summit sin fricciones técnicas. |

## Tabla 4

| WEB OFICIAL — summitaecode.com |

## Tabla 5

| APP MÓVIL — iOS & Android |

## Tabla 6

| 01 | STACK TECNOLÓGICO DEFINIDO Decisiones técnicas que el equipo debe confirmar en kick-off |

## Tabla 7

| Equipo | WEB | APP MÓVIL |
| Frontend | Next.js (SSR + SSG) | React Native / Flutter |
| Backend / BaaS | Supabase o Firebase | Supabase o Firebase (compartido) |
| Diseñador UX/UI | Figma - Claude - Miro | Figma - Clude - Miro |
| Project manager | Jira - Miro | Jira - Miro |
| Pagos | Stripe (membresía Premium) | Stripe (in-app) |
| Streaming | YouTube Live / Zoom embed | YouTube Live / Zoom embed |
| Push notifications | N/A (email vía SendGrid o similar) | Firebase Cloud Messaging (FCM) |
| Chatbot Aecodito | Widget embed (Claude API) | Pantalla nativa (Claude API) |
| CRM / Analytics | HubSpot + GA4 | Panel admin propio + analytics RT |
| QR offline | N/A | Generado localmente en el dispositivo |
| Wallet export | N/A | Apple Wallet / Google Wallet |

## Tabla 8

|  | El stack de autenticación y base de datos debe ser compartido entre web y app. Un asistente registrado en la web debe poder hacer check-in con el QR en la app sin necesidad de registrarse de nuevo. |

## Tabla 9

| 02 | SECCIONES DE LA APP — ALCANCE FUNCIONAL 11 módulos · Detalle de qué debe contener cada uno |

## Tabla 10

| 01 · Onboarding & Registro |

## Tabla 11

| 02 · Check-in |

## Tabla 12

| 03 · Home del evento |

## Tabla 13

| 04 · Agenda |

## Tabla 14

| 05 · Mapa de feria |

## Tabla 15

| 06 · Speakers |

## Tabla 16

| 07 · Networking |

## Tabla 17

| 08 · Streaming en vivo |

## Tabla 18

| 09 · Chatbot — Aecodito |

## Tabla 19

| 10 · Zona de juegos |

## Tabla 20

| 11 · Post-evento |

## Tabla 21

| 03 | FASES DE DESARROLLO Roadmap de 16 semanas hasta el go-live · 10 de julio 2026 |

## Tabla 22

| FASE | NOMBRE | ALCANCE | TIEMPO |
| Fase 1 | MVP de evento | WEB: landing + registro + Stripe · APP: Onboarding + QR offline + Check-in + Agenda + Home | Semanas 1–4 |
| Fase 2 | Experiencia completa | WEB: agenda pública + speakers + sponsors · APP: Mapa de feria + Streaming + Speakers + Networking | Semanas 5–8 |
| Fase 3 | Engagement | APP: Chatbot Aecodito (Claude API) + Leaderboard + Ruleta + Bingo + Quiz · Panel admin AECODE | Semanas 9–12 |
| Fase 4 | QA y lanzamiento | Testing de carga (800 usuarios simulados) · QA completo web y app · Deploy · Onboarding al equipo AECODE | Semanas 13–16 |
| Post | Retención Premium | Grabaciones + certificados + comunidad · Upsell Premium via Aecodito · Métricas post-evento | Post julio 2026 |

## Tabla 23

|  | Go-live de la app y la web en estado final: 10 de julio de 2026 — 7 días antes del evento. Sin excepciones. |

## Tabla 24

| 04 | KPIs DE ÉXITO Métricas que el equipo de dev debe poder medir y reportar |

## Tabla 25

| KPI | TARGET | APLICA A |
| Descarga de la app pre-evento | 90% de inscritos | App |
| Check-in en menos de 30 segundos | 95% de asistentes | App |
| Asistentes que guardan ≥2 sesiones como favoritas | 70% | App |
| Interacción con Aecodito durante el evento | ≥50% de asistentes | App |
| Activación de ruleta el día 1 | ≥60% de asistentes | App |
| Promedio de contactos escaneados por asistente | 5 contactos | App |
| Conversión Free → Premium (7 días post-evento) | 15% de asistentes Free | App + Web |
| Tasa de rebote en landing de registro | <40% | Web |
| Tiempo al QR de check-in (desde app abierta) | <1 segundo | App |
| Crashes en check-in y QR | 0 — cero tolerancia | App |
| Crashes en el resto de la app | ≤0.5% | App |
| Push notifications — tiempo de entrega | <5 segundos | App |

## Tabla 26

| Riesgo que identificamos | Nuestro plan B o medida de mitigación |
| ________________________ | ________________________ |
| ________________________ | ________________________ |
| ________________________ | ________________________ |
| ________________________ | ________________________ |
| ________________________ | ________________________ |

## Tabla 27

| Necesitamos de esta área | Qué necesitamos exactamente y para cuándo |
| ________________________ | ________________________ |
| ________________________ | ________________________ |
| ________________________ | ________________________ |

## Tabla 28

| Esta área nos pedirá | Qué debemos tener listo y para cuándo |
| ________________________ | ________________________ |
| ________________________ | ________________________ |
| ________________________ | ________________________ |

## Tabla 29

| Tramo | ¿Qué debe estar hecho o encaminado? |
| EN 3 SEMANAS (antes del 13 mayo) | ________________________________________________________________________ |
| EN 6 SEMANAS (antes del 3 junio) | ________________________________________________________________________ |
| EN 9 SEMANAS (antes del 24 junio) | ________________________________________________________________________ |
| SEMANA PREVIA (10 al 16 julio) | ________________________________________________________________________ |

## Tabla 30

| Semana previa (10-16 julio) — ¿Qué revisan, confirman y dejan listos? |
| ▸ ¿Qué freezan definitivamente la semana previa? |
| ▸ ¿Qué pruebas finales hacen antes del 17? |

## Tabla 31

| DÍA 1 — 17 de julio — ¿Cómo operan exactamente? |
| ▸ ¿Quién monitorea la web durante el evento? |
| ▸ ¿Cuál es el protocolo si cae el servidor o el formulario? |
| ▸ ¿Cómo publican actualizaciones urgentes de agenda o logística sin romper el sitio? |

## Tabla 32

| DÍA 2 — 18 de julio — ¿Qué cambia respecto al día 1? |
| ▸ ¿Qué actualizan al final del día 2? |
| ▸ ¿Cuándo activan la página post-evento con recursos y grabaciones? |

## Tabla 33

| Acuerdos del área |
| Nuestras 3 prioridades más urgentes esta semana son: |
| 1. ________________________ |
| 2. ________________________ |
| 3. ________________________ |
|  |
| Lo que más nos puede complicar la ejecución es: |
| ________________________ |
|  |
| Lo que necesitamos de otras áreas esta semana es: |
| ________________________ |
|  |
| Si el 17 y 18 de julio nuestro frente sale bien, se verá así: |
| ________________________ |
|  |
| El responsable de hacer seguimiento a este canvas es: ________________________ |
| Próxima revisión de avance: ________________________ |