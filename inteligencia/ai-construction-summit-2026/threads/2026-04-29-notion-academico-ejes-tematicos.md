---
slug: 2026-04-29-notion-academico-ejes-tematicos
proyecto: AI Construction Summit 2026
fecha: 2026-04-29
tipo: sintesis
---

## Objetivo del hilo

Documentar la estructura real de Notion del AI Construction Summit 2026 relacionada con el area Academico y dejar registrada la forma correcta de guardar entregables academicos gestionables.

## Resumen ejecutivo

- Se escaneo la pagina raiz del Summit en Notion y se ubico que el contenido academico vive dentro de la base de equipos, no como seccion suelta de portada.
- Se creo el entregable **Ejes tematicos finales del Summit** en la BD de entregables por area y se vinculo al equipo **Academico (Contenido y Programa)**.
- Se corrigio el formato de los ejes: deben vivir en una base de datos inline editable, no en una tabla estatica.

## Estado del proyecto en este momento

- El area Academico ya tiene una ruta clara en Notion para documentar planes, propuestas y ejes.
- Existe un entregable academico nuevo con los 7 ejes tematicos finales y una matriz editable.
- Para futuras sesiones, cualquier documentacion academica del Summit debe respetar esta estructura.

## Avances detectados

- Pagina raiz del Summit identificada: `AI CONSTRUCTION SUMMIT 2026` (`31a3460f1c3680e8a08ff2ca031cef35`).
- Pagina de equipo identificada: `Academico (Contenido y Programa)` (`34a3460f1c368032b4c4c2ba7df82be2`).
- Data source de equipos: `BD - Equipos de trabajo Summit` (`collection://34a3460f-1c36-8024-ab56-000ba60e3e41`).
- Data source de entregables por area: `BD - Entregables por area Summit` (`collection://34a3460f-1c36-80c5-b68e-000b7252130b`).
- Entregables academicos previos: `Plan del area academica` y `Generacion de primera propuesta`.
- Nuevo entregable creado: `Ejes tematicos finales del Summit` (`3513460f1c368132b52dc374b462668f`).
- Base inline creada dentro del entregable: `Matriz de ejes tematicos` (`5226ae0f83314027851258674c71b1fd`, data source `collection://b0a596da-a900-47cb-8358-4077d8dea35e`).

## Problemas o bloqueos

- La primera version documento los ejes como tabla estatica; el usuario corrigio que debian estar en una base de datos inline.
- Al crear la base y una vista vinculada, aparecieron dos tablas visibles; se elimino la vista duplicada y quedo una sola base inline.
- Notion protegio child databases durante un replace; para limpiar duplicados hay que preservar o confirmar explicitamente bloques hijos.

## Decisiones tomadas

- Los ejes tematicos finales deben documentarse como entregable academico al mismo nivel que `Plan del area academica`, no como bloque suelto en la portada raiz.
- La informacion academica gestionable debe ir en bases inline editables cuando requiere orden, filtros, estados, audiencia, relevancia o futuro uso para programa.
- La matriz de ejes debe mantener columnas minimas: `Orden`, `Eje tematico`, `Descripcion`, `Subtemas`, `Relevancia`, `Audiencia principal`, `Estado`.

## Soluciones o propuestas

- Para nuevos entregables academicos, crear filas en `BD - Entregables por area Summit` y relacionarlas con `Academico (Contenido y Programa)`.
- Dentro de cada entregable, usar una mezcla de breve contexto textual + base inline editable si el contenido sera gestionado por el equipo.
- Evitar duplicar bases/vistas dentro de la misma pagina; verificar con `notion_fetch` despues de crear bases o vistas.

## Patrones detectados

- `avance_sin_cierre`: una tabla visual parecia suficiente, pero no dejaba el entregable listo para gestion real.
- `repeticion_de_error`: si no se escanea la estructura de Notion, se puede documentar en la capa incorrecta.
- `oportunidad_no_aprovechada`: convertir contenido estrategico en BD inline permite que el equipo lo use para programa, responsables y seguimiento.

## Oportunidades detectadas

- Usar Notion como matriz operativa del Summit, no solo como repositorio de texto.
- Convertir ejes academicos en base para programa, speakers, sponsors y tracks.
- Crear vistas futuras por audiencia, relevancia, estado o bloque tematico sin reescribir el contenido.

## Aprendizajes reutilizables

- Antes de documentar algo del Summit en Notion, primero ubicar si pertenece a una area/equipo, entregable, base maestra o pagina de referencia.
- Si el usuario dice "en el area Academico", buscar dentro de `BD - Equipos de trabajo Summit` y luego dentro de los entregables relacionados.
- Para contenido que se editara o evaluara, preferir base inline sobre tabla estatica.
- Despues de crear databases o linked views en Notion, hacer un fetch final para detectar duplicados visibles.

## Preguntas abiertas

- Si los ejes finales deben tener despues columnas adicionales como sponsor objetivo, speaker potencial, referencias externas, prioridad comercial o formato de sesion.
- Si la matriz de ejes sera la base directa del programa academico o solo una matriz previa de decision.

## Proximos pasos

- Si se agregan nuevos contenidos academicos, usar el entregable o crear nuevos entregables en la misma BD segun granularidad.
- Ampliar la matriz de ejes si el equipo necesita pasar de ejes a agenda, ponentes o tracks.
- Mantener esta ruta como contexto obligatorio en futuros chats sobre documentacion del Summit.

## Tags tematicos

- summit
- notion
- academico
- ejes-tematicos
- entregables
- base-de-datos
- documentacion

## Tags de patron

- avance_sin_cierre
- repeticion_de_error
- oportunidad_no_aprovechada

## Tags de senal

- aprendizaje
- decision
- oportunidad
- insight

## Relaciones internas del hilo

- Estructura real de Notion -> define destino correcto -> evita documentar en portada o pagina equivocada.
- Ejes tematicos -> entregable academico -> matriz editable -> base para programa y comunicacion.
- Tabla estatica -> baja operatividad -> base inline -> mejor gestion por equipo.

## Senales exportables a otros proyectos

- En Notion, si una lista sera gestionada por personas, usar base de datos antes que tabla estatica.
- Antes de documentar en un workspace estructurado, mapear la jerarquia y escribir en la capa operativa correcta.
