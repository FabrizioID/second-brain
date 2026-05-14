# Notion Global Activities Sync

## Regla
Toda actividad creada o actualizada en una base `ACTIVIDADES` de proyecto Notion debe sincronizarse tambien con el status general de trabajo.

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

## Mapeo recomendado
- Actividad de proyecto -> `Actividad` global.
- `% Avance` del proyecto -> `Status` numerico global.
- Pendiente/bloqueado/en proceso sin avance -> `0`.
- Listo/cerrado -> `100`.
- Organizacion paraguas -> `Empresa`.
- Proyecto, cliente, bloque, entregable y origen -> `Observación`.
- Fecha limite del proyecto, si existe -> `Date`.

## Convencion de nombre
Usar un prefijo identificable para evitar duplicados:

`<Proyecto> | <Actividad>`

Ejemplos:
- `The Circle | Preparar RFI inicial`
- `The Circle | Controlar discrepancias planta vs detalle en vigas/columnas`

## Protocolo anti-duplicados
Antes de crear una fila global:
1. Consultar la base global `ACTIVIDADES`.
2. Buscar coincidencia por `Actividad`.
3. Si existe, actualizar `Status`, `Date` y `Observación`.
4. Si no existe, crear fila nueva.

## Cuidado
No usar el cliente como `Empresa` salvo que el usuario lo indique. En proyectos de Fabrizio/GEN+, probablemente `Empresa` sea `GEN+` y el cliente debe ir en `Observación`.
