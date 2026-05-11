---
proyecto: aecode
fecha: 2026-05-01
slug: 2026-05-01-arquitectura-f3-contexto-inicial
tipo: contexto
estado: cerrado
---

# THREAD: Arquitectura AECODE Fase 3 — Contexto Inicial

## Resumen ejecutivo
Ingesta del sistema de arquitectura pedagogica de AECODE Fase 3. La pieza central del sistema es la **Skill** como unidad minima de producto, no la capsula. La jerarquia completa es `Ruta -> Cluster -> Skill -> Capsula`, pero el valor de producto, la medicion, el monitoreo y la escala se concentran en la Skill.

## Estado del proyecto en este momento
- Arquitectura base definida y documentada
- System instructions del assistant disponibles
- Documentos fuente: AECODE_Fase3_Arquitectura_Skills.md y AECODE_System_Instructions_Rutas_Clusters_Skills.md
- Fase 3 activa: diseno orientado a desempeno laboral en AEC

---

## Arquitectura del sistema

### Jerarquia
`Ruta -> Cluster -> Skill -> Capsula`

### Unidad central de producto
**Skill** — no es la capsula.

### Formulas clave

**RUTA**
`RUTA = Rol o resultado laboral objetivo + Secuencia progresiva de clusters + Dependencias validadas`
`RUTA AEC = Especialidad profesional + Rol especializado o resultado ocupacional + Secuencia progresiva de clusters + Dependencias validadas`

**CLUSTER**
`CLUSTER = Funcion tecnica macro + Conjunto coherente de skills + Limite de dominio`

**SKILL BASE**
`SKILL BASE = Capacidad + Sistema/Objeto tecnico + Funcion dominante + Objetivo profesional`

**SKILL AFINADA**
`SKILL AFINADA = Capacidad + Sistema/Objeto tecnico + Funcion dominante + Contexto tecnico relevante + Objetivo profesional`

**SKILL AEC**
`SKILL AEC = Capacidad + Sistema/Objeto tecnico + Funcion dominante + Especialidad relevante + Contexto tecnico relevante + Objetivo profesional`

**CAPSULA**
`CAPSULA = Microfuncion o accion delimitada + Elemento tecnico + Contexto inmediato de ejecucion`

---

## Decisiones de arquitectura

- La skill es la unidad que crea valor, diseña experiencia, mide avance, monitorea ejecucion, empaqueta oferta y escala producto
- En AEC, la especialidad relevante debe incluirse cuando cambia la naturaleza profesional de la skill
- La funcion dominante es el frente de trabajo tecnico, no la accion puntual (diferente de la capacidad)
- Un brief/brochure no define arquitectura — solo delimita alcance; la arquitectura se reconstruye con logica AECODE
- Si hay varias salidas ocupacionales reconocibles en un brief, puede ser una macrooferta con varias rutas internas

---

## Reglas criticas a recordar

1. **Densidad de skill**: una sola capacidad dominante, un bloque tecnico principal, evaluable con resultado observable
2. **Progresion de ruta**: siempre incluir skills fundacionales + operativas + avanzadas; ninguna skill avanzada sin skills previas que la habiliten
3. **Clusters por funcion, no por herramienta**: si cambia de herramienta y el cluster sigue teniendo sentido, es valido
4. **Capsula no es skill**: si tiene valor profesional propio y puede medirse sola, es skill no capsula
5. **Errores a evitar**: convertir herramientas en clusters, copiar modulos de syllabus, skills demasiado amplias, omitir skills fundacionales

---

## Patrones detectados

- `diseno_pedagogico_orientado_a_producto`: el sistema prioriza valor de mercado y medicion sobre logica academica tradicional
- `skill_como_unidad_atomica_de_valor`: decision de diseno central que diferencia AECODE de otros sistemas de formacion
- `especialidad_como_diferenciador_aec`: el sector AEC requiere especificidad disciplinar en cada skill para evitar ambiguedad profesional

---

## Tags

**Tematicos:** aecode, fase3, skill, arquitectura_pedagogica, ruta, cluster, capsula, diseno_de_producto_educativo, aec, bim
**Patron:** diseno_desde_desempeno_laboral, skill_como_unidad_central
**Señal:** oportunidad — sistema arquitectural maduro disponible para aplicar a cualquier brief AEC

---

## Relaciones internas
- Aplicable a cualquier brief, brochure o temario AEC que llegue al proyecto
- Conecta con estrategia de marketing (ver AECODE_Estrategia_Marketing_Procesos.docx)
- Base para el diseño de rutas especificas por especialidad (estructuras, MEP, arquitectura, infraestructura)

---

## Señales exportables
- El modelo Ruta-Cluster-Skill-Capsula puede aplicarse a proyectos de formacion fuera de AEC
- La distincion `capacidad vs funcion dominante` es util en cualquier diseño curricular orientado a competencias
