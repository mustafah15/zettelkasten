---
tags:
  - calculus
parent: "[[integration techniques]]"
type: permanent
---

Integration by Parts is another fundamental technique of integration. While substitution is the reverse of the Chain Rule, **Integration by Parts is the reverse of the Product Rule.**
which state the following 

$$  \frac{d}{dx}[f(x)g(x)] = f(x)g'(x) + g(x)f'(x). \qquad\qquad $$
It is used when you are integrating the **product of two different types of functions** (e.g., $x$ multiplied by $e^x$, or $x^2$ multiplied by $\sin(x)$).
to see more check [[differentiation rules]]

### The Formula

The formula allows you to trade a difficult integral for an easier one:

$$\int u \, dv = uv - \int v \, du$$

To use this, you must split your original integral into two parts:
1. **$u$**: The part you will **differentiate**.
2. **$dv$**: The part you will **integrate**.

### How to Choose $u$ (The LIATE Rule)

Success depends entirely on choosing the right $u$. If you pick the wrong one, the integral might get harder! Use the **LIATE** acronym to prioritize which function to set as $u$ (choose the one that comes **first** in this list):
1. **L** — **L**ogarithmic functions ($\ln x, \log x$)
2. **I** — **I**nverse Trigonometric functions ($\arcsin x, \arctan x$)
3. **A** — **A**lgebraic functions ($x, x^2, 5x^3$)
4. **T** — **T**rigonometric functions ($\sin x, \cos x$)
5. **E** — **E**xponential functions ($e^x, 3^x$)

_Everything else that is left over becomes $dv$._



### Step-by-Step Example

**Problem:** Calculate $\int x \sin(x) \, dx$

**1. Choose $u$ and $dv$**
- We have $x$ (Algebraic) and $\sin(x)$ (Trigonometric).
- **A** comes before **T** in LIATE, so we choose **$u = x$**
- The rest is $dv$, so **$dv = \sin(x) \, dx$**.

**2. Differentiate $u$ and Integrate $dv$**

- **Differentiate $u$:** $\frac{du}{dx} = 1 \implies du = dx$
- **Integrate $dv$:** $\int dv = \int \sin(x) \, dx \implies v = -\cos(x)$

3. Plug into the Formula

Formula: $\int u \, dv = uv - \int v \, du$

Substitute our parts:

$$\int x \sin(x) \, dx = (x)(-\cos(x)) - \int (-\cos(x)) \, dx$$

**4. Simplify and Solve**

$$= -x \cos(x) + \int \cos(x) \, dx$$

Now, the new integral $\int \cos(x) \, dx$ is easy to solve:

$$= -x \cos(x) + \sin(x) + C$$

