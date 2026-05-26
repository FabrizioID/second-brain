# Legacy inteligencia ingest - 2026-05-26

Se migraron memorias faltantes desde `C:\Users\USUARIO\inteligencia` hacia `second-brain/inteligencia` sin eliminar el origen legacy y sin sobrescribir reescrituras existentes.

## Migrado

- `genplus/threads/2026-05-17-agente-refs-ads.md` -> `gen-plus/threads/2026-05-17-agente-refs-ads.md`
- `genplus/threads/2026-05-21-genbot-inmobiliario-n8n.md` -> `gen-plus/threads/2026-05-21-genbot-inmobiliario-n8n.md`
- `ingeconcreto/` -> `ingeconcreto/`
- `tesis-juan-carlos-arteaga/threads/2026-05-07-apa7-validacion-fuentes.md` -> `tesis-juan-carlos-arteaga/threads/2026-05-07-apa7-validacion-fuentes.md`
- `branding/` -> `branding/`

## Normalizaciones

- `genplus` se mapeo al slug canonico `gen-plus`.
- `ingeconcreto/threads/T01-propuesta-bim.md` se guardo como `ingeconcreto/threads/2026-05-06-propuesta-bim-training.md` para cumplir convencion fecha + slug.
- Se agregaron filas en los indices canonicos para que Magnus/context pull encuentren los hilos.
- Se registro `GEN+` e `INGECONCRETO` en `_registry.md`.

## Seguridad

- En el hilo `2026-05-21-genbot-inmobiliario-n8n.md` se redacto una contraseña temporal antes de dejarla en Second Brain canonico.

## Regla vigente

La raiz canonica queda en `second-brain/inteligencia/`. `C:\Users\USUARIO\inteligencia` queda como legacy/fallback de lectura o auditoria historica, no como destino de nuevos hilos.
