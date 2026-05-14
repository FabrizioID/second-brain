# Notion Setup - Edificio The Circle

## Pagina
Proyecto creado en Notion de Fabrizio:
https://www.notion.so/EDIFICIO-THE-CIRCLE-35fd8cc4cfc18181a63ae9b059b02a4b

## Configuracion corregida
- `ACTIVIDADES` debe mantener 3 vistas:
  - `Vista Filtrada`: board agrupado por `Status`, filtro real `Status` no es `Listo`, grupos vacios ocultos.
  - `Original`: board agrupado por `Status`, sin filtro restrictivo.
  - `Status`: tabla agrupada por `Entregable`.
- `REUNIONES`:
  - `Tabla General`
  - `Calendario`

## Dato operativo clave
Los documentos prometidos por Ferralia no son cartilla final aun. Son:
- Plantilla de planilla para pasar/importar informacion a Graphico.
- Plantilla RFI.

## Criterio tecnico de alerta
Para vigas y columnas, puede ocurrir que la planta y los detalles no cuadren en dimensiones.

Regla:
- No asumir automaticamente que manda la planta o que manda el detalle.
- Cuando se detecte una diferencia dimensional, alertar.
- Registrar el caso con bloque/zona, elemento, dimension en planta, dimension en detalle y observacion.
- Levantar consulta/RFI para que Ferralia defina que fuente manda o que correccion aplica.
- Este criterio no debe vivir como bloque visible suelto en la pagina principal porque no corresponde a la plantilla tipo Tingo. Debe quedar como actividad/RFI y como memoria interna.

## Verificacion realizada
- `Vista Filtrada` en ACTIVIDADES tiene filtro real aplicado: `Status` no es `Listo`.
- La vista `Status` en ACTIVIDADES es tabla agrupada por `Entregable`.
- Se archivo de Notion la base extra `CONTROL POR BLOQUE` porque no corresponde a la plantilla tipo Tingo.
- Se archivaron los bloques visibles `CRITERIO TECNICO - PLANTA VS DETALLE` porque el criterio debe vivir como actividad/RFI y memoria, no como seccion suelta.
- Se archivaron de Notion las bases `DOCUMENTOS` y `CONTACTOS CLIENTE` porque tampoco correspondian a la plantilla aplicada para The Circle.

## Sincronizacion con TO-DO LIST
El 2026-05-14 se creo el proyecto como fila padre/desplegable en la base global:
- Base: `TO-DO LIST > T.TRABAJO (8 hr: 09:00 - 17:00) > ACTIVIDADES`.
- Padre: `The Circle`.
- Page ID padre: `360d8cc4-cfc1-81b7-99e0-e29f4a142aa6`.
- Empresa: `GEN+`.
- Subitems creados:
  - `G | Preparar RFI inicial`.
  - `D | Preparar matriz de avance por bloque y elemento`.
  - `D | Organizar avance preliminar de vigas por zona`.
  - `D | Controlar discrepancias planta vs detalle en vigas/columnas`.
- Fecha objetivo aplicada: `2026-05-15` para las actividades internas y los subitems globales, porque el usuario aclaro que el trabajo era para este fin de semana.
- 2026-05-14: Se agregaron 3 subitems globales bajo `The Circle`:
  - `G | Validar torre de inicio con Carlos` con Status `100`.
  - `G | Pasar informacion y plantilla de planilla a Alex` con Status `100`.
  - `G | Hacer seguimiento a Alex para croquis/despiece Torre A1` con Status `0`.
- Regla confirmada por usuario: Codex puede actualizar `Status`, pero no debe marcar `Checkbox` en la base global salvo pedido explicito.
