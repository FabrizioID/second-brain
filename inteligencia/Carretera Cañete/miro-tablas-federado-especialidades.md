# Miro - Tablas de trazabilidad para federado BIM

Uso sugerido en Miro:

- Crear un frame principal: `Carretera Cañete - Trazabilidad BIM para Federado`.
- Crear un frame por especialidad.
- Pegar cada tabla como tabla nativa de Miro o como bloque markdown/documento.
- Semaforo sugerido:
  - Cubierto: verde.
  - Parcial: amarillo.
  - Falta BIM / falta familia: rojo.
  - Revisar sustento: naranja.

## Especialidad: Señalización y Seguridad Vial

| Elemento | Informe / inventario | Familias BIM encontradas | Estado para federado |
|---|---:|---|---|
| Señales informativas | 14 und / 35.41 m2 | `I-31` | Parcial. Faltan `I-18`, `I-2A`, `I-5`, `I-5A`, `I-7`, `I-8` |
| Señales preventivas | 221 und | `P-10B`, `P-16A`, `P-17A`, `P-1A`, `P-1B`, `P-2A`, `P-2B`, `P-31`, `P-33A`, `P-3B`, `P-49`, `P-4A`, `P-4B`, `P-51`, `P-5-1`, `P-5-1A`, `P-5-2A`, `P-5-2B`, `P-56`, `P-7`, `P-9A`, `P-9B` | Parcial. Faltan `P-10`, `P-10A`, `P-16B`, `P-33`, `P-3A`, `P-48`, `P-6` |
| Señales reglamentarias | 12 und | `R-30 KMH` | Cubierto como tipo/familia |
| Postes de kilometraje | 11 und | `HITO KILOMETRICO-AP569-0` a `AP569-17` | Parcial. Hay 18 familias, no calza con cantidad del informe |
| Marcas en pavimento | 2453 m2 | `lineacurvaplazueleta`, `lineaplazueleta`, `PASE PEATONAL` | Parcial. Falta trazar contra metrados/plano |
| Reductores de velocidad | 2 und / 10 m | `REDUCTORES DE VELOCIDAD 5.00 X 4.00 M` | Cubierto como tipo/familia |
| Tachas retroreflectivas | 1736 und | `tacha` | Cubierto como tipo/familia |
| Barreras de seguridad | 2052 m | Familias de barrera con/sin curvatura y postes | Cubierto como tipos. Falta validar correspondencia exacta con longitud/tramos |
| Postes delineadores | 128 und | `POSTES DELINEADORES` | Cubierto como tipo/familia |
| Guardavías | Informe indica que no se consideran | Varias familias de guardavías | Revisar. Posible sobrante o falta de sustento |
| Pase peatonal / zona escolar | Informe indica que no se proyecta pase peatonal/zona escolar | `PASE PEATONAL`, `P-49` | Inconsistente. Revisar sustento |

## Especialidad: Estructuras y Obras de Arte

| Elemento | Informe / inventario | Insumo BIM encontrado | Estado para federado |
|---|---:|---|---|
| Alcantarillas de reemplazo | 61 und | 7 familias `.rfa` + 7 CAD `.dwg` | Parcial. Faltan 54 alcantarillas si se espera modelo por progresiva |
| Alcantarilla eliminada | 1 und | No requiere familia nueva | No aplica modelar, pero debe quedar documentada |
| Alcantarillas nuevas | 0 und | No hay familias nuevas adicionales | Correcto segun informe |
| Muro de sostenimiento | 150 m, de 00+210 a 00+360, H=3.50 m | Memoria y planos DWG/PDF, sin familia/modelo BIM detectado | Falta modelar o justificar fuera del federado |
| Canal de concreto a reponer | 1,306 m | Plano DWG/PDF, sin familia/modelo BIM detectado | Falta modelar o justificar fuera del federado |
| Canal de tierra afectado/reposicion | 1,277 m | Sin familia/modelo BIM detectado | Falta definir si se modela o solo se documenta como afectacion/reposicion |
| Total canales a reponer | 2,583 m | Solo informe/planos, sin modelo BIM detectado | Falta modelo o criterio de exclusion |
| Memorias de calculo de alcantarillas | 5 tipos: 0.40x0.40, 0.60x0.60, 0.80x0.80, 1.00x1.00, 4.00x2.00 | SAP/Excel/PDF | Insumo tecnico existe, no equivale a modelo BIM |
| Memoria de muro | 1 muro H=3.50 m | PDF/XLSM | Insumo tecnico existe, falta BIM |
| Planos de alcantarillas | Si | DWG/PDF | Insumo CAD existe |
| Planos de muros | Si | DWG/PDF | Insumo CAD existe, falta BIM |
| Planos de canal | Si | DWG/PDF | Insumo CAD existe, falta BIM |

## Especialidad: Vialidad, Topografía y Diseño Geométrico

| Elemento | Informe / inventario | Insumo BIM encontrado | Estado para federado |
|---|---|---|---|
| Georreferenciación | `INFORME DE GEORREFERENCIACIÓN`, diario GNSS, líneas base, descripción monográfica y certificados | `PUNTOS GEODESICOS.dwg` | Insumo base existe. Falta validar sistema común en federado |
| Levantamiento topográfico | `INFORME DE TOPOGRAFIA`, puntos, nivelación BMS, poligonal de apoyo, paneles fotográficos | LandXML `PLANTA Y PERFIL.xml` y DWG de puntos geodésicos | Parcial. Hay base geométrica, falta modelo coordinado publicado |
| Fotogrametría / ortomosaico | Informe de procesamiento y `ORTOMOSAICO ROLDAN.ecw` | Maqueta InfraWorks puede usarlo como contexto | Insumo documental/visual existe, no equivale a federado |
| Diseño vial / trazado | `INFORME DE DISEÑO VIAL`, informe de compatibilidad, interferencias de diseño geométrico | LandXML `PLANTA Y PERFIL.xml`; maqueta `ROLDAN.sqlite` | Parcial. Falta corredor/modelo Civil 3D o exportación `NWC/IFC/RVT` |
| Curvas verticales | `SUSTENTO DE CURVAS VERTICALES.xlsx` | No se detectó modelo específico | Insumo de cálculo existe, falta trazabilidad BIM |
| Sobreancho | `SOBRE ANCHO.xlsx` y cálculo de sobreancho en topografía | No se detectó modelo específico | Insumo de cálculo existe, falta parametrizar/modelar |
| Intersecciones | Informe de diseño vial + planos de intersecciones | 22 DWG en `6.00 INTERSECCIONES`, progresivas 0+760 a 10+405 | Parcial. CAD existe, falta convertir/integrar al federado |
| Planta y perfil longitudinal | Planos de planta/perfil en Vol. XIII | LandXML `PLANTA Y PERFIL.xml` | Parcial. Falta validación contra planos y modelo coordinado |
| Secciones transversales | Planos de secciones transversales en Vol. XIII | No se detectó modelo específico de secciones | Falta modelo o criterio de exclusión |
| Diagrama de masas | Plano/carpeta de diagrama de masas en Vol. XIII | No se detectó modelo BIM asociado | Insumo documental, no BIM |

## Especialidad: Hidrología, Hidráulica y Drenaje

| Elemento | Informe / inventario | Insumo BIM encontrado | Estado para federado |
|---|---|---|---|
| Informe HHD | `2.0 INFORME.docx/pdf` | No se detectó modelo HHD independiente | Insumo técnico existe, falta modelo/federado |
| Datos hidrológicos | Anexo 1: datos hidrológicos y estaciones | No se detectó modelo BIM | Insumo de cálculo, no BIM |
| Análisis estadísticos | Estación Cañete y estación Pacarán en XLSX/PDF | No se detectó modelo BIM | Insumo de cálculo, no BIM |
| Inventario vial HHD | Anexo 3: ficha alcantarilla, sectores vulnerables, canales afectados, KMZ y puntos UTM | Familias de 7 alcantarillas + DWG de algunas progresivas | Parcial. Falta cruzar inventario completo contra familias/modelo |
| Obras de drenaje propuestas | `OBRAS DE DRENAJE PROPUESTO - ROLDAN.xlsx` | 7 familias `.rfa` de alcantarillas | Parcial. Debe cruzarse con relación total de OD |
| Diseño hidráulico de alcantarillas pluviales | `DISEÑO HIDRAULICO ALC-PLUVIAL.xlsx/pdf` | Familias de alcantarillas puntuales | Parcial. Falta modelo para todas las OD aplicables |
| Diseño hidráulico de canales | `DISEÑO HIDRAULICO DE CANALES.xlsx` | No se detectó familia/modelo de canales | Falta BIM o justificar fuera de federado |
| Parámetros geomorfológicos | Anexo 4 `PARAMETROS GEOMORFOLOGICOS.xlsx/pdf` | No se detectó modelo BIM | Insumo técnico, no BIM |
| Sectores vulnerables | Anexo 6 análisis de sectores vulnerables | No se detectó modelo BIM | Falta modelar/georreferenciar o documentar exclusión |
| Planos HHD | Anexo 8 planos | Planos PDF/DWG en Vol. XIII drenaje | Insumo CAD/documental existe, falta federado |

## Especialidad: Geología y Geotecnia

