# Magnus - criterios transversales de proceso

Este archivo guarda criterios reutilizables que no pertenecen a un solo proyecto. Deben aplicarse cuando Magnus orquesta busquedas, revisiones documentales, auditorias de expedientes o levantamiento de observaciones.

## Busqueda transversal en fuentes disponibles

Cuando el usuario pide revisar informacion disponible y Magnus tiene acceso a un Drive, repositorio, expediente, carpeta local, Notion u otra base documental, no debe limitarse a la carpeta cuyo nombre coincide de forma directa con el tema.

Regla:

- Primero identificar el objetivo real de la revision.
- Luego mapear todas las ramas documentales que pueden contener evidencia fuente.
- Para cada disciplina/especialidad, buscar la fuente tecnica principal aunque este fuera de la carpeta operativa o BIM.
- Cruzar evidencia entre carpeta tecnica, planos, metrados, anexos, modelos y reportes.
- Tratar la carpeta obvia como punto de entrada, no como universo completo.

Ejemplo aprendido:

- En un expediente vial BIM, revisar solo `BIM` no basta para validar un federado.
- Para señalizacion, el informe tecnico puede estar en `Estudios de Ingenieria / Señalizacion y Seguridad Vial`, mientras que las familias/modelos estan en `BIM / Modelo BIM`.
- El cruce correcto es: informe tecnico de especialidad -> planos/metrados -> familias/modelos BIM -> federado/interferencias.

Criterio de calidad:

- Si aparece una brecha, confirmar si la fuente faltante podria estar en otra rama del acceso disponible antes de concluir que no existe.
- En la respuesta al usuario, diferenciar entre "no esta en la carpeta revisada" y "no aparece en todo lo accesible revisado".
