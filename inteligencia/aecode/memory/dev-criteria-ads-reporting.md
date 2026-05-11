# Criterios dev - Automatizacion ADS / n8n / reportes

Fuente: sesion `2026-05-07-flujo-reportes-ads-meta-sheets-wsp`.

| Criterio | Fase donde aplica | Fuente | Fecha |
|---|---|---|---|
| En flujos de reportes ADS, separar tres capas: extraccion de datos, generacion de reportes y envio. Cada capa debe poder probarse aislada y sin enviar WhatsApp. | Dev, Ops, QA | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |
| Los reportes comerciales deben usar el mismo filtro que la fuente operativa: estado activo real + no bloqueado/completed + fechas validas + naming actual. No basta con que el RAW tenga datos. | Dev, Ads Reporting | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |
| Si el naming de campana define `DD/MM | PRODUCTO | FORM/MENSAJES`, ese naming es contrato de datos. El reporte debe excluir campanas que no cumplan el contrato cuando se trate de reportes actuales. | Dev, Ads Reporting | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |
| El objetivo de rendimiento manda sobre la metrica disponible: `FORM` se reporta como LEADS aunque tenga clics; `MENSAJES/WHATSAPP` se reporta como CONVERSACIONES; solo TRAFICO o fallback usa CLICS. | Dev, Ads Reporting | correccion usuario `VIDEO BIM` | 2026-05-07 |
| Para ventas, "lead" puede ser acumulado comercial: leads de formulario + conversaciones si el objetivo/naming es mensajes. No separar si el usuario pide lectura comercial agregada. | Dev, Ventas, Ads Reporting | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |
| Evitar IA para reportes deterministas cuando el valor esta en agregacion, filtros y formato. Desactivar nodos IA como backup en vez de borrarlos si pueden volver a servir. | Dev, Cost Control | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |
| No depender de columnas nuevas de Sheets hasta verificar que existen como headers legibles para el nodo. Si el header falla, calcular desde una fuente estable como RAW. | Dev, Sheets, QA | fallo `REPORTE PROFUNDO` no leido | 2026-05-07 |
| Todo envio WhatsApp debe tener prueba previa o rama temporal controlada. Si se crea webhook temporal para QA, se elimina al cerrar. | Dev, QA, WhatsApp | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |
| En reportes profundos por anuncio, estructura recomendada: producto -> campana -> anuncio; campos minimos: resultado por objetivo principal, CPR, CTR, frecuencia. | Dev, Ads Reporting | requerimiento usuario | 2026-05-07 |
| Al comparar Meta Ads Manager vs flujo, explicar que Meta puede mostrar metrica principal distinta del acumulado del flujo. Validar fecha, nivel de agregacion, objetivo y acciones incluidas antes de asumir error. | Dev, Ads QA | sesion flujo ADS Meta-Sheets-WSP | 2026-05-07 |

## Capsula corta para Magnus
- Reportes ADS: primero validar estado activo real, luego naming, luego objetivo de rendimiento.
- Objetivo manda: FORM -> LEADS; MENSAJES/WHATSAPP -> CONVERSACIONES; TRAFICO -> CLICS.
- No enviar WhatsApp sin preview o rama temporal; borrar webhooks temporales al cerrar.
- Si Sheets no expone headers nuevos, no insistir: calcular desde RAW o crear hoja con headers controlados.
- IA solo si agrega criterio; si el reporte es agregacion + formato, hacerlo por codigo.
