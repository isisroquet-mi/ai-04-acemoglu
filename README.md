# Repositorio 4 — Acemoglu, Kong y Ozdaglar (2026)

## Paper trabajado

**Acemoglu, D., Kong, D., & Ozdaglar, A. (2026). _AI, Human Cognition and Knowledge Collapse_. NBER Working Paper No. 34910.**

Este repositorio trabaja el modelo teórico propuesto por Acemoglu, Kong y Ozdaglar sobre los efectos de la IA generativa, especialmente la IA agéntica, sobre el aprendizaje humano y la acumulación de conocimiento colectivo.

La idea central del paper es que la IA puede mejorar las decisiones individuales en el corto plazo, pero también puede reducir los incentivos de las personas a aprender. Si el esfuerzo humano cae, también cae la producción de conocimiento general que sostiene el aprendizaje colectivo en el largo plazo.

---

## 1. Pregunta del paper

El paper pregunta cómo la IA agéntica afecta los incentivos de aprendizaje humano y la evolución del conocimiento colectivo.

En particular, no solo se pregunta si la IA mejora la calidad de las decisiones individuales, sino si esa mejora puede tener un costo dinámico: reducir el esfuerzo humano que alimenta el conocimiento general de la sociedad.

La pregunta puede resumirse así:

$$
\boxed{
\text{¿La IA agéntica mejora las decisiones individuales a costa de debilitar el conocimiento colectivo?}
}
$$

---

## 2. Problema del agente

El modelo considera agentes que deben tomar decisiones o realizar predicciones. Para que una decisión sea exitosa, el agente necesita combinar dos tipos de conocimiento:

$$
\text{conocimiento general} + \text{conocimiento específico del contexto}.
$$

El conocimiento general corresponde al saber compartido por una comunidad. Puede pensarse como conocimiento médico, financiero, técnico o científico acumulado. El conocimiento específico del contexto corresponde a información particular sobre el caso individual que enfrenta el agente.

El agente elige un nivel de esfuerzo $e_{i,t}$. Ese esfuerzo tiene un costo, pero produce información útil. En el modelo, el esfuerzo humano genera dos señales:

1. una señal privada sobre el contexto específico del agente;
2. una señal pública, más delgada, que contribuye al conocimiento general de la comunidad.

La utilidad esperada del agente puede escribirse como:

$$U_{i,t} = f(0,0) + G(X_t)\Delta_G + G(X_t)G(Y_{i,t})\Delta_X- \frac{1}{\alpha}e_{i,t}^{\alpha},\qquad \alpha>1.$$

donde:

$$
Y_{i,t}
= \sigma^{-2}
+\lambda_I e_{i,t}
+\tau_A.
$$

Aquí, $X_t$ representa la precisión del conocimiento general disponible; $Y_{i,t}$ representa la precisión del conocimiento específico del agente; $\tau_A$ mide la precisión de la recomendación de la IA agéntica; y $\Delta_X>0$ captura la complementariedad entre conocimiento general y conocimiento específico.

El punto clave es que el agente internaliza el beneficio privado de aprender sobre su propio contexto, pero no internaliza completamente el beneficio social de contribuir al conocimiento general. Por eso, existe una externalidad de aprendizaje.

---

## 3. Resultado principal y condiciones

El resultado principal del paper es que la IA agéntica genera una tensión entre el corto y el largo plazo.

En el corto plazo, una IA más precisa puede mejorar la información específica del agente y ayudarlo a tomar mejores decisiones. Sin embargo, esa misma precisión reduce el incentivo del agente a realizar esfuerzo propio de aprendizaje.

La tensión central puede expresarse así:

$$
\boxed{
X_t \uparrow \Rightarrow e^* \uparrow
}
$$

pero

$$
\boxed{
\tau_A \uparrow \Rightarrow e^* \downarrow.
}
$$

Es decir, el conocimiento general complementa el esfuerzo humano, mientras que la IA agéntica sustituye ese esfuerzo.

Esta intuición se obtiene a partir de la Observación 1 del paper. El beneficio marginal del esfuerzo es:

$$\frac{\partial U_{i,t}}{\partial e_{i,t}}= \Delta_XG(X_t)\lambda_I g(Y_{i,t})- e_{i,t}^{\alpha-1}.$$

Al derivar respecto al conocimiento general $X_t$, se obtiene:

$$\frac{\partial^2 U_{i,t}} {\partial e_{i,t}\partial X_t}= \Delta_X\lambda_I g(X_t)g(Y_{i,t})>0.$$

Por tanto, el conocimiento general aumenta el retorno marginal del esfuerzo humano.

