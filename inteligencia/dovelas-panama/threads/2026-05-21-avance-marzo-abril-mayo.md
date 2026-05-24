---
slug: 2026-05-21-avance-marzo-abril-mayo
proyecto: Dovelas Panama
fecha: 2026-05-21
tipo: sintesis
---

## Objetivo del hilo
Abrir el hilo del proyecto Dovelas Panama y documentar el avance mostrado en el control de entregas de marzo, abril y mayo, junto con el seguimiento a Guisella para actividades pendientes.

## Resumen ejecutivo
- Proyecto de detallamiento de dovelas por tramos de un viaducto en Panama.
- Marzo y abril figuran completados al 100% en los tramos registrados.
- Mayo esta casi cerrado: hay dovelas completadas, una dovela al 90% y una sin iniciar; se requiere seguimiento a Guisella para cierre, tonelajes y fechas.

## Estado del proyecto en este momento
- Ya se estan haciendo entregas por tramo.
- En Notion existe el proyecto `DOVELAS PANAMA` y el padre operativo `Dovelas Ferralia Panama`.
- Se cargaron actividades nuevas de seguimiento y validacion bajo el padre operativo.

## Avances detectados
- Marzo - tramo W19d - W20d: dovelas 6, 7, 8 y 9 al 100%, status `Completado`, tonelaje total 34 t.
- Abril - tramo W08d - W09d: dovelas 11, 12, 10, 13, 9, 14, 8, 15, 7, 16, 6, 17, 5, 18, 4, 3, 2 y 1 al 100%, status `Completado`, tonelaje total 171.4 t.
- Mayo - tramo W11d - W10d: control muestra avance mayormente completado y tonelaje visible total 114.8 t.
- Mayo completadas al 100% con fecha visible: dovelas 6 y 7 el 11-may; 3 y 13 el 12-may; 10, 9 y 8 el 13-may; 14 el 14-may; 12 y 15 el 15-may; 4 y 11 el 16-may; 5 el 17-may; 2 el 18-may; 16 el 19-may.
- Mayo pendientes/observadas: dovela 17 al 90% en proceso con fecha 20-may; dovela 1 al 0% sin iniciar con fecha 20-may.
- Se registro en Notion una actividad de hito: `G | Registrar avance acumulado marzo-abril-mayo de dovelas`.
- Se registro en Notion una actividad de seguimiento: `G | Seguimiento a Guisella - cierre de dovelas tramo W11d-W10d`.
- Se registro en Notion una actividad de validacion: `G | Validar tonelajes y fechas faltantes de mayo - Dovelas Panama`.
- 2026-05-21: Se corrigio la pagina del proyecto `DOVELAS PANAMA` en Notion creando una base inline `REUNIONES` dentro de la pagina del proyecto y cargando alli el resumen de avance/reunion.
- 2026-05-21: Se reviso la pagina del proyecto contra la plantilla operativa y estaba casi vacia: solo tenia una transcripcion vacia y `REUNIONES`. Se completo con `DESCRIPCION`, `ACCESOS`, `INFORMACION`, `ACTIVIDADES`, `CONTROL POR TRAMO`, `DOCUMENTOS` y `CONTACTOS CLIENTE`.
- 2026-05-21: Se recargo la skill `documentar-notion` actualizada y se corrigieron las vistas de `ACTIVIDADES`: `Vista Filtrada` como board por `Status` excluyendo `Listo`, `Original` como board por `Status`, y `Status` como tabla agrupada por `Entregable`.

## Problemas o bloqueos
- En mayo el tonelaje visible suma 114.8 t, pero no se observan tonelajes para las ultimas filas del control mostrado.
- La dovela 17 esta al 90%, por lo que aun requiere cierre.
- La dovela 1 figura al 0% y sin iniciar, por lo que requiere confirmacion de plan de arranque.
- La continuidad de entregas depende del seguimiento a Guisella y de confirmar fechas/tonelajes faltantes.

## Decisiones tomadas
- Crear `dovelas-panama` como slug/carpeta del proyecto en memoria local.
- Usar `Dovelas Panama` como nombre canonico del proyecto.
- Registrar el avance por mes, tramo, dovela, porcentaje, status, fecha y tonelaje cuando este disponible.
- Mantener el seguimiento a Guisella como actividad operativa en Notion.

## Soluciones o propuestas
- Consolidar una tabla maestra por tramo con dovela, status, fecha, tonelaje y observacion.
- Usar el total mensual como control rapido: marzo 34 t, abril 171.4 t, mayo 114.8 t visible.
- Separar completados de pendientes para mayo y no cerrar el paquete sin validar dovela 17, dovela 1 y tonelajes faltantes.

## Patrones detectados
- avance_sin_cierre: hay entregas avanzadas, pero mayo todavia tiene filas pendientes o incompletas que necesitan cierre formal.
- dependencia_excesiva: la confirmacion de cierre depende de Guisella y de datos visibles/actualizados del control.

## Oportunidades detectadas
- Convertir el control visual mensual en una memoria estructurada reutilizable.
- Crear una regla de cierre por tramo: todas las dovelas al 100%, fecha confirmada y tonelaje validado.
- Usar las actividades de Guisella como punto unico de seguimiento para no perder pendientes.

## Aprendizajes reutilizables
- En proyectos de dovelas, el avance por porcentaje no basta: debe cruzarse con fecha y tonelaje.
- Cuando un control tiene totales visibles pero filas sin tonelaje, conviene validar antes de declarar cierre total.
- Para entregas seriadas por tramo, el hilo mensual ayuda a detectar rapido que queda pendiente.

## Preguntas abiertas
- Cual es el tonelaje de las dovelas de mayo que no se ve en la imagen.
- Si la dovela 16 de mayo debe considerarse cerrada aunque no tenga tonelaje visible en el recorte.
- Cual es la fecha objetivo para cerrar la dovela 17 y arrancar/cerrar la dovela 1.
- Si el total de mayo 114.8 t corresponde solo a dovelas con tonelaje visible o al paquete completo reportado.

## Proximos pasos
- Hacer seguimiento a Guisella para cerrar la dovela 17 del tramo W11d - W10d.
- Confirmar plan y fecha para la dovela 1, actualmente sin iniciar.
- Validar tonelajes faltantes de mayo.
- Registrar el cierre final del tramo W11d - W10d cuando todas las dovelas esten completadas.
- Usar la base `REUNIONES` dentro de `DOVELAS PANAMA` para futuros resúmenes de reunion/avance, no solo el tablero global de actividades.
- Mantener las actividades de seguimiento en la base interna `ACTIVIDADES` del proyecto y usar `CONTROL POR TRAMO` para trazabilidad mensual por tramo, dovelas y tonelaje.

## Tags tematicos
- dovelas_panama
- viaducto
- detallamiento
- entregas
- guisella
- tonelaje
- marzo
- abril
- mayo

## Tags de patron
- avance_sin_cierre
- dependencia_excesiva

## Tags de senal
- aprendizaje
- decision
- riesgo
- oportunidad

## Relaciones internas del hilo
- Control visual mensual -> genera memoria estructurada del avance.
- Mayo con pendientes -> activa seguimiento a Guisella.
- Tonelajes visibles incompletos -> exige validacion antes de cierre.

## Senales exportables a otros proyectos
- En proyectos seriados de detallamiento, el avance debe documentarse por unidad repetitiva, estado, fecha y cantidad metrica para sostener control real de entrega.
