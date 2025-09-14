---
tags:
  - calculus
parent: "[[differentiation rules]]"
type: permanent
---
$$
\begin{align}
&\textbf{THEOREM 2—The Chain Rule} \quad \text{If } f(u) \text{ is differentiable at the point } u = g(x) \\
&\text{and } g(x) \text{ is differentiable at } x, \text{ then the composite function } (f \circ g)(x) = f(g(x)) \text{ is} \\
&\text{differentiable at } x, \text{ and} \\[1em]
&\qquad (f \circ g)'(x) = f'(g(x)) \cdot g'(x). \\[1.5em]
&\text{In Leibniz's notation, if } y = f(u) \text{ and } u = g(x), \text{ then} \\[1em]
&\qquad \frac{dy}{dx} = \frac{dy}{du} \frac{du}{dx}, \\[1em]
&\text{where } dy/du \text{ is evaluated at } u = g(x).
\end{align}
$$
“Outside-Inside” Rule
A difficulty with the Leibniz notation is that it doesn’t state specifically where the derivatives in the Chain Rule are supposed to be evaluated. So it sometimes helps to think about the Chain Rule using functional notation. If y= ƒ(g(x)).
In words, differentiate the “outside” function ƒ and evaluate it at the “inside” function g(x) left alone; then multiply by the derivative of the “inside function.”

$$
\begin{align}
&\textbf{\color{red}EXAMPLE} \quad \text{Differentiate } \sin(x^2 + x) \text{ with respect to } x. \\[1.5em]
&\textbf{\color{red}Solution} \quad \text{We apply the Chain Rule directly and find} \\[1em]
&\qquad \frac{d}{dx} \sin(x^2 + x) = \cos(x^2 + x) \cdot (2x + 1). \\[0.5em]
&\qquad\qquad \underbrace{\phantom{(x^2 + x)}}_{\color{blue}\text{inside}} \quad \underbrace{\phantom{(x^2 + x)}}_{\color{blue}\text{inside}} \quad \underbrace{\phantom{(2x + 1)}}_{\color{blue}\text{derivative of}} \\
&\qquad\qquad\qquad\qquad\quad \color{blue}\text{left alone} \quad \color{blue}\text{the inside}
\end{align}
$$
#### Power Chain Rule

$$
\frac{d}{dx}(u^n) = nu^{n-1}\frac{du}{dx}, \qquad\qquad \frac{d}{du}(u^n) = nu^{n-1}
$$

The Power Chain Rule simplifies computing the derivative of a power of an expression.
$$
\begin{align}
&\textbf{\color{red}EXAMPLE} \\[1em]
\text{(a)} \quad \frac{d}{dx}(5x^3 - x^4)^7 &= 7(5x^3 - x^4)^6 \frac{d}{dx}(5x^3 - x^4) \\[1em]
&= 7(5x^3 - x^4)^6(5 \cdot 3x^2 - 4x^3) \\[1em]
&= 7(5x^3 - x^4)^6(15x^2 - 4x^3)
\end{align}
$$
