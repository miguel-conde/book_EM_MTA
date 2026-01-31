
**Informe editorial — Hallazgos sobre $\omega_{b,h}$ / $w_{h,b}$ (exposure)**

**1) Estado actual (qué funciona)**
- La definición “formal” de la variable existe y es consistente: en 2-modelo-base.qmd se fija $w_{h,b}\ge 0$ como exposición/oportunidad observada y se declara la equivalencia con $\omega_{b,h}$, con puntero al apéndice.
- Hay una definición técnica muy defendible (exposure vs offset) en 93-ap-3-exposure.qmd: $\omega$ es exposure y $\log\omega$ es offset.
- También hay una definición operativa (más “mental model”, incluye qué no es) en 8-caso-de-uso-MTA.qmd, pero aparece tarde en el libro.

**2) Dónde se pierde un lector técnico (riesgos reales)**
- En Cap. 1, la exposición se define en abstracto, pero sin ejemplo inmediato: 1-problema-variables-latentes.qmd. Para un lector, “exposición/peso/oportunidad” puede seguir sonando ambiguo (¿binaria? ¿normalizada? ¿visitas?).
- En Cap. 3 y 5, el símbolo $w_{h,b}$ se usa intensamente en fórmulas como parte del mecanismo, pero se asume que el lector ya lo interiorizó (no se re-explica): por ejemplo 3-EM-paso-a-paso.qmd y 5-modelo-realista.qmd.
- En capítulos posteriores cambia la notación a $\omega_{b,h}$ sin “micro-recordatorio” local, lo que reabre la duda de si es el mismo objeto:
  - En 9-unidades-y-euros.qmd aparece $\omega_{b,h}$ en E-step/M-step en frío.
  - En 10-pitfalls-y-extensiones.qmd aparece $\omega_{b,h}$ dentro de discusiones de identificabilidad (aún más sensible a confusión).
- El primer ejemplo “ultra-concreto” (binario $0/1$) aparece recién en 4-ejemplo-a-mano.qmd. Para muchos lectores, ese ejemplo debería existir antes, al introducir el concepto.

**3) Recomendación editorial (lo que conviene cambiar)**
- Introducir un ejemplo aclaratorio *muy temprano* (Cap. 1 y/o Cap. 2) para fijar el concepto antes de entrar en EM y antes de que aparezca la alternancia $w \leftrightarrow \omega$.
- Añadir un recordatorio explícito de equivalencia “$\omega_{b,h}\equiv w_{h,b}$” justo en los capítulos que usan $\omega$ (Cap. 9 y 10), aunque sea en una frase o nota al margen, porque ahí ya no es el momento de reabrir dudas semánticas.

**4) Propuesta concreta: “ejemplos mínimos” sin romper el flujo**
- Cap. 1 (mejor sitio): justo después de la frase definicional de $w_{h,b}$ en 1-problema-variables-latentes.qmd.
  - Formato sugerido: un recuadro/mini-lista de 3 bullets:
    1) Caso didáctico: $w_{h,b}\in\{0,1\}$ (pertenece/no pertenece).
    2) Caso operativo HCP–brick: “nº de visitas” o “tiempo en zona”.
    3) Análogo MMM→MTA: impresiones/GRPs (posiblemente transformadas).
  - Objetivo: que el lector entienda “es oportunidad conocida; puede ser binaria o intensidad; no es un share”.
- Cap. 2 (segundo sitio, aún más “canónico”): inmediatamente después de fijar notación en 2-modelo-base.qmd.
  - Micro-aclaración sugerida (1–2 frases): “en el libro $\omega_{b,h}$ y $w_{h,b}$ son el mismo objeto; no tiene por qué sumar 1; si trabajas con GLM entra como offset vía $\log w$ (ver apéndice)”.
  - Esto “ancla” el símbolo justo cuando el lector aprende la notación fija.

Si quieres, puedo redactar esas dos inserciones como texto editorial listo para pegar (Cap. 1 y Cap. 2) manteniendo el tono actual y sin introducir ideas nuevas (solo material ya presente en 4-ejemplo-a-mano.qmd, 8-caso-de-uso-MTA.qmd y 93-ap-3-exposure.qmd).