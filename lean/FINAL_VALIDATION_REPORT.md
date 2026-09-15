# Informe de validación

## Veredicto

Formalización parcial. El canal de sustitución de la Observación 1 tiene una
especificación separada y un endpoint de prueba sin `sorry` ni axiomas añadidos.

## Superficie verificada

- Representación explícita de los cuatro factores de la derivada cruzada.
- Signo negativo bajo `Delta_X > 0`, `G(X) > 0`, `lambda_I > 0` y `g'(Y) < 0`.

## Fuera de alcance

- Existencia y estabilidad de los estados estacionarios.
- Construcción del umbral crítico `tauA^c`.
- No monotonicidad global del bienestar.
- Resultados empíricos o afirmaciones causales fuera del modelo.

## Comprobación

El estado de compilación y el comando reproducible se registran en
`status.json`. La ausencia de errores de Lean prueba consistencia sintáctica y
tipada del resultado, no la fidelidad empírica de los supuestos.

Resultado local: `lake build AKO26KnowledgeCollapse` completó correctamente
625 tareas con Lean `v4.30.0-rc2`.
