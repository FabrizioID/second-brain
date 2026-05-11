# Patrones de Decisión y Pensamiento - Magnus Scan

> Este archivo se actualiza cada vez que el usuario dice "escanea" o Magnus detecta un patrón relevante.
> Formato: patrón observado → qué lo activa → valor para decisiones futuras.

---

## Protocolo de escaneo

Cuando el usuario dice **"escanea"**, Magnus:
1. Revisa la conversación completa en busca de: decisiones tomadas, variables clave usadas, razonamientos validados por el usuario, rechazos o correcciones
2. Extrae patrones en 3 categorías: metodológicos, de preferencia del usuario, de variables de decisión
3. Los guarda aquí como patrones y en `criteria.md` si son lo suficientemente específicos para cambiar una decisión futura
4. Confirma al usuario: "Escaneo completado — N patrones extraídos"

---

## Patrones extraídos

### SCAN-001 | 2026-05-01 | Estimación estructural por ratios

**Patrón:** Para estimar acero en estructura completa sin despiece total, usar un elemento con despiece real como ancla de calibración (preferiblemente cimentación/platea) y aplicar factores de ajuste por tipo de elemento al resto.

**Variables clave del patrón:**
- Ratio ancla = tonelaje real ÷ volumen real del elemento calibrador
- Factores típicos: losas ×0.85–1.08 / vigas ×1.57–1.93 / muros ×1.20–1.45 (relativo a platea)
- Validación: ratio global resultante debe estar entre 80–110 kg/m³ para estructura mixta HA

**Qué lo activa:** Cuando hay volumetrías pero solo un despiece completo disponible

**Valor:** Reduce tiempo de estimación de semanas a minutos con precisión de ±15%

---

### SCAN-002 | 2026-05-01 | Flujo de trabajo preferido para metrados

**Patrón:** El usuario prefiere pasar datos en tablas de imagen (captura de pantalla de Excel/BIM) en lugar de texto plano. Magnus debe leer las imágenes directamente y no pedir que los reformatee.

**Qué lo activa:** Cualquier tarea de metrado, presupuesto o cuantificación

**Valor:** No interrumpir el flujo del usuario pidiéndole reformatear datos que ya tiene en tabla

---

### SCAN-003 | 2026-05-01 | Presentar rangos + valor central en estimaciones

**Patrón:** En estimaciones de ingeniería, el usuario acepta mejor un resultado con escenario conservador / central / alto que un único número puntual. El valor de trabajo recomendado siempre se nombra explícitamente.

**Qué lo activa:** Cualquier estimación con incertidumbre (costos, tonelajes, tiempos)

**Valor:** Evita sobreconfianza y da al usuario margen de negociación

---

### SCAN-004 | 2026-05-01 | Configuración del entorno Magnus

**Patrón:** El usuario quiere Magnus activo por defecto en cada sesión, con aprendizaje continuo y sin prompts de permiso para tools frecuentes. Prefiere operar sin fricción en el entorno.

**Variables:**
- `learning_mode: true` en state.json del router
- Allowlist de tools read-only en `.claude/settings.json`
- Tools mutantes (Word, Playwright) requieren habilitación explícita separada si se quiere sin prompt

**Qué lo activa:** Configuración de nueva sesión o nuevo proyecto

**Valor:** No reconfigurar el entorno cada sesión

