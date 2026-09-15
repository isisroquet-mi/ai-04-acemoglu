# Formalización Lean: IA, cognición humana y colapso del conocimiento

Esta carpeta contiene una formalización parcial y reproducible de un resultado
del modelo de Acemoglu, Kong y Ozdaglar (2026).

## Qué verifica Lean

Se formaliza el canal de sustitución de la Observación 1. El retorno marginal
del esfuerzo humano se representa como

\[
\Delta_X G(X)\lambda_I g\!\left(\sigma^{-2}+\lambda_I e+\tau_A\right)
- c'(e).
\]

Lean representa el lado derecho de la derivada cruzada y verifica que

\[
\frac{\partial^2 U}{\partial e\,\partial \tau_A}
= \Delta_X G(X)\lambda_I g'(Y)<0
\]

si `deltaX > 0`, `G(X) > 0`, `lambdaI > 0` y `g'(Y) < 0`. La igualdad
entre la derivada cruzada y ese producto se toma de la traducción matemática
del paper, no se vuelve a derivar desde la función de utilidad.

## Qué no verifica

La carpeta no formaliza todo el paper. En particular, no prueba la existencia
del umbral global `tauA^c`, la dinámica completa de estados estacionarios ni la
forma unimodal del bienestar. El resultado probado es condicional a los signos
y a la diferenciabilidad que el modelo supone.

## Archivos principales

- `AKO26KnowledgeCollapse/PaperInterface.lean`: especificación legible del
  resultado seleccionado.
- `AKO26KnowledgeCollapse/MainTheorems.lean`: definición de la expresión de la
  derivada cruzada y prueba de su signo.
- `AKO26KnowledgeCollapse/ProofInterface.lean`: endpoint que prueba exactamente
  la especificación.
- `docs/FORMALIZATION_PLAN.md`: alcance, correspondencia con el paper y límites.
- `status.json`: estado verificable de la formalización.

## Reproducir

Desde esta carpeta:

```bash
lake update
lake build AKO26KnowledgeCollapse
```

La versión fijada es Lean `v4.30.0-rc2` con Mathlib de la misma versión.
