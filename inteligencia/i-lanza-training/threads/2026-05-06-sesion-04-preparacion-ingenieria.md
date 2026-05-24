---
slug: 2026-05-06-sesion-04-preparacion-ingenieria
proyecto: I Lanza Training
fecha: 2026-05-06
tipo: estrategia
---

## Objetivo del hilo
Preparar la Sesion 04 de i-Lanza orientada a IA aplicada a ingenieria, con ejercicios de revision de memorias de calculo, generacion de informes tecnicos y automatizacion de requerimientos/materiales con n8n.

## Resumen ejecutivo
- Se definio una agenda de Sesion 04 enfocada en ingenieria: revisar, documentar y automatizar.
- Se creo el paquete local `i_lanza_sesion04_ingenieria/` con agenda, guia, checklist, insumos, prompts y blueprint n8n.
- El enfoque conserva validacion humana: la IA alerta, estructura y acelera, pero no aprueba calculos.

## Estado del proyecto en este momento
- La Sesion 03 ya cubrio GPTs personalizados, actas, pliegos/TDR e informes.
- La Sesion 04 se reorienta a casos de ingenieria mas especificos, evitando depender de Outlook/Copilot por limitaciones de cuenta/permisos.
- El material de taller ya esta generado localmente.

## Avances detectados
- Agenda resumida para WhatsApp creada en `i_lanza_sesion04_ingenieria/00_agenda_wsp.md`.
- Guia de facilitador creada en `00_guia_facilitador.md`.
- Checklist de preparacion creado en `00_checklist_preparacion.md`.
- Ejercicio 01 creado: Revisor de Memorias de Calculo con Normativa usando GPT Assistant personalizado.
- Ejercicio 02 creado: Generador de Informe Tecnico de Diseno usando GPT Assistant personalizado.
- Ejercicio 03 creado: Automatizacion de Requerimientos y Materiales con n8n.
- Se incluyeron insumos demo: memoria de calculo, normativa ficticia, plantilla de revision, plantilla de informe, requerimiento, cotizacion y guia de recepcion.
- 2026-05-16: Se retoma la sesion para generar una slide de Prompt Engineering para imagenes usando la plantilla institucional de especializacion en automatizacion/n8n.
- 2026-05-16: Se solicita una segunda slide comparativa sobre buen prompt vs mal prompt para imagenes.
- 2026-05-16: Se solicita una tercera slide sobre la importancia de comunicarse bien con la IA mediante prompt engineering.
- 2026-05-16: Se solicita una slide con ejemplo concreto de prompt mal hecho para imagenes y prompt bueno para imagenes.
- 2026-05-16: Se solicita una slide de prompt engineering para developers, enfocada como especificacion tecnica para IA.

## Problemas o bloqueos
- Si n8n no esta listo en vivo, se debe ejecutar el flujo manualmente con ChatGPT como plan B.
- La normativa incluida es demo y debe presentarse como ficticia para capacitacion.
- El flujo n8n incluye blueprint y JSON minimo, pero la conexion final con OpenAI/Sheets/correo depende de credenciales y entorno disponibles.

## Decisiones tomadas
- No centrar la Sesion 04 en Outlook/Copilot por incertidumbre de licencias y permisos.
- Usar GPT Assistant personalizado para ejercicios 01 y 02.
- Usar n8n para ejercicio 03.
- Separar revision tecnica de generacion de informe: primero alertas, luego documento.

## Soluciones o propuestas
- Crear dos GPTs antes de la sesion:
  - `Revisor Tecnico de Memorias de Calculo`;
  - `Generador de Informes Tecnicos de Diseno`.
- Montar en n8n un workflow simple con Manual Trigger, Set de entradas, OpenAI/Chat Model y salida a tabla/correo.
- Mantener plan B manual con prompts si falla n8n.

## Patrones detectados
- Para ingenieria, los casos ganan credibilidad cuando parten de insumos tecnicos concretos y terminan en artefactos revisables.
- La automatizacion debe presentarse como control de informacion entre areas, no como reemplazo del criterio tecnico.

## Oportunidades detectadas
- Convertir el Revisor de Memorias en GPT reutilizable para i-Lanza.
- Convertir el Generador de Informes en plantilla corporativa asistida.
- Convertir el flujo n8n de materiales en piloto operativo para oficina tecnica, compras, almacen y obra.

## Aprendizajes reutilizables
- En capacitaciones tecnicas, conviene separar "alertar/revisar" de "redactar/informar" para evitar que un informe bien escrito oculte riesgos.
- Un flujo de materiales es valioso aunque no exista foto de obra; puede iniciar desde PDF, cotizacion, guia, Excel o correo.

## Preguntas abiertas
- Si se usara n8n cloud/local y que credenciales estaran listas.
- Si se reemplazara la normativa demo por normativa real de i-Lanza antes de dictar.
- Si se quiere generar un dashboard HTML de apoyo para navegar los ejercicios en vivo.

## Proximos pasos
- Crear los dos GPT Assistant personalizados y cargar archivos.
- Probar prompts de ejercicios 01 y 02 antes de la sesion.
- Montar workflow n8n demo o usar plan manual.
- Definir si se compartira el paquete completo o solo outputs durante la capacitacion.

## Tags tematicos
- i-lanza
- training
- sesion-04
- ingenieria
- memorias-de-calculo
- normativa
- informes-tecnicos
- n8n
- materiales
- compras
- almacen

## Tags de patron
- continuidad_de_proyecto
- training_orientado_a_entregables
- adopcion_por_artefactos
- validacion_humana
- automatizacion_operativa

## Tags de senal
- aprendizaje
- oportunidad
- materiales_listos
- decision
- pendiente_validacion

## Relaciones internas del hilo
- Sesion 03 genero base de GPTs personalizados -> Sesion 04 los lleva a memorias e informes.
- Limitacion Outlook/Copilot -> se eligio n8n y flujos no dependientes de correo corporativo.
- Necesidad de ingenieria -> se priorizaron calculos, normativa, informes y materiales.

## Senales exportables a otros proyectos
- Si una demo depende de permisos corporativos inciertos, usar triggers neutrales como webhook/manual/formulario.
- Para IA en ingenieria, explicitar siempre que la herramienta produce borradores, alertas y trazabilidad, no aprobaciones.
