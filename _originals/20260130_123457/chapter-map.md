# Chapter Role Map

Este documento define el rol editorial de cada capítulo. Su objetivo es evitar
repeticiones, inconsistencias de terminología/notación y “scope creep”.

---

## Preface / Front Matter — Preface

### Purpose
Dar el encuadre pragmático del libro (problema “agregado → desagregado”), la tesis central y una ruta de lectura.

### Concepts Introduced
- Problema “agregado → desagregado” como variables latentes
- Conservación de masa
- EM como mecanismo estándar para estimación + reparto

### Concepts Assumed (Previously Introduced)
- Ninguno (debe ser autocontenido)

### Depth Level
- ☒ Conceptual
- ☐ Technical
- ☐ Applied
- ☐ Mixed

### Must NOT Do
- Entrar en derivaciones largas
- Presentar implementación

---

## Chapter 0 — Introducción

### Purpose
Fijar el patrón canónico (observado/latente/productividad/exposición) y conectar explícitamente HCP–Brick con MMM→MTA.

### Concepts Introduced
- Observado vs latente en ambos casos de uso
- Exposición/offset como oportunidad
- Productividad positiva (y extensión con covariables vía $\exp(X\beta)$)

### Concepts Assumed (Previously Introduced)
- Lectura del Preface

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☐ Applied
- ☐ Mixed

### Must NOT Do
- Resolver el caso MMM→MTA completo (se reserva para el capítulo 8)

---

## Chapter 1 — El problema como modelo de variables latentes

### Purpose
Reformular el problema de negocio como estadística: inferencia con datos incompletos y variables latentes.

### Concepts Introduced
- Variables latentes / datos incompletos en atribución
- Qué está observado vs qué es latente

### Concepts Assumed (Previously Introduced)
- Patrón general de la Introducción

### Depth Level
- ☒ Conceptual
- ☐ Technical
- ☐ Applied
- ☐ Mixed

### Must NOT Do
- Fijar notación definitiva del libro (se hace en el Capítulo 2)

---

## Chapter 2 — Modelo probabilístico base (sin covariables)

### Purpose
Formalizar notación y el modelo generativo base (unidades) y su restricción estructural de suma al agregado.

### Concepts Introduced
- Notación ($h,b$, $\mathcal{H}_b$, $y_b$, $w_{h,b}$)
- Variable latente $z_{h,b}$ y restricción $\sum_h z_{h,b}=y_b$

### Concepts Assumed (Previously Introduced)
- Definición del problema como variables latentes

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☐ Applied
- ☐ Mixed

### Must NOT Do
- Introducir covariables (Capítulo 5)

---

## Chapter 3 — EM paso a paso en este contexto

### Purpose
Derivar EM en el caso Poisson (unidades) y fijar la interpretación del share como esperanza condicional.

### Concepts Introduced
- Multinomial condicionada en la suma para Poisson independientes
- E-step como reparto por shares y M-step para parámetros

### Concepts Assumed (Previously Introduced)
- Notación y modelo base del Capítulo 2

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☐ Applied
- ☐ Mixed

### Must NOT Do
- Hacer el ejemplo numérico (Capítulo 4)

---

## Chapter 4 — Ejemplo numérico pequeño (a mano)

### Purpose
Internalizar la mecánica de EM con un ejemplo mínimo y completo (2 bricks, 4 HCPs) con 2–3 iteraciones.

### Concepts Introduced
- Ejecución concreta de E-step/M-step en un dataset pequeño

### Concepts Assumed (Previously Introduced)
- EM derivado en el Capítulo 3

### Depth Level
- ☐ Conceptual
- ☐ Technical
- ☒ Applied
- ☐ Mixed

### Must NOT Do
- Introducir regularización/covariables (Capítulo 5)

---

## Chapter 5 — Incorporando features de HCP (modelo realista)

### Purpose
Hacer el salto a producción: parametrizar productividad con covariables ($\lambda_h=\exp(X_h\beta)$) para generalizar y regularizar.

### Concepts Introduced
- Productividad estructural con $X_h$ y $\beta$
- Motivación: identificabilidad débil, generalización y shrinkage vía regularización

### Concepts Assumed (Previously Introduced)
- Modelo base y EM (Capítulos 2–4)

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Entrar en detalles completos de implementación (Capítulo 7)

