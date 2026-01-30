# Global Glossary (Canonical Terms)

Este glosario fija términos canónicos y evita deriva de sinónimos entre capítulos.

---

## Term: Expectation–Maximization (EM)
- Language: EN/ES
- Definition: Algoritmo iterativo para estimar parámetros en modelos con variables latentes alternando un E-step (inferir esperanzas condicionales) y un M-step (actualizar parámetros).
- Notes:
  - Synonyms to avoid: “EM algorithm” vs “algoritmo EM” (usar “EM” de forma consistente)

---

## Term: E-step
- Language: EN
- Definition: Paso donde se calcula $\mathbb{E}[z\mid y,\theta]$ o los repartos/atribuciones esperadas dado el total observado.
- Notes:
  - Preferred phrasing: “E-step (reparto)” cuando se quiera enfatizar su interpretación

---

## Term: M-step
- Language: EN
- Definition: Paso donde se actualizan parámetros (p. ej. $\lambda$ o $\beta$) maximizando el objetivo dado el E-step.

---

## Term: Variable latente
- Language: ES
- Definition: Variable no observada (p. ej. $z_{h,b}$) cuya suma/restricción explica el agregado observado.
- Notes:
  - Synonyms to avoid: “oculta” (usar “latente”)

---

## Term: Conservación de masa
- Language: ES
- Definition: Propiedad por la cual la atribución desagregada suma exactamente al total observado (p. ej. $\sum_h \hat z_{h,b}=y_b$).

---

## Term: Exposición / oportunidad
- Language: ES
- Definition: Término conocido que modula el volumen esperable (p. ej. $w_{h,b}$ o $w_{m,k,t,g}$), usado como evidencia/escala en el reparto.
- Notes:
  - Preferred phrasing: “exposición”
  - Synonyms to avoid: alternar “exposure”, “opportunity” y “peso” sin fijar equivalencia

---

## Term: Offset
- Language: EN
- Definition: Término fijo en un GLM que entra aditivamente en el predictor lineal (p. ej. $\log \tilde w$ en Poisson) para modelar exposición.

---

## Term: Productividad / eficiencia
- Language: ES
- Definition: Parámetro positivo que controla el reparto relativo (p. ej. $\lambda_h$ o $\lambda_{m,k}$).

---

## Term: MMM (Marketing Mix Model)
- Language: EN
- Definition: Modelo que estima contribuciones por canal/medio, típicamente en granularidad temporal y opcionalmente geo.

---

## Term: MTA (Multi-touch Attribution)
- Language: EN
- Definition: Asignación de contribución a niveles inferiores (campañas/creatividades/adsets) dentro de un canal, con granularidad más fina que MMM.

---

## Term: HCP
- Language: EN
- Definition: Health Care Professional, unidad individual a la que se atribuyen ventas dentro de bricks.

---

## Term: Brick
- Language: EN/ES
- Definition: Agrupación geográfica/comercial donde se reporta un total agregado ($y_b$).

---

## Term: Poisson (unidades)
- Language: EN
- Definition: Distribución natural para conteos no negativos (unidades); en el libro se usa como caso base donde EM queda cerrado.

---

## Term: Gamma / Lognormal (euros)
- Language: EN
- Definition: Distribuciones naturales para variables continuas positivas (euros), con colas pesadas y outliers.

---

## Term: Identificabilidad
- Language: ES
- Definition: Propiedad por la cual los datos contienen suficiente información para distinguir parámetros; su falta implica repartos no únicos.

---

## Term: Regularización (ridge)
- Language: ES/EN
- Definition: Penalización (p. ej. L2) para controlar overfitting en el M-step cuando hay covariables.

---

## Term: IRLS
- Language: EN
- Definition: Iteratively Reweighted Least Squares; algoritmo estándar para ajustar GLMs (p. ej. Poisson) en el M-step.

---

## Term: Adstock
- Language: EN
- Definition: Transformación que introduce memoria/arrastre temporal en exposición (usada al construir $w$ MMM-consistente).

---

## Term: Saturación (Hill)
- Language: ES/EN
- Definition: Transformación no lineal (p. ej. Hill) para modelar rendimientos decrecientes de la exposición.

---

## Term: Shrinkage
- Language: EN
- Definition: Contracción de estimaciones hacia un valor común inducida por priors jerárquicos o regularización.

