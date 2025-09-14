---
tags:
  - calculus
parent: "[[derivatives]]"
type: permanent
---


A simple rule of differentiation is that the derivative of every constant function is zero.

$$
\begin{align}
&\textbf{Derivative of a Constant Function} \\[0.5em]
&\text{If } f \text{ has the constant value } f(x) = c, \text{ then} \\[1em]
&\qquad \frac{df}{dx} = \frac{d}{dx}(c) = 0.
\end{align}
$$
**Proof**  
We apply the definition of the derivative to f(x)=cf(x) = c f(x)=c, the function whose outputs have the constant value c. At every value of x x, we find that

$$

f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h} = \lim_{h \to 0} \frac{c - c}{h} = \lim_{h \to 0} 0 = 0. \quad 
$$

---

$$
\begin{align}
&\textbf{Power Rule (General Version)} \\[0.5em]
&\text{If } n \text{ is any real number, then} \\[1em]
&\qquad \frac{d}{dx}x^n = nx^{n-1}, \\[1em]
&\text{for all } x \text{ where the powers } x^n \text{ and } x^{n-1} \text{ are defined.}
\end{align}
$$


$$

\begin{align}
&\textbf{Derivative Sum Rule} \\[0.5em]
&\text{If } u \text{ and } v \text{ are differentiable functions of } x, \text{ then their sum } u + v \text{ is differentiable} \\
&\text{at every point where } u \text{ and } v \text{ are both differentiable. At such points,} \\[1em]
&\qquad \frac{d}{dx}(u + v) = \frac{du}{dx} + \frac{dv}{dx}. \\[2em]
&\text{For example, if } y = x^4 + 12x, \text{ then } y \text{ is the sum of } u(x) = x^4 \text{ and } v(x) = 12x. \text{ We} \\
&\text{then have} \\[1em]
&\qquad \frac{dy}{dx} = \frac{d}{dx}(x^4) + \frac{d}{dx}(12x) = 4x^3 + 12.
\end{align}
$$

$$
\begin{align}
&\textbf{Derivative Product Rule} \\[0.5em]
&\text{If } u \text{ and } v \text{ are differentiable at } x, \text{ then so is their product } uv, \text{ and} \\[1em]
&\qquad \frac{d}{dx}(uv) = u\frac{dv}{dx} + v\frac{du}{dx}. \\[2em]
&\text{The derivative of the product } uv \text{ is } u \text{ times the derivative of } v \text{ plus } v \text{ times the deriva-} \\
&\text{tive of } u. \text{ In } \textit{prime notation}, (uv)' = uv' + vu'. \text{ In function notation,} \\[1em]
&\qquad \frac{d}{dx}[f(x)g(x)] = f(x)g'(x) + g(x)f'(x). \qquad\qquad (3)
\end{align}
$$

---

$$
\begin{align} &\textbf{Derivative Division Rule} \\[0.5em] &\text{If } u \text{ and } v \text{ are differentiable at } x \text{ and if } v(x) \neq 0, \text{ then the quotient } u/v \text{ is dif-} \\ &\text{ferentiable at } x, \text{ and} \\[1em] &\qquad \frac{d}{dx}\left(\frac{u}{v}\right) = \frac{v\frac{du}{dx} - u\frac{dv}{dx}}{v^2}. \\[2em] &\text{In function notation,} \\[1em] &\qquad \frac{d}{dx}\left[\frac{f(x)}{g(x)}\right] = \frac{g(x)f'(x) - f(x)g'(x)}{g^2(x)}. \end{align}
$$
---

### [[derivatives chain rule]]
