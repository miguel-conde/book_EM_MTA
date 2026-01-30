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

### Nivel técnico
- Technical level: intermediate (pragmático, end-to-end, orientado a producción)

### Tono
- Profesional
- Didáctico
- Practitioner-oriented
- No es paper académico, ni blog casual.

### Composición (estilo de redacción)

Este libro tiene objetivos tutoriales y pedagógicos. Por tanto, la composición prioriza prosa técnica clara y guiada por encima de esquemas.

- Prosa primero: explicar en párrafos completos antes de enumerar.
- Menos listas: usar viñetas solo cuando estructuren material ya explicado (checklists, enumeraciones cortas, comparativas).
- Transiciones explícitas: conectar secciones con frases puente que aclaren por qué se pasa de un concepto al siguiente.
- Densidad legible: mantener contenido técnico, pero con ritmo de lectura fluido (definir términos al introducirlos y recordar brevemente notación cuando reaparece).
- Coherencia de notación: preferir una notación canónica estable a lo largo del libro (p. ej., índices y símbolos consistentes entre capítulos).

### Recursos visuales (negritas y cursivas)

Se permite usar **negritas** y *cursivas* como ayudas visuales, con un criterio consistente y moderado.

- **Negrita**: reservar para anclas conceptuales (p. ej., observado vs latente; conservación de masa; objetivo/modelo/inferencia) y para resaltar el término clave de un párrafo. Evitar negrita en frases completas y limitar a 1–3 resaltados por párrafo.
- *Cursiva*: reservar para etiquetas técnicas y nombres cortos dentro de la prosa (p. ej., *likelihood observada*, *likelihood completa*, *E-step*, *M-step*, *stress testing*). Mantener el mismo término siempre en el mismo estilo.
- No mezclar estilos para “subir volumen” (evitar ***negrita+cursiva*** salvo casos excepcionales).
- No usar subrayado; mantener las expresiones matemáticas sin énfasis tipográfico (la notación se controla con LaTeX).

---

## Constraints
- Preservar el contenido 100% (ideas, argumentos y conclusiones)
- Preservar el/los idioma(s) original(es)
- Cambios permitidos: edición (claridad, estructura, fluidez, consistencia)

### Criterio práctico

Cuando haya tensión entre “resumir” y “enseñar”, se prioriza enseñar: reescritura a prosa más guiada, manteniendo las mismas ideas, supuestos y resultados.
