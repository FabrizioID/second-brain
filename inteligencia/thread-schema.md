# Thread Schema

Cada hilo es un nodo independiente de memoria. Debe poder leerse sin abrir todo el proyecto.

## Frontmatter minimo

```yaml
---
slug: YYYY-MM-DD-slug-tema
proyecto: Nombre del proyecto
fecha: YYYY-MM-DD
tipo: estrategia | ingesta | sintesis | ejecucion | decision | cierre
---
```

## Secciones recomendadas

- `Objetivo del hilo`
- `Resumen ejecutivo`
- `Estado del proyecto en este momento`
- `Avances detectados`
- `Problemas o bloqueos`
- `Decisiones tomadas`
- `Soluciones o propuestas`
- `Patrones detectados`
- `Oportunidades detectadas`
- `Aprendizajes reutilizables`
- `Preguntas abiertas`
- `Proximos pasos`
- `Tags tematicos`
- `Tags de patron`
- `Tags de senal`
- `Relaciones internas del hilo`
- `Senales exportables a otros proyectos`

## Regla de oro

Si una informacion solo sirve dentro de la sesion actual, no va a `MASTER_IDEAS.md`; va al thread del proyecto o no se guarda.
