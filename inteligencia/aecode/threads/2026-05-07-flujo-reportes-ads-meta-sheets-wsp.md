---
slug: 2026-05-07-flujo-reportes-ads-meta-sheets-wsp
proyecto: aecode
fecha: 2026-05-07
tipo: decision
---

## Objetivo del hilo
Corregir y estabilizar el sistema de reportes de Meta Ads hacia Google Sheets y WhatsApp, reduciendo consumo de IA, alineando filtros de campanas activas y separando reportes comerciales de reportes profundos por anuncio.

## Resumen ejecutivo
- Se apago la rama de IA del interpretador ADS sin borrar nodos ni columnas, dejando backup para reactivacion futura.
- Se creo reporte profundo por codigo: producto -> campana -> anuncio, con resultado por objetivo, CPR, CTR y frecuencia.
- El envio WhatsApp de las 17:00 quedo enviando reporte de ventas y reporte profundo al grupo actual, con posibilidad de cambiar luego el grupo destino.

## Estado del proyecto en este momento
- Extraccion Meta -> Sheets activa cada 30 minutos.
- Interpretador ADS activo a las 07:00 y 16:00, sin consumo de IA.
- WhatsApp ADS activo a las 17:00, con dos ramas: ventas acumulado y reporte profundo.
- El reporte profundo de WhatsApp se calcula desde RAW_Adveronix para evitar dependencia fragil de headers nuevos en Reporte_General.

## Avances detectados
- RAW_Adveronix y AGG_Ads quedaron sincronizados con el extractor recurrente.
- Se fortalecio criterio de activo real: estado efectivo/configurado, bloqueo por pausado/completed/issues y fechas de cierre.
- Se alinio el filtro de reporte profundo con el filtro de ventas: naming nuevo tipo `DD/MM | PRODUCTO | FORM/MENSAJES`.
- Se confirmo que el criterio de resultado principal debe venir del objetivo de rendimiento del naming, no de la primera metrica con volumen.

## Problemas o bloqueos
- Meta Ads Manager puede mostrar metricas principales distintas al acumulado usado por el flujo, generando aparentes diferencias.
- Reporte_General no expuso las columnas nuevas `REPORTE PROFUNDO` como headers legibles para el nodo de Sheets, por eso el envio WhatsApp profundo se movio a calculo directo desde RAW.
- Algunas campanas antiguas tenian naming no desmembrable y contaminaban agrupaciones hasta aplicar filtro de naming actual.
- Si una campana FORM aun no tiene leads, el reporte debe mostrar `0 LEADS`, no caer a `CLICS`, aunque existan clics.

## Decisiones tomadas
- Mantener nodos de IA como backup desactivado; no eliminar OpenAI ni columna `IA_Insight`.
- Generar reportes profundos por codigo deterministico para reducir tokens y evitar interpretaciones innecesarias.
- El reporte comercial de ventas conserva suma de leads generales: formularios + conversaciones cuando el objetivo/naming indica mensajes.
- El reporte profundo respeta el objetivo del anuncio/campana: FORM -> LEADS; MENSAJES/WHATSAPP -> CONVERSACIONES INICIADAS; TRAFICO -> CLICS.
- Enviar por ahora el reporte profundo al mismo grupo WhatsApp actual; luego solo cambiar grupo destino.

## Soluciones o propuestas
- Para reportes operativos, calcular al vuelo desde RAW cuando el Sheet tenga headers inestables o columnas nuevas no disponibles.
- Reusar helpers de naming/filtro entre ventas y profundo para evitar divergencia entre reportes.
- Mantener temp webhooks solo durante pruebas y limpiarlos siempre al cerrar.
- Validar workflow tras cada cambio estructural y probar preview antes de enviar al grupo.

## Patrones detectados
- `repeticion_de_error`: filtros implementados en un flujo no se propagaron automaticamente a otro, produciendo reportes incoherentes.
- `dependencia_excesiva`: depender de headers nuevos en Sheets puede romper envios aunque el calculo exista en n8n.
- `decision_sin_validacion`: si el reporte elige metrica por disponibilidad y no por objetivo de rendimiento, comunica una lectura equivocada.
- `avance_sin_cierre`: cambios de automatizacion deben cerrarse con prueba no-send, validacion y limpieza de webhooks temporales.

## Oportunidades detectadas
- Crear una mini-libreria/capsula de criterios ADS para Magnus: filtros de activo real, naming, objetivo principal, acumulados y QA de envio.
- Convertir el reporte profundo en vista separada para equipo de marketing/metodologia cuando exista grupo WhatsApp dedicado.
- Estandarizar naming obligatorio de campanas/anuncios para que todos los reportes puedan desmembrar producto, objetivo y pieza sin fallback debil.

## Aprendizajes reutilizables
- En automatizaciones de Ads, nunca mezclar criterio de estado con criterio de naming: ambos deben aplicarse cuando el reporte depende de campanas activas actuales.
- El objetivo de rendimiento manda sobre la metrica disponible: una pieza FORM con clics y cero leads se reporta como `0 LEADS`, no como clics.
- Para ventas, "lead" puede ser categoria comercial amplia: formularios + conversaciones si el objetivo es mensajes.
- Para reporting profundo, agrupar por producto/campana/anuncio y mostrar resultado objetivo, CPR, CTR, frecuencia da una lectura mas accionable que una interpretacion IA generica.
- Antes de mandar a WhatsApp, hacer preview sin envio o ejecutar rama aislada; si se usa webhook temporal, removerlo al finalizar.
- Si el flujo usa Sheets como puente, confirmar que los headers existen fisicamente y el nodo los lee; si no, calcular desde la fuente estable.

## Preguntas abiertas
- Cual sera el grupo WhatsApp nuevo para reporte profundo.
- Si el reporte profundo debe ocultar anuncios con 0 resultado objetivo o mostrarlos como alerta de gasto/sin resultado.
- Si se debe desactivar definitivamente el viejo reporte general IA o mantenerlo solo como backup visible.

## Proximos pasos
- Cuando el usuario confirme el nuevo grupo, cambiar solo destino del nodo de envio profundo.
- Evaluar si conviene crear una hoja `Reporte_Profundo` con headers controlados en vez de depender de `Reporte_General`.
- Consolidar helpers de filtros ADS en una capsula reusable para futuros agentes/flujos.

## Tags tematicos
- aecode | meta_ads | google_sheets | whatsapp | n8n | reporting_ads | automatizacion | ventas | marketing

## Tags de patron
- repeticion_de_error | dependencia_excesiva | avance_sin_cierre | decision_sin_validacion

## Tags de senal
- aprendizaje | decision | riesgo | oportunidad

## Relaciones internas del hilo
- Diferencia Meta vs Sheets -> llevo a validar frecuencia de extraccion y acumulados.
- Filtro de ventas correcto -> se replico al reporte profundo tras detectar Metodologia fuera de criterio.
- Columna nueva no legible en Sheets -> llevo a calcular reporte profundo desde RAW para WhatsApp.
- Error `VIDEO BIM: CLICS` -> corrigio regla central: objetivo de rendimiento manda sobre metrica disponible.

## Senales exportables a otros proyectos
- En reportes automatizados, separar dato operativo, interpretacion y envio; no acoplarlos si cada audiencia necesita una lectura distinta.
- Desactivar IA como backup es preferible a borrar nodos cuando la interpretacion puede volver a ser util.
- Los flujos que mandan mensajes deben tener modo preview/no-send o rama aislada para QA.