---

## Chapter 6 — Mock data generation

### Purpose
Definir un mundo sintético con ground truth para testear recuperación, estabilidad y conservación de masa.

### Concepts Introduced
- Diseño de simulación: $X_h$, $\beta^*$, $z^*_{h,b}$, $y_b$

### Concepts Assumed (Previously Introduced)
- Modelo con covariables (Capítulo 5)

### Depth Level
- ☐ Conceptual
- ☐ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Presentar el notebook end-to-end (Capítulo 7)

---

## Chapter 7 — Implementación completa en Python

### Purpose
Proveer una implementación end-to-end (E-step vectorizado; M-step como Poisson GLM con offset + IRLS + ridge) y checklist de debugging.

### Concepts Introduced
- Vectorización del E-step y garantías de conservación de masa
- M-step como GLM con offset y regularización

### Concepts Assumed (Previously Introduced)
- EM y modelo realista (Capítulos 3–6)

### Depth Level
- ☐ Conceptual
- ☐ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Cambiar el alcance del algoritmo (se mantiene dentro del marco ya definido)

---

## Chapter 8 — Capítulo extra (MMM → MTA)

### Purpose
Aplicar el mismo patrón EM para repartir contribuciones de MMM (por tiempo y opcionalmente geo) a campañas/creatividades dentro de cada medio.

### Concepts Introduced
- Notación MMM→MTA: $C_{m,t,g}$ observado y $z_{m,k,t,g}$ latente
- Exposición/evidencia por campaña (spend/impresiones/clicks) con adstock + saturación

### Concepts Assumed (Previously Introduced)
- Patrón general (Introducción)
- EM como reparto condicionado en el total

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Presentar granularidad horaria como requisito resuelto si no está en el texto

---

## Chapter 9 — Unidades vs Euros

### Purpose
Guiar la elección de distribución (Poisson vs Gamma/Lognormal) cuando el total observado son unidades vs euros, y cómo cambia el EM.

### Concepts Introduced
- Diferencias conceptuales y prácticas entre unidades y euros

### Concepts Assumed (Previously Introduced)
- EM base en unidades

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Derivar teoría adicional fuera del objetivo práctico

---

## Chapter 10 — Pitfalls reales y extensiones

### Purpose
Fijar criterio de producción: identificabilidad, overfitting silencioso y extensiones prácticas.

### Concepts Introduced
- Identificabilidad y casos típicos de fallo
- Overfitting silencioso y controles

### Concepts Assumed (Previously Introduced)
- Modelo y EM en producción

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Convertir el capítulo en un tratado académico

---

## Chapter 11 — Explicar a negocio

### Purpose
Dar una narrativa defendible para stakeholders: qué hace el split, por qué es coherente, y qué no promete.

### Concepts Introduced
- Storyline en 3 slides (sin ecuaciones)
- Guardrails: no inventar ventas; total fijo

### Concepts Assumed (Previously Introduced)
- Qué representa el total (MMM) y qué representa el reparto (MTA)

### Depth Level
- ☒ Conceptual
- ☐ Technical
- ☒ Applied
- ☒ Mixed

### Must NOT Do
- Reintroducir la matemática (si el capítulo pretende ser sin ecuaciones)

---

## Chapter 12 — Enfoque Bayesiano Jerárquico

### Purpose
Presentar la alternativa bayesiana jerárquica: inferencia de $p(\theta,z\mid y)$, incertidumbre, shrinkage e implicaciones prácticas.

### Concepts Introduced
- Diferencia EM vs Bayes (posteriores vs puntos)
- Salidas: distribuciones, intervalos, decisiones con riesgo

### Concepts Assumed (Previously Introduced)
- Modelo generativo y rol de $z$ como latente

### Depth Level
- ☐ Conceptual
- ☒ Technical
- ☐ Applied
- ☒ Mixed

### Must NOT Do
- Asumir que el lector ya domina MCMC/VI sin introducirlo en el texto

---

## Appendices (90–95) y Biblio (99)

### Purpose
Material de soporte: software, documentación para CXOs, notas de exposición/offset y piezas de comunicación.

### Depth Level
- ☒ Applied

### Must NOT Do
- Repetir contenido central de capítulos

