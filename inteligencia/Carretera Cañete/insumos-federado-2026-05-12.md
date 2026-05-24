# Insumos disponibles para modelo federado - Carretera Cañete

Fecha de corte: 2026-05-12

## Lectura ejecutiva

El expediente BIM contiene insumos parciales suficientes para preparar una estrategia de federación, pero en la carpeta revisada no aparece un federado publicado ni archivos de coordinación en formatos `RVT`, `IFC`, `NWC` o `NWD`.

Lo disponible está concentrado en:

- Familias y objetos Revit/FBX de señalización.
- Familias y CAD de alcantarillas.
- DWG de intersecciones y puntos geodésicos.
- LandXML de planta y perfil/superficie.
- Maqueta InfraWorks con base `.sqlite` y carpeta `.files`.
- PEB con estrategia BIM declarada.
- Informe de compatibilidad socioambiental.

## Carpeta BIM revisada

Drive BIM: `16 BIM`

Subcarpetas principales:

- `1.00 INFORME DE MODELOS`
- `2.00 INFORME DE INTERFERENCIAS`
- `3.00 INFORME DE COMPATIBIILIDAD`
- `4.00 VIDEO`
- `5.00 MODELO BIM`
- `6.00 ACTUALIZACION BEP`
- `7.00 SIMULACION BIM 4D`
- `8.00 MAQUETA INFRAWORK`

## Hallazgos por tipo de insumo

### Modelo BIM

La carpeta `5.00 MODELO BIM` tiene 216 elementos escaneados. Por archivos:

- `2.00 ALCANTARILLAS`: 7 familias `.rfa`, 7 CAD `.dwg`, 1 `.bak`.
- `3.00 SEÑALIZACIONES`: 65 familias `.rfa` y 65 exportaciones `.fbx`.
- `4.00 DATOS XML - SUPERFIE`: 1 `PLANTA Y PERFIL.xml` de aprox. 326 MB.
- `5.00 PUNTOS GEODESICOS`: 1 `PUNTOS GEODESICOS.dwg`.
- `6.00 INTERSECCIONES`: 22 archivos `.dwg`.

No se encontró una carpeta `1.00` dentro de `5.00 MODELO BIM` en el primer nivel revisado.

### Señalización

Sí hay insumo modelado de señalización. Incluye:

- Preventivas: I-31, P-10B, P-16A, P-17A, P-1A, P-1B, P-2A, P-2B, P-31, P-33A, P-34, P-3B, P-49, P-4A, P-4B, P-5-1, P-5-1A, P-5-2A, P-5-2B, P-51, P-53, P-56, P-7, P-9A, P-9B.
- Reglamentarias: R-30.
- Postes kilométricos: AP569-0 a AP569-17.
- Marcas en pavimento: líneas, pase peatonal.
- Reductores de velocidad.
- Tachas.
- Barreras de seguridad.
- Guardavías.
- Postes delineadores.

### Alcantarillas

Hay familias y CAD por progresiva:

- 1+022
- 4+052
- 4+275
- 4+379
- 4+494
- 4+903
- 4+996

### Intersecciones

Hay 22 DWG, cubriendo progresivas desde 0+760 hasta 10+405, con algunos archivos agrupando varias intersecciones.

### InfraWorks

La carpeta `8.00 MAQUETA INFRAWORK` contiene:

- `ROLDAN.sqlite` de aprox. 444 MB.
- `ROLDAN.files` con estructura de modelo InfraWorks.
- Carpeta `SUPERADO` con `CERRO AZUL - CAÑETE.sqlite` de aprox. 434 MB y su carpeta `.files`.

La estructura interna incluye clases InfraWorks como `ROADS`, `INTERSECTIONS`, `CULVERTS`, `BARRIERS`, `BRIDGES`, `TERRAIN_SURFACES`, `TERRAIN_TEXTURES`, `DATA_SOURCES`, `ALIGNMENT_*`, entre otras. Esto sirve como maqueta de contexto/visualización y posible base de revisión, pero no equivale por sí sola al federado de coordinación.

### Informe de modelos

`1.00 INFORME DE MODELOS` contiene anexos, no un informe narrativo directo en el nivel revisado:

- Inventario vial en XLSX.
- Clasificación de materiales en PDF/XLSX.
- Sustento de metrados en HTML/XLS.

### Informe de interferencias

`2.00 INFORME DE INTERFERENCIAS` aparece vacío en el escaneo por Drive API. Esto es crítico: el PEB exige reporte de interferencias y modelo de coordinación, pero el expediente revisado no muestra esa evidencia cargada en esa carpeta.

### Informe de compatibilidad

El documento revisado es de compatibilidad entre ingeniería y socioambiental. Confirma partidas/alcances como:

- Movimiento de tierras.
- Pavimento.
- Obras de arte y drenaje: cunetas, alcantarillas.
- Transporte de material.
- Señalización y seguridad vial.
- Canteras, DME, patio de máquinas, planta de asfalto y planta de concreto con coordenadas UTM.

Incluye un DWG de patio de máquinas dentro de la carpeta de compatibilidad.

## Lo que el PEB declara para federación

El PEB indica:

- El modelo federado debe alojarse en el Entorno Común de Datos.
- Debe ser un archivo único de coordinación y visualización 3D basado en integración de modelos, sin fusionar archivos.
- Debe servir para coordinación, visualización y detección de interferencias.
- Debe estar georreferenciado en UTM WGS84.
- La detección de interferencias se haría con Navisworks Manage.
- Los formatos/software declarados incluyen Revit 2024, Civil 3D 2024, InfraWorks 2024 y Navisworks 2024.
- Para coordinación e interferencias se declara formato `NWC`.

## Brecha principal

El expediente revisado muestra insumos para federar, pero no muestra el federado como entregable. Tampoco se encontró `NWC`, `NWD`, `IFC`, `RVT` ni archivos nativos de Civil 3D separados del DWG. Esto implica que el alcance de levantamiento debería incluir, como mínimo:

- Solicitar o reconstruir el modelo de coordinación/federado.
- Validar georreferenciación común entre XML/DWG/RFA/InfraWorks.
- Cargar o exportar los modelos necesarios a `NWC`/`NWD` o formato equivalente de coordinación.
- Incorporar señalización al federado, porque sí hay familias/FBX disponibles y el PEB la contempla como disciplina.
- Generar o completar reporte de interferencias, porque la carpeta correspondiente está vacía.
- Trazar qué insumos son modelos reales, qué son familias sueltas y qué son solo documentación/CAD.

## Cruce inventario vs familias/codigos

Revision adicional del 2026-05-12:

- Los XLSX de inventario del `1.00 INFORME DE MODELOS` no listan literalmente los codigos de familias encontrados en `5.00 MODELO BIM`.
- Se contrastaron 72 codigos/nombres unicos de familias `.rfa` contra los inventarios XLSX descargados; coincidencias literales encontradas: 0.
- El `FORMATO N 06 - SEÑALIZACION` inventaria 21 elementos existentes/fotograficos: 10 postes kilometricos, 6 señales preventivas, 3 informativas, 1 reglamentaria y 1 poste sin cartel.
- El modelo BIM contiene 65 familias `.rfa` de señalizacion: 25 preventivas, 1 reglamentaria, 18 postes kilometricos, 3 marcas en pavimento, 1 reductor, 1 tacha, 5 barreras, 10 guardavias y 1 poste delineador.
- El informe de compatibilidad/memoria de metrados trabaja con cantidades de partidas, no con codigos de familias: señales informativas 35.41 m2, preventivas 221 u, reglamentarias 12 u, postes de kilometraje 11 u, marcas en pavimento 2,453 m2, reductores 2 u, tachas 1,736 u, barrera de seguridad 2,052 m y postes delineadores 128 u.

Conclusion: el inventario sirve para condiciones existentes y metrados por partida, pero no valida por si solo la cantidad/codigo de familias BIM. Para levantar el federado hace falta una matriz propia que relacione partida/metrado -> familia/tipo BIM -> ubicacion/progresiva -> evidencia en modelo.

## Cruce con informe especifico de señalizacion

Fuente revisada: `INFORME DE SEÑALIZACIÓN.docx` (`1ggIRKySCYYeOHgVdJDFdcjm3EbVJI36x`), descargado localmente como `drive_scan/docs/INFORME_DE_SENALIZACION.docx`.

Este informe si es la fuente correcta para contrastar señalizacion proyectada. Contiene resumen general:

- Señales informativas: 14 und / 35.41 m2.
- Señales preventivas: 221 und.
- Señales reglamentarias: 12 und.
- Postes de kilometraje: 11 und.
- Marcas en el pavimento: 2453.00 m2.
- Reductores de velocidad: 2 und / 10.00 m.
- Tachas retroreflectivas: 1736 und.
- Barreras de seguridad: 2052.00 m.
- Postes delineadores: 128 und.

Comparacion de codigos:

- Codigos detectados en el informe: 37.
- Familias RFA con codigo en Drive: 26.
- Codigos que aparecen en informe pero no tienen familia RFA detectada: `I-18`, `I-2A`, `I-5`, `I-5A`, `I-7`, `I-8`, `P-10`, `P-10A`, `P-16B`, `P-33`, `P-3A`, `P-48`, `P-6`.
- Familias RFA que aparecen en Drive pero no se detectaron como codigo en el informe: `P-34`, `P-53`.

Lectura: la carpeta de familias no coincide al 100% con el informe especifico de señalizacion. Hay familias suficientes para una parte importante del set, pero faltan familias/codigos usados o mencionados en el informe, y existen familias que no se justifican claramente con ese informe. Esto debe tratarse como observacion BIM para el federado y para fichas tecnicas.

## Archivos locales de apoyo generados

- `inteligencia/Carretera Cañete/drive_scan/BIM_ROOT.csv`
- `inteligencia/Carretera Cañete/drive_scan/MODELO_BIM.csv`
- `inteligencia/Carretera Cañete/drive_scan/INFORME_MODELOS.csv`
- `inteligencia/Carretera Cañete/drive_scan/COMPATIBILIDAD.csv`
- `inteligencia/Carretera Cañete/drive_scan/INFRAWORKS.csv`
- `inteligencia/Carretera Cañete/drive_scan/docs/PLAN_DE_EJECUCION_BIM.txt`
- `inteligencia/Carretera Cañete/drive_scan/docs/INFORME_DE_COMPATIBILIDAD.txt`
