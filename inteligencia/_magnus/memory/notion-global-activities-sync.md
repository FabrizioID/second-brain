# Notion Global Activities Sync

## Regla de checkbox
Codex puede actualizar `Status`, `Date`, `Empresa`, relaciones y observaciones, pero no debe marcar ni desmarcar `Checkbox` en la base global salvo que el usuario pida explicitamente esa accion.

## Regla de responsabilidad
En la base global `TO-DO LIST > T.TRABAJO > ACTIVIDADES`, registrar solo lo que el usuario debe ejecutar o seguir directamente.

Si una actividad de proyecto sera ejecutada por otra persona, no cargarla como tarea directa del usuario en el status global. En ese caso:
- Mantener la actividad tecnica en la base `ACTIVIDADES` del proyecto si sirve para control del proyecto.
- En la base global crear solo una tarea de seguimiento/coordinacion.
- Ejemplo The Circle: Alex ejecuta croquis/despiece; en global debe quedar `G | Hacer seguimiento a Alex...`, no tareas `D | Organizar avance...` como si fueran ejecucion directa del usuario.

## Uso de Observacion
La propiedad `Observacion`/`Observación` de la base global se usa para agregar detalles sobre la actividad.

Usarla para:
- Contexto del proyecto.
- Cliente.
- Responsable real de ejecucion.
- Que debe seguir el usuario.
- Bloqueo o criterio tecnico relevante.
- Fuente de la actividad.
- Razon del status.

No dejarla vacia cuando el contexto sea necesario para entender la tarea despues.

## Fechas operativas
Si el usuario comunica una fecha operativa o deadline, siempre mapearla a:
- `Date` en la base global `TO-DO LIST > T.TRABAJO > ACTIVIDADES`.
- La fecha limite de la actividad del proyecto cuando esa propiedad exista.

Para The Circle, el usuario aclaro que el trabajo era para este fin de semana; se aplico `2026-05-15` como fecha objetivo en:
- Los 4 subitems globales bajo el padre `The Circle`.
- Las actividades internas del proyecto en Notion.

## Regla
Toda actividad creada o actualizada en una base `ACTIVIDADES` de proyecto Notion debe sincronizarse tambien con el status general de trabajo.

Importante: la base global no es una lista plana. Funciona con filas padre/desplegables por proyecto o frente de trabajo, y actividades directas como subitems dentro de cada padre.

## Destino global
- Pagina: `TO-DO LIST`
- URL: https://www.notion.so/TO-DO-LIST-e2066553a8494738976450204e36efd7
- Page ID: `e2066553-a849-4738-9764-50204e36efd7`
- Subpagina: `T.TRABAJO (8 hr: 09:00 - 17:00)`
- Work page ID: `241d8cc4-cfc1-80e7-bce2-f01e6a14c7f4`
- Base: `ACTIVIDADES`
- Database ID: `2dcd8cc4-cfc1-806c-bda6-f9c4862a9cfd`
- Data source ID: `2dcd8cc4-cfc1-8121-a268-000b4f55c021`

## Propiedades verificadas
- `Actividad` title.
- `Status` number.
- `Empresa` rich_text.
- `Date` date.
- `Observación` rich_text.
- `Checkbox` checkbox.
- `Parent item` relation.
- `Sub-item` relation.

## Estructura real observada
- La base global esta organizada por proyectos/frentes como filas padre.
- Ejemplos de filas padre: `AI Summit`, `I-Lanza`, `Cerco Perímetrico Tarjea`, `Dovelas Ferralia Panama`, `Comercial`.
- Una fila padre normalmente tiene:
  - `Actividad` = nombre del proyecto/frente.
  - `Empresa` = `AECODE`, `GEN+` o `THESIA`.
  - `Status` vacio.
  - `Parent item` vacio.
  - `Sub-item` con relaciones a las actividades hijas.
- Una actividad directa normalmente tiene:
  - `Actividad` con prefijo operativo, por ejemplo `G | ...`, `D | ...`, `O | ...`.
  - `Empresa` igual a la fila padre.
  - `Status` numerico.
  - `Parent item` apuntando a la fila padre.

## Mapeo recomendado
- Proyecto/frente -> fila padre global.
- Actividad de proyecto -> subitem/actividad hija global.
- `% Avance` del proyecto -> `Status` numerico global.
- Pendiente/bloqueado/en proceso sin avance -> `0`.
- Listo/cerrado -> `100`.
- Organizacion paraguas -> `Empresa`.
- Proyecto, cliente, bloque, entregable y origen -> `Observación`.
- Fecha limite del proyecto, si existe -> `Date`.

## Convencion de nombre
Para la fila padre usar el nombre limpio del proyecto/frente:

`The Circle`

Para actividades hijas usar prefijo operativo + descripcion:

`G | <actividad de gestion>`
`D | <actividad de desarrollo/produccion>`
`O | <actividad de oportunidad/operacion puntual>`

Ejemplos:
- Padre: `The Circle`
- Hija: `G | Preparar RFI inicial`
- Hija: `D | Controlar discrepancias planta vs detalle en vigas/columnas`

## Protocolo anti-duplicados
Antes de crear una actividad global:
1. Consultar la base global `ACTIVIDADES`.
2. Buscar o crear la fila padre del proyecto/frente por `Actividad` y `Empresa`.
3. Buscar la actividad hija por `Actividad` y `Parent item`.
4. Si existe, actualizar `Status`, `Date` y `Observación`.
5. Si no existe, crear fila nueva con `Parent item` apuntando al padre.

Para The Circle:
- Buscar/crear padre `The Circle` con `Empresa = GEN+` salvo que el usuario indique otra empresa paraguas.
- Cliente `Ferralia Republica Dominicana` debe ir en `Observación`, no en `Empresa`.

## The Circle - estado creado
El 2026-05-14 se creo en la base global:
- Padre: `The Circle`.
- Page ID padre: `360d8cc4-cfc1-81b7-99e0-e29f4a142aa6`.
- Empresa: `GEN+`.
- Subitems creados:
  - `G | Preparar RFI inicial`.
  - `D | Preparar matriz de avance por bloque y elemento`.
  - `D | Organizar avance preliminar de vigas por zona`.
  - `D | Controlar discrepancias planta vs detalle en vigas/columnas`.
- Verificacion: padre `The Circle` con `SUB_COUNT=4`.

Nota tecnica: al usar PowerShell, la propiedad `Observacion` con tilde puede fallar por codificacion si se envia por nombre. En ese caso usar API/MCP con UTF-8 correcto o usar property id de Notion.

## Cuidado
No usar el cliente como `Empresa` salvo que el usuario lo indique. En proyectos de Fabrizio/GEN+, probablemente `Empresa` sea `GEN+` y el cliente debe ir en `Observación`.
