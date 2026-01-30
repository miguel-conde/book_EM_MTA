# Stage 0 — Book Intake (Global Context)

Este documento define el contexto editorial global del libro. Debe estar
completo antes de editar capítulos.

---

## Book Title
Algoritmo Expectation–Maximization (EM)

## Subtitle (if any)
Aplicado a atribución de ventas HCP y Multi-touch Attribution (MTA)

## Author
Miguel Conde

## Intended Audience
- Data Scientists / Analytics que trabajan con MMM/MTA, CRM, ventas agregadas o asignación de crédito.
- Equipos que necesitan un output estable, defendible y auditable ante negocio.

### Expected Background Knowledge
- Probabilidad y estadística aplicada (distribuciones, esperanza/varianza, log-likelihood).
- Modelos lineales generalizados (GLM) a nivel práctico.
- Python para implementación y debugging (no hace falta ML “black-box”).

### Not Expected
- Que el lector asuma que el método por sí mismo “crea causalidad”.
- Inferencia bayesiana avanzada como prerequisito (se introduce al final como alternativa).
- Que EM sustituya a experimentos (geo-lift, A/B, etc.).

---

## Book Objective

### What problem the book solves
Repartir un total agregado (ventas por brick, contribución incremental por canal, etc.) a unidades inferiores (HCPs, campañas, creatividades) de forma coherente, auditable y reproducible, formulándolo como un modelo generativo con variables latentes.

### What the reader should be able to do after finishing the book
- Formular el problema “agregado → desagregado” como un modelo de variables latentes.
- Derivar y ejecutar EM para estimar productividades/eficiencias y obtener un reparto consistente (con conservación de masa).
- Operacionalizar el enfoque: identificabilidad, regularización, cold start, estabilidad y criterios de producción.

### What the book explicitly does NOT attempt to cover
- No promete causalidad intra-canal por sí misma; si el total viene de un MMM incremental, el total es “causal”, pero el split intra-canal requiere identificación extra.
- No sustituye experimentos.

---

## Editorial Tone and Positioning
- Technical level: intermediate (pragmático, end-to-end, orientado a producción)
- Style reference:
  - Profesional
  - Didáctico
  - Practitioner-oriented
- No es paper académico, ni blog casual.

---

## Constraints
- Preservar el contenido 100% (ideas, argumentos y conclusiones)
- Preservar el/los idioma(s) original(es)
- Cambios permitidos: edición (claridad, estructura, fluidez, consistencia)