En cambio, al derivar respecto a la precisión de la IA agéntica $\tau_A$, se obtiene:

$$\frac{\partial^2 U_{i,t}} {\partial e_{i,t}\partial \tau_A}= \Delta_XG(X_t)\lambda_I g'(Y_{i,t})<0.$$

Este signo es negativo porque $g'(Y_{i,t})<0$. Por tanto, una IA agéntica más precisa reduce el retorno marginal del esfuerzo humano.

---

## 4. Bienestar y precisión de la IA

Una respuesta intuitiva sería pensar que una IA más precisa siempre aumenta el bienestar. Sin embargo, el paper muestra que esto no necesariamente ocurre.

El bienestar en el estado estacionario alto puede escribirse como:

$$\bar U^+ =G(\bar X_h)\Delta_G+G(\bar X_h)G(\bar Y_h)\Delta_X-\frac{1}{\alpha}\bar e_h^\alpha.$$

El efecto de aumentar la precisión de la IA tiene dos componentes:

$$\frac{d\bar U^+}{d\tau_A}=\underbrace{G(\bar X_h)\Delta_X g(\bar Y_h)}_{\text{efecto directo positivo}}+ \underbrace{g(\bar X_h)\left[\Delta_G+ G(\bar Y_h)\Delta_X\right]\frac{d\bar X_h}{d\tau_A}}_{\text{efecto indirecto negativo}}.$$

El efecto directo es positivo porque una IA más precisa mejora la información específica del agente. Pero el efecto indirecto es negativo porque una IA más precisa reduce el esfuerzo humano, lo que debilita la acumulación de conocimiento general.

Por eso:

$$
\boxed{
\frac{d\bar U^+}{d\tau_A}
\gtrless
0.
}
$$

En consecuencia, el bienestar no necesariamente aumenta con la precisión de la IA. Puede aumentar al inicio, pero caer cuando la IA se vuelve demasiado precisa y desplaza demasiado el aprendizaje humano.

---

## 5. Supuestos relajados y supuesto no relajado

En la Sección 5, los autores relajan varios supuestos del modelo base.

Primero, relajan el supuesto de que la IA agéntica solo entrega información específica al individuo y no mejora la agregación del conocimiento general. En una extensión, permiten que la IA también aumente la capacidad de agregación $I$.

Segundo, relajan el supuesto de que el conocimiento general nuevo proviene únicamente del esfuerzo humano. Para ello, introducen datos sintéticos, representados por una precisión adicional $\tau_{syn}$.

Tercero, relajan el supuesto de que el esfuerzo humano produce de manera conjunta conocimiento general y conocimiento específico. En la extensión de separabilidad imperfecta, permiten que la contribución del esfuerzo al conocimiento general dependa de $e^\beta$.

Sin embargo, hay un supuesto fuerte del lado de la producción que no relajan de fondo:

$$
\boxed{
\Delta_I=0
\qquad
\text{y}
\qquad
\Delta_X>0.
}
$$

Este supuesto implica que el conocimiento específico por sí solo no genera valor si no está acompañado por conocimiento general. Por eso, el resultado de colapso del conocimiento depende fuertemente de una complementariedad productiva fuerte entre conocimiento general y conocimiento específico.

Una posible crítica es que el paper explora extensiones sobre agregación, datos sintéticos y separabilidad del esfuerzo, pero no analiza qué ocurre si la información específica producida por la IA tiene valor incluso cuando el conocimiento general es bajo, es decir, si $\Delta_I>0$.

---

## 6. Nota sobre la versión leída

Para este repositorio se trabajó como versión principal:

**Acemoglu, D., Kong, D., & Ozdaglar, A. (2026). _AI, Human Cognition and Knowledge Collapse_. NBER Working Paper No. 34910, February 2026.**

Esta versión corresponde a un **working paper del NBER**, por lo que debe tomarse en cuenta que no es un artículo revisado por pares.

Además, se contrastó con otra versión del mismo paper fechada el **5 de mayo de 2026**. Ambas versiones mantienen el mismo título, los mismos autores, el mismo argumento central y una estructura general muy similar. Sin embargo, difieren en la portada, la fecha y algunos aspectos de presentación y notación del modelo.

Por transparencia, la versión declarada como leída y usada para el análisis es la versión **NBER Working Paper No. 34910**.

`prompts.md` is the export of the session that produced the tutorial in `extra/`.
Read it for what it gets wrong as much as for what it gets right. The episode
worth studying is on slide 4 of the presentation: asked for "the most natural
extension", the model confidently proposed relaxing the linear cost — which the
authors had already done in Appendix D. It took opening the appendix to find out.