| Elemento | Informe / inventario | Insumo BIM encontrado | Estado para federado |
|---|---|---|---|
| Informe GG | `GEOLOGIA Y GEOTECNIA.docx/pdf` + levantamiento de observaciones | No se detectó modelo GG independiente | Insumo técnico existe, falta modelo/federado |
| Geología regional | Plano `Mapa Geología Regional.pdf` | No se detectó modelo BIM | Insumo cartográfico, no BIM |
| Geología local | Planos geológicos locales 01-04 y plano general | No se detectó modelo BIM | Insumo cartográfico, falta integración georreferenciada |
| Geomorfología | `Mapa Geomorfologico.pdf` | No se detectó modelo BIM | Insumo cartográfico, no BIM |
| Investigaciones geotécnicas | `Investigaciones geotecnicas.pdf`, registros de campo y excavaciones | PEB declara modelo 3D de estratos/niveles de cimentación, pero no se detectó archivo | Falta modelo o evidencia de cumplimiento |
| Clasificación de material | `CLASIF. MATERIAL.xlsx/pdf` | `CLASIF. MATERIAL.xlsx` también aparece en informe de modelos | Insumo técnico existe, falta vínculo al modelo |
| Ensayos de laboratorio | Informes de laboratorio SF/CF y capacidad admisible de muro | No se detectó modelo BIM | Insumo técnico, no BIM |
| Capacidad admisible para obras de arte | `CA_RESUMEN OBRAS DE ARTE_ROLDAN` y capacidad de carga OA | Relacionable con alcantarillas/muro, no modelo BIM | Insumo técnico, falta trazabilidad con estructuras modeladas |
| Parámetros geotécnicos | Macizo rocoso y discontinuidades XLS/PDF | No se detectó modelo BIM | Insumo técnico, no BIM |
| Sismicidad | Reporte catálogo sísmico R=100 km y plano sísmico | No se detectó modelo BIM | Insumo técnico, no BIM |

## Especialidad: Suelos, Canteras, Fuentes de Agua y Pavimentos

| Elemento | Informe / inventario | Insumo BIM encontrado | Estado para federado |
|---|---|---|---|
| Estudio de suelos | `Informe de Estudio de Suelos febrero-2026.docx/pdf` | No se detectó modelo BIM de suelos/estratos | Insumo técnico existe, falta modelo o exclusión |
| Canteras | `Informe_Canteras_y_F.A. febrero-2026.docx/pdf` + ensayos cantera Victoria, Roma, Carolina Uno | No se detectó modelo BIM de canteras | PEB declara modelo de ubicación de canteras/MDE, falta evidencia |
| Fuentes de agua | Informe de canteras y fuentes de agua | No se detectó modelo BIM específico | Falta ubicación modelada/georreferenciada o exclusión |
| Diseño de pavimentos | `Informe_Diseño de Pavimento febrero-2026.docx/pdf` | No se detectó modelo BIM de paquete estructural | Insumo técnico existe, falta modelo vial/corredor con capas |
| Respuesta a observaciones | `RESPUESTA A LAS OBSERVACIONES DEL INFORME FINAL 1.docx` | No aplica como modelo | Revisar si modifica criterios de federado |

### Alcantarillas modeladas detectadas

| Progresiva BIM | Coincidencia con informe | Estado |
|---|---|---|
| 1+022 / 1+023 | Si, diferencia de redondeo | Modelada |
| 4+052 | Si | Modelada |
| 4+275 | Si | Modelada |
| 4+379 | Si | Modelada |
| 4+494 | Si | Modelada |
| 4+903 | Si | Modelada |
| 4+996 | Si | Modelada |

## Lectura para el tablero

| Especialidad | Lo cubierto | Brecha principal | Prioridad |
|---|---|---|---|
| Señalización | Tipos base de señales, tachas, barreras, reductores y postes delineadores | Falta trazabilidad por codigo/cantidad/progresiva y faltan familias informativas/preventivas | Alta |
| Estructuras | 7 alcantarillas modeladas y soporte tecnico CAD/calculo | Faltan muros, canales y la mayoria de alcantarillas en BIM | Alta |
| Vialidad / Topografía | LandXML, puntos geodésicos, DWG de intersecciones, InfraWorks y documentación de diseño | Falta corredor/modelo coordinado exportable a federado | Alta |
| Hidrología / Hidráulica / Drenaje | Informe, anexos, relación OD, diseños hidráulicos, canales y sectores vulnerables | Falta modelo HHD completo y cruce contra alcantarillas/canales | Alta |
| Geología / Geotecnia | Informe, planos, ensayos, clasificación de material, sismicidad y capacidad admisible | Falta modelo 3D de estratos/geotecnia declarado por PEB | Media-Alta |
| Suelos / Canteras / Pavimentos | Informes de suelos, canteras/fuentes de agua y pavimentos | Falta modelo de canteras/MDE y paquete de pavimento/corredor | Media-Alta |
