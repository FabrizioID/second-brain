# Notion Engineering Project Template Criteria

## Patron canonico tipo PUENTE TINGO

Usar este criterio cuando el usuario pida crear un proyecto tecnico/de ingenieria en Notion de Fabrizio y mencione que debe quedar como plantilla/proyecto listo.

## Base raiz
- Crear pagina dentro de la base `PROYECTOS` de Fabrizio.
- Usar propiedades compatibles de la base raiz: `Name`, `Status`, `Fecha de Inicio`, `Fecha de Fin`, `Cliente`, `Tipo de Proyecto`.
- No copiar contenido de PUENTE TINGO; solo replicar la logica estructural.

## Estructura superior recomendada
- `DESCRIPCION`
- `ACCESOS` si hay links reales o placeholders claros.
- `INFORMACION`
- Toggles/secciones operativas solo si aportan al proyecto.
- Divisor antes de bases internas.

No agregar bloques visibles de criterios tecnicos, alertas o reglas del agente debajo de las bases si no existen en la plantilla o si el usuario no los pidio explicitamente. Esos criterios deben vivir en `ACTIVIDADES`, `DOCUMENTOS`, `REUNIONES` o memoria interna, no como secciones sueltas que deformen la plantilla.

## Bases internas
No asumir bases internas minimas por defecto.

Crear solo las bases que pertenecen a la plantilla exacta o que el usuario confirma explicitamente. Si el usuario pide replicar una plantilla, primero verificar visualmente/por API que bases existen y cuales corresponden.

Para The Circle, no correspondian `DOCUMENTOS`, `CONTACTOS CLIENTE` ni `CONTROL POR BLOQUE`; fueron archivadas de la pagina.

Cuando si corresponda crear una base, crearla como inline real, no como linked view suelta.

## ACTIVIDADES - Propiedades
Adaptar nombres al proyecto, pero respetar esta logica:
- `Name` title.
- `Entregable` select.
- `Status` select.
- `% Avance` number/percent.
- `Fecha Limite` date.
- `Observacion` rich_text.
- Propiedades especificas del proyecto, por ejemplo `Bloque`, `Elemento`, `Disciplina`, `Zona`, etc.

## ACTIVIDADES - Vistas canonicas
Mantener 3 vistas, como PUENTE TINGO:
- `Vista Filtrada`: board agrupado por `Status`, con filtro real de trabajo activo.
  - Filtro base recomendado: `Status` no es `Listo`.
  - Ocultar grupos vacios.
- `Original`: board agrupado por `Status`, sin filtro restrictivo.
- `Status`: tabla agrupada por `Entregable`.

No crear vistas extra como `Por Entregable` si la necesidad es agrupar la tabla general; configurar la vista `Status` o tabla equivalente con `group_by Entregable`.

## DOCUMENTOS
Crear solo si la plantilla/proyecto lo requiere. Si se crea, mantener pocas vistas:
- `Tabla General`
- `Por Estado`
- `Por Tipo`

No agregar calendario salvo que el usuario lo pida o haya fechas operativas reales que deban gestionarse.

## REUNIONES
- `Tabla General`
- `Calendario` si se usan fechas de reunion.

## CONTACTOS CLIENTE
Crear solo si la plantilla/proyecto lo requiere.
- `Tabla General`
- `Por Tipo` si hay varias categorias de contacto.

## Control adicional
No crear bases adicionales por defecto. Si el proyecto necesita una base propia, crearla solo con confirmacion explicita del usuario o cuando sea parte de la plantilla destino. En la plantilla tipo PUENTE TINGO no corresponde agregar `CONTROL POR BLOQUE` por defecto.

Si se necesita control por bloques, modelarlo primero dentro de `ACTIVIDADES` con propiedades como `Bloque`, `Elemento`, `Entregable`, `Status` y `% Avance`.

## Regla de verificacion obligatoria
Despues de crear/configurar:
- Verificar conteo de filas por base.
- Verificar nombres de vistas por base.
- Verificar que `Vista Filtrada` tenga filtro real, no solo el nombre.
- Verificar que la tabla `Status` este agrupada por `Entregable`.
- Reportar limitaciones si la API no permite replicar algo.

## Sincronizacion global de actividades
Cuando se cree, actualice o cambie estado de una actividad dentro de la base `ACTIVIDADES` de un proyecto Notion, tambien se debe reflejar en el status general de trabajo.

Destino global:
- Pagina: `TO-DO LIST`
- URL: https://www.notion.so/TO-DO-LIST-e2066553a8494738976450204e36efd7
- Page ID: `e2066553-a849-4738-9764-50204e36efd7`
- Subpagina de trabajo: `T.TRABAJO (8 hr: 09:00 - 17:00)`
- Work page ID: `241d8cc4-cfc1-80e7-bce2-f01e6a14c7f4`
- Base global: `ACTIVIDADES`
- Database ID: `2dcd8cc4-cfc1-806c-bda6-f9c4862a9cfd`
- Data source ID: `2dcd8cc4-cfc1-8121-a268-000b4f55c021`

Propiedades de la base global:
- `Actividad` title.
- `Status` number.
- `Empresa` rich_text.
- `Date` date.
- `Observación` rich_text.
- `Checkbox` checkbox.
- `Parent item` relation.
- `Sub-item` relation.

Regla de sincronizacion:
- No basta actualizar solo la base `ACTIVIDADES` del proyecto.
- Crear o actualizar una fila espejo en la base global `TO-DO LIST > trabajo > ACTIVIDADES`.
- Usar un nombre identificable que incluya proyecto y actividad, por ejemplo `The Circle | Preparar RFI inicial`.
- Mapear avance del proyecto a `Status` numerico global:
  - pendiente/bloqueado/en proceso sin avance claro -> `0`.
  - `% Avance` disponible -> usar ese porcentaje como numero.
  - listo/cerrado -> `100`.
- Usar `Empresa` para la organizacion paraguas correspondiente, no para el cliente si no corresponde.
- Guardar cliente/proyecto/contexto en `Observación`, por ejemplo `Proyecto: Edificio The Circle; Cliente: Ferralia Republica Dominicana; Fuente: ACTIVIDADES del proyecto`.
- Al actualizar una actividad existente, buscar primero por `Actividad` y/o convencion de nombre para evitar duplicados.
- Si no se puede determinar empresa, fecha o mapeo exacto, no inventar: crear la fila con observacion clara o pedir confirmacion.

## Caso The Circle - criterio aprendido
Para proyectos de croquis/despiece de acero:
- No asumir que se recibira cartilla final si el usuario dice plantillas.
- Si el usuario dice que "nos pasaran plantillas", documentar como:
  - `Plantilla de planilla para Graphico`.
  - `Plantilla RFI`.
- Graphico debe tratarse como flujo/importacion de informacion, no como documento final por defecto.
- No agregar base `CONTROL POR BLOQUE` ni bloque visible `CRITERIO TECNICO` en la pagina si se esta respetando plantilla tipo Tingo.
- El criterio de discrepancia planta-detalle en vigas/columnas debe registrarse como actividad/RFI y memoria, no como seccion suelta en la pagina principal.
- No crear `DOCUMENTOS` ni `CONTACTOS CLIENTE` por defecto para The Circle; no correspondian a la plantilla aplicada y deben omitirse salvo confirmacion explicita.
