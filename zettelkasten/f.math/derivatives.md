---
tags:
  - calculus
  - math
parent: "[[calculus]]"
type: permanent
---


$$
```latex
\begin{align}
\textbf{DEFINITIONS} \quad &\text{The slope of the curve } y = f(x) \text{ at the point } P(x_0, f(x_0)) \text{ is the} \\
&\text{number} \\[1em]
&m = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h} \quad \text{(provided the limit exists).} \\[1em]
&\text{The \textbf{tangent line} to the curve at } P \text{ is the line through } P \text{ with this slope.}
\end{align}
```
$$
### Example 

find the slope of the function’s graph at the given point. Then find an equation for the line tangent to the graph there.

- ƒ(x)= x2 + 1, (2, 5)

 Step 1: Apply the Definition of Slope
Using the limit definition: $$m = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$$
Step 2: Calculate f(x₀ + h)
Given: $f(x) = x^2 + 1$

$$f(x_0 + h) = (x_0 + h)^2 + 1$$ $$= x_0^2 + 2x_0h + h^2 + 1$$

Step 3: Set Up the Difference Quotient

$$\frac{f(x_0 + h) - f(x_0)}{h} = \frac{(x_0^2 + 2x_0h + h^2 + 1) - (x_0^2 + 1)}{h}$$

Step 4: Simplify the Numerator

$$= \frac{x_0^2 + 2x_0h + h^2 + 1 - x_0^2 - 1}{h}$$ $$= \frac{2x_0h + h^2}{h}$$

$$= \frac{h(2x_0 + h)}{h} = 2x_0 + h$$ (for h ≠ 0)

Step 5: Take the Limit

$$m = \lim_{h \to 0} (2x_0 + h) = 2x_0$$

**The slope at point (x₀, f(x₀)) is m = 2x₀**

Step 7: Find the Tangent Line Equation

Using point-slope form: $y - y_1 = m(x - x_1)$

At point $(x_0, x_0^2 + 1)$ with slope $m = 2x_0$:

$$y - (x_0^2 + 1) = 2x_0(x - x_0)$$ $$y - x_0^2 - 1 = 2x_0x - 2x_0^2$$ $$y = 2x_0x - 2x_0^2 + x_0^2 + 1$$ $$y = 2x_0x - x_0^2 + 1$$

**General tangent line equation: y = 2x₀x - x₀² + 1**

At point (2, 5)

If we want the tangent line at x₀ = 2:

- **Point**: $(2, f(2)) = (2, 2^2 + 1) = (2, 5)$
- **Slope**: $m = 2(2) = 4$
- **Tangent line**: $y = 2(2)x - 2^2 + 1 = 4x - 4 + 1 = 4x - 3$

**At (2, 5): Slope = 4, Tangent line: y = 4x - 3**


## deeper

### [[differentiation rules]]

### [[derivatives of trigonometric functions]]