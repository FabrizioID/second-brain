---
slug: 2026-05-02-video-script-generator-skill-build
proyecto: aecode
fecha: 2026-05-02
tipo: estrategia
---

## Objetivo del hilo
Diseñar, construir e iterar la skill `video-script-generator` para el Escaid Setup (Claude Code), más su reporte visual HTML de documentación con fondo animado de red social y mascota holográfica.

## Resumen ejecutivo
- La skill fue construida completa: 2 tiempos inamovibles, 3 guiones × 5 hooks, 7 frameworks, 4 formatos, 9 criterios virales, ficha de validación obligatoria, protocolo de inyección de audiencia.
- El reporte HTML se iteró múltiples veces hasta lograr: logos reales de plataformas sociales (Path2D con SVG paths de Simple Icons), secciones semi-transparentes con backdrop-filter, y mascota holográfica en Three.js (Maui-style, shader GLSL cyan/azul).
- Se definió un principio de diseño clave: el fondo animado nunca debe ser tapado bruscamente por secciones — semi-transparente, muta con scroll, o contraste total.

## Estado del proyecto en este momento
- Skill `video-script-generator` creada y funcional en `C:\Users\USUARIO\.claude\skills\video-script-generator\SKILL.md`
- HTML de documentación en `C:\Users\USUARIO\Desktop\GEN+ TEMP\Machine Learning\video-script-generator-docs.html` — versión iterable, pendiente mejorar secciones internas
- Pendiente: skill `audience-aec` con contexto específico de AECODE (BIM, Civil 3D, Revit, audiencia 25-35)
- Pendiente: mejorar secciones del HTML (agregar nuevas secciones que no tapen el fondo)

## Avances detectados
- Knowledge base completa absorbida: 1000 Viral Hooks PDF (7 categorías), 7 frameworks de marketing, 4 formatos de video, sistema de 3 capas por hook, 9 criterios virales, reglas de lenguaje
- Skill construida con arquitectura de dos tiempos (interpret+validate → generate) — checkpoint inamovible
- Logos reales de plataformas sociales renderizados con `Path2D` usando SVG paths oficiales de Simple Icons — no dibujados a mano
- Principio de fondo/secciones: guardado en memoria del proyecto

## Problemas o bloqueos
- Primer intento de mascota 3D (hook) resultó caricaturesco — requirió rediseño con shader GLSL holográfico
- Logos dibujados a mano en Canvas 2D no eran precisos — resuelto usando Path2D con paths oficiales de Simple Icons
- Error de sintaxis `.5.8` en código muerto (spiralPts) rompía toda la carga JS — corregido eliminando el bloque
- Secciones con background sólido tapaban el canvas fijo — resuelto con `background: transparent` + class `alt` con `rgba + backdrop-filter`

## Decisiones tomadas
- Skill standalone (no backend) con knowledge base baked-in — escala como API en el futuro
- Ficha = variables estructurales validables; contexto de audiencia = capa de inteligencia activa (no en la ficha)
- Hook mascota: estilo Maui de Moana + holograma azul/cyan (no morado genérico)
- Logos: todos morados wireframe (no de colores de marca)
- Secciones del HTML: semi-transparentes con backdrop-filter, nunca opacas sobre el canvas

## Soluciones o propuestas
- Para secciones que no tapen el fondo: 3 opciones válidas — (1) semi-transparente + blur, (2) canvas que muta según scroll, (3) contraste total blanco intencional
- Path2D con SVG paths de Simple Icons para logos perfectos sin CDN ni CORS
- Shader GLSL custom en Three.js para efectos holográficos reales (fresnel, scanlines, glitch)

## Patrones detectados
- Usuario corrige cuando el output es genérico o "de plantilla" — exige especificidad y autenticidad visual
- El proceso de construcción de UI requiere múltiples iteraciones — usuario valida visualmente, no por descripción
- Herramientas adecuadas > improvisación: cuando no tenía los SVG paths correctos intentó dibujarlos a mano con resultados pobres

## Oportunidades detectadas
- Skill `audience-aec` es el siguiente paso natural — encaja como capa de inteligencia para la `video-script-generator`
- El HTML de documentación puede ser plantilla para documentar otras skills del Escaid Setup
- El principio fondo/secciones es reutilizable en todos los proyectos con canvas animado

## Aprendizajes reutilizables
- `Path2D` acepta SVG path strings directamente — Simple Icons provee paths open source para todas las plataformas (viewBox 0 0 24 24)
- Para hologramas en Three.js: `ShaderMaterial` con fresnel + scanlines + glitch lines + depthWrite:false + side:DoubleSide
- Canvas 2D + Three.js en el mismo HTML: usar dos canvas separados, renderers independientes — no conflicts
- `ctx.stroke(path)` para wireframe, `ctx.fill(path)` + baja opacidad para ghost fill — combinación óptima para logos tech elegantes
- Fondo animado: siempre considerar cómo interactúa con secciones antes de presentar

## Preguntas abiertas
- ¿Cómo debería mutar el canvas de fondo al hacer scroll? (velocidad, color, densidad de nodos)
- ¿El gancho holográfico necesita más trabajo o está aceptable para avanzar?
- ¿Qué nuevas secciones agregar al HTML sin tapar el fondo?

## Próximos pasos
- Agregar nuevas secciones al HTML con enfoque en no tapar el fondo
- Iterar el gancho holográfico (pendiente según feedback del usuario)
- Construir skill `audience-aec`

## Tags temáticos
- video_script, skill, escaid_setup, html, ui, animacion, three_js, canvas_2d, logos, social_media, aecode

## Tags de patrón
- avance_sin_cierre (HTML pendiente de nuevas secciones)
- dependencia_excesiva (visual depende de iteraciones manuales sin sistema de preview)

## Tags de señal
- aprendizaje, decision, oportunidad, insight

## Relaciones internas del hilo
- Skill construida → requiere skill `audience-aec` para activar protocolo de inyección
- HTML doc → principio fondo/secciones → aplicable a todos los futuros HTMLs del proyecto
- Error Path2D → aprendizaje: usar SVG paths reales, no dibujar a mano

## Señales exportables a otros proyectos
- Principio fondo/secciones: aplica a cualquier proyecto con canvas animado (i-lanza-training, presentaciones, etc.)
- Path2D con Simple Icons: técnica reutilizable para cualquier visualización con logos de plataformas
- Shader GLSL holográfico: patrón reutilizable para mascotas/elementos 3D en pages de skills

## Actualizacion en vivo - 2026-05-02 - gancho 3D externo

### Estado nuevo
- El usuario rechazo que el gancho se moldee/genere manualmente y pidio insertar un modelo 3D real encontrado en web.
- El HTML debe revisarse por servidor local (`http://127.0.0.1:8765/video-script-generator-docs.html`) para que `GLTFLoader` cargue modelos `.glb`; por `file://` puede fallar o verse distinto.
- Modelo probado: Poly Pizza "Hook and chain" (`assets/models/gancho-hook.glb` / `gancho-hook-v2.glb`), fuente `https://poly.pizza/m/dBp9m8k9kTi`, licencia CC-BY 3.0.
- El `.glb` respondio 200 por HTTP, pero en la verificacion visual final el modelo nuevo no quedo visible de forma robusta y el usuario percibio que seguia apareciendo el gancho anterior.

### Decisiones nuevas
- Mantener oculto/eliminado visualmente el fallback procedural anterior (`hookGroup.visible=false`, `energyLine.visible=false`) para evitar que reaparezca si falla el modelo externo.
- El efecto holograma puede simularse en Three.js sobre un asset real mediante material cyan transparente, additive blending, wireframe/edges, ghosts y glitch; no hace falta que el modelo venga ya como holograma.
- Para el gancho final, usar un asset 3D externo descargado/licenciado y atribuido; no volver a geometria procedural si el usuario pide "modelo encontrado".

