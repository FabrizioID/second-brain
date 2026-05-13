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

## Bases internas minimas
- `ACTIVIDADES`
- `REUNIONES`
- `DOCUMENTOS`
- `CONTACTOS CLIENTE`

Crear bases inline reales, no linked views sueltas.

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
Mantener pocas vistas:
- `Tabla General`
- `Por Estado`
- `Por Tipo`

No agregar calendario salvo que el usuario lo pida o haya fechas operativas reales que deban gestionarse.

## REUNIONES
- `Tabla General`
- `Calendario` si se usan fechas de reunion.

## CONTACTOS CLIENTE
- `Tabla General`
- `Por Tipo` si hay varias categorias de contacto.

## Control adicional
Si el proyecto necesita una base propia, crearla solo cuando aporte control operativo real. Ejemplo para The Circle:
- `CONTROL POR BLOQUE` con `Bloque`, `Zona/Nivel`, `Prioridad`, `Estado`, `Notas`.
- Vistas maximas recomendadas: `Tabla General`, `Por Estado`, `Prioridad`.

## Regla de verificacion obligatoria
Despues de crear/configurar:
- Verificar conteo de filas por base.
- Verificar nombres de vistas por base.
- Verificar que `Vista Filtrada` tenga filtro real, no solo el nombre.
- Verificar que la tabla `Status` este agrupada por `Entregable`.
- Reportar limitaciones si la API no permite replicar algo.

## Caso The Circle - criterio aprendido
Para proyectos de croquis/despiece de acero:
- No asumir que se recibira cartilla final si el usuario dice plantillas.
- Si el usuario dice que "nos pasaran plantillas", documentar como:
  - `Plantilla de planilla para Graphico`.
  - `Plantilla RFI`.
- Graphico debe tratarse como flujo/importacion de informacion, no como documento final por defecto.
