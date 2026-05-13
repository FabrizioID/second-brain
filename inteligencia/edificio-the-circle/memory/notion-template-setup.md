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