### Bloqueos nuevos
- El modelo "Hook and chain" puede estar fuera de camara, con escala/centro problematico o con materiales que no sobreviven bien al reemplazo holografico.
- Carga exitosa no equivale a visibilidad: hay que separar transporte HTTP 200, framing/escala/camara y material/renderizado.
- La validacion debe ser visual: screenshot Playwright desde servidor local con espera de carga y revision directa.

### Proximo paso inmediato
- Reemplazar el GLB actual por un modelo externo nuevo y mas visible; candidato principal: Poly Pizza "Fish hook" (`https://poly.pizza/m/3xxRFD2brcq`), alternativa: "Pirate hook" si se requiere una silueta inequivocamente distinta.
- Guardar el nuevo asset con nombre nuevo (`gancho-hook-fish.glb` o similar), ponerlo primero en `modelUrls`, aplicar cache buster en la URL de prueba y verificar con Playwright antes de confirmarlo al usuario.

## Actualizacion en vivo - 2026-05-02 - hook vuelve a aparecer
- Se verifico con Playwright local que el hook no aparecia y la consola mostraba `Maximum call stack size exceeded`.
- Causa corregida: `applyExternalHologram()` agregaba wireframes/ghosts dentro de `model.traverse()`, generando recursion al recorrer hijos recien creados.
- Causa adicional corregida: la animacion pisaba `externalHook.position.y` y podia romper el centrado calculado por `frameExternalHook()`; ahora se guarda `externalHookBasePos` y el bob se suma encima.
- Resultado verificado: captura `video-script-generator-docs-hook-fixed.png` muestra el hook externo cyan/holografico visible en el hero derecho.

## Actualizacion en vivo - 2026-05-03 - flujo 3D para UI premium
- Decision adoptada: para UI/documentacion premium, el flujo base sera buscar modelos 3D existentes en repos confiables, descargarlos/atribuirlos y luego transformarlos visualmente con materiales, holograma, wireframe, glow, particulas, framing y verificacion.
- Regla agregada a `Proyecto/escaid-setup/skills/premium-interactive-docs/SKILL.md` y sincronizada con la copia instalada en `.codex/skills/premium-interactive-docs/SKILL.md`.
- No modelar objetos 3D complejos desde cero salvo que el usuario lo pida explicitamente o no exista asset licenciado adecuado.

## Actualizacion en vivo - 2026-05-03 - skill video-script-generator creada
- Se creo `Proyecto/escaid-setup/skills/video-script-generator/` para el repo de Fabrizio con `SKILL.md`, `agents/openai.yaml` y referencias separadas: `frameworks.md`, `hooks.md`, `output-format.md`.
- La skill opera en dos tiempos inamovibles: ficha de interpretacion con confirmacion obligatoria y luego 3 guiones completos con 5 hooks cada uno.
- La skill fue sincronizada tambien en `.codex/skills/video-script-generator/` para uso local inmediato.
- Validacion `quick_validate.py`: OK en repo y OK en copia local.

## Actualizacion en vivo - 2026-05-03 - capa Magnus de psicologia del espectador
- Criterio absorbido: antes de escribir hooks/guiones, destruir variables perceptuales del usuario: creencia actual, friccion, deseo, miedo, amenaza de ignorar, payoff inmediato, razon para confiar y razon para comentar/guardar/compartir.
- Se agrego `references/audience-psychology.md` a `video-script-generator` con mapa de estados del espectador, levers psicologicos, simulacion de reaccion del hook y filtro Magnus de decision.
- La skill ya no debe aceptar hooks cuya reaccion interna sea solo "ok", "ya sabia" o "suena importante"; debe buscar "espera, eso puede pasarme", "nunca lo vi asi" o "esto me haria mas senior".
- Validacion OK en repo y copia local.

## Actualizacion en vivo - 2026-05-03 - separacion Magnus vs skill de guiones
- Criterio confirmado por usuario: Magnus elige el filo estrategico; la skill `video-script-generator` ejecuta la escritura.
- Magnus debe decidir: estado de conciencia, barrera perceptual, tension, palanca psicologica, amenaza de ignorar, payoff, hook family, framework family y angulo publico.
- La skill debe ejecutar: ficha, hooks, estructura, guion, capas verbal/visual/textual/auditiva, CTA, direccion de produccion y variantes.
- Se creo `inteligencia/aecode/memory/criteria.md` con criterios de eleccion para Magnus.
- Se agrego `references/magnus-handoff.md` y se actualizo `SKILL.md` para que la skill use `MAGNUS STRATEGIC INPUT` como fuente de verdad cuando exista.
- Validacion OK en repo y copia local.

## Actualizacion en vivo - 2026-05-03 - nuevo poder general de Magnus
- Criterio ampliado: los aprendizajes de percepcion, hooks, frameworks y psicologia no pertenecen solo a marketing ni a `video-script-generator`; son una capacidad general de Magnus para cualquier decision donde humanos deban mirar, confiar, adoptar, aprobar, comprar, recordar o actuar.
- Se agrego `references/perception-choice.md` a `magnus-thinker` en repo y copia local.
- Se actualizo `magnus-thinker/SKILL.md` para enlazar el protocolo y agregar la regla: Magnus elige percepcion y filo antes de que las skills operativas ejecuten.
- Validacion automatica de Magnus no corre por encoding heredado del SKILL.md, pero se verifico con `rg` que los cambios estan presentes en repo y local.

## Actualizacion en vivo - 2026-05-03 - Magnus como kernel general de criterios
- Se audito `magnus-thinker` y se detecto que varios poderes estaban formulados como protocolos condicionados por accion. Se promovio la logica a un kernel general siempre activo.
- Nuevo archivo: `skills/magnus-thinker/references/general-criteria-kernel.md` con criterios universales: realidad del receptor, adopcion sobre elegancia, referencia externa antes de inventar, herramienta existente antes de custom, ruta de recursos antes de reducir alcance, capas semanticas, friccion/riesgo, asimetria/opcionalidad, especificidad, feedback path y delegacion a skills.
- `SKILL.md` ahora declara una cuarta capa silenciosa: kernel general de criterios, entre criterios activos y fases internas.
- Regla agregada: los protocolos especificos no quedan encerrados en triggers; Magnus extrae el criterio reusable y lo aplica en cualquier dominio donde cambie la decision.
- Sincronizado en repo y `.codex/skills/magnus-thinker`.

## Actualizacion en vivo - 2026-05-03 - filtro de lenguaje vivido por la mayoria
- Correccion del usuario: Magnus puede elegir bien la variable estrategica, pero fallar al traducirla a palabras que la mayoria del publico siente/piensa. Ejemplo: "modelo limpio" es etiqueta analitica; "modelar en Revit no es coordinar hospitales" ataca una creencia masiva del sector.
- Criterio absorbido en `inteligencia/aecode/memory/criteria.md`: priorizar lenguaje vivido y comportamientos reconocibles por la mayoria sobre frases tecnicamente correctas pero raras o abstractas.
- Se agrego `Mass Language Filter` a `magnus-thinker/references/perception-choice.md` y a `video-script-generator/references/audience-psychology.md`.
- Regla: una frase estrategicamente correcta se rechaza si el publico no piensa/habla asi; el hook debe conectar comportamiento comun + consecuencia/identidad deseada.

## Actualizacion de continuidad - 2026-05-04 - punto exacto para seguir con Claude

### Estado actual del trabajo
- HTML `video-script-generator-docs.html` quedo visualmente operativo con gancho 3D externo real tipo fish hook, cargado como data URI para evitar problemas de cache/CORS/file://, con efecto holografico cyan y reencuadre sin recorte.
- Flujo UI premium actualizado: usar modelos 3D reales de repos, guardarlos/atribuirlos localmente y transformarlos visualmente; no modelar desde cero salvo pedido explicito.
- Skill `video-script-generator` creada en `Proyecto/escaid-setup/skills/video-script-generator/` y sincronizada en `.codex/skills/video-script-generator/`.
- Magnus fue ampliado: `magnus-thinker` ahora tiene `perception-choice.md` y `general-criteria-kernel.md`; Magnus no solo aplica estos criterios a marketing, sino a cualquier decision donde humanos deban mirar, confiar, adoptar, aprobar, comprar, recordar o actuar.
- `inteligencia/aecode/memory/criteria.md` contiene criterios activos sobre eleccion, percepcion, hooks, frameworks, lenguaje vivido y separacion Magnus vs skills operativas.

### Separacion conceptual confirmada por usuario
- Magnus = capa protagonista de decision: elige filo, percepcion, barrera, tension, palanca, framework/hook family y lenguaje que mueve a la mayoria.
- Skill de guiones = capa operativa: BD de hooks/frameworks + escritura de ficha, hooks, guion, CTA y direccion de produccion.
- La skill de guiones no elige funnel ni estrategia macro; eso viene antes desde Magnus + skill estrategica/funnel/marketing.

### Ultima correccion critica del usuario
- Magnus puede conectar variables bien, pero aun puede fallar al traducirlas a texto publico.
- Ejemplo rechazado: `Tu modelo BIM puede estar limpio...` porque `modelo limpio` es etiqueta rara/analitica que la mayoria no piensa ni siente.
- Mejor camino mental: atacar comportamientos masivos reconocibles, por ejemplo `modelar en Revit`, `revisar clashes`, `saber usar la herramienta`, y contrastarlos con outcomes de mayor valor como `coordinar hospitales`, `operacion critica`, `riesgo`, `flujos clinicos`, `criterio senior`.
- Criterio activo: una frase estrategicamente correcta se rechaza si el publico no piensa/habla asi; el hook debe conectar comportamiento comun + consecuencia o identidad deseada.

### Ultima iteracion de hooks BIM hospitalario
- Caso: video sobre BIM aplicado a hospitales para usuarios que ya conocen el curso, pero no perciben claramente el valor diferencial frente a BIM en edificaciones/colegios.
- Hook base inicial corregido por usuario: `Modelar en Revit no es coordinar hospitales` era ejemplo, no necesariamente final.
- Propuesta corregida de hooks del Guion 1:
  - `Saber Revit no significa saber coordinar un hospital.`
  - `Nunca coordines un hospital como si fuera un edificio normal.`
  - `El error mas caro en BIM hospitalario no siempre aparece como clash.`
  - `Si solo revisas interferencias, todavia estas haciendo BIM basico.`
  - `En edificios coordinas espacios. En hospitales coordinas riesgos.`
- Lectura: el usuario quiere seguir paso a paso corrigiendo hooks, evaluando si transmiten realmente ego/status, expertise gap, hidden cost y lenguaje masivo.

### Proximo paso recomendado para Claude
1. Continuar con el primer hook del primer guion, pero NO asumir que la ultima propuesta ya gano.
2. Hacer evaluacion Magnus explicita de cada hook candidato:
   - lenguaje vivido por la mayoria
   - creencia masiva que ataca
   - emocion que realmente transmite
   - si se entiende en menos de 3 segundos
   - si suena a persona real o a analista
   - si vende a la masa o solo a un subgrupo experto
3. Pedir al usuario validar/corregir antes de pasar al siguiente hook.
4. Mantener Coda Magnus solo como debrief de eleccion, no como cadena larga.

### Archivos clave
- `Proyecto/escaid-setup/skills/video-script-generator/SKILL.md`
- `Proyecto/escaid-setup/skills/video-script-generator/references/audience-psychology.md`
- `Proyecto/escaid-setup/skills/video-script-generator/references/viral-quality-gates.md`
- `Proyecto/escaid-setup/skills/video-script-generator/references/magnus-handoff.md`
- `Proyecto/escaid-setup/skills/magnus-thinker/references/perception-choice.md`
- `Proyecto/escaid-setup/skills/magnus-thinker/references/general-criteria-kernel.md`
- `inteligencia/aecode/memory/criteria.md`

### Nota de validacion
- `video-script-generator` valido con `quick_validate.py` en repo y copia local.
- `magnus-thinker` no valida automaticamente por encoding heredado del `SKILL.md`, pero los cambios fueron verificados con `rg` y sincronizados en repo/local.
