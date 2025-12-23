---
tags:
  - calculus
parent: "[[integration techniques]]"
type: permanent
---

Integration by substitution (also called **u-substitution**) is one of the most powerful tools in calculus. You can think of it as the **reverse of the [[derivatives chain rule]] ** for differentiation.

Its goal is to simplify a messy, complex integral by changing the variable from $x$ to a new variable, usually $u$.

## The Core Concept

The method works best when your integral contains a composite function $f(g(x))$ *multiplied* by the derivative of the "inside" function $g'(x)$.

The formal formula is:

$$
\int f(g(x)) \cdot g'(x) \, dx = \int f(u) \, du
$$

Where:
* $u = g(x)$ (The "inside" function)
* $du = g'(x) \, dx$ (The derivative of the inside function)

---

## The Step-by-Step Method

Here is the standard workflow to solve an integral using substitution:

1.  **Choose $u$:** Look for a function inside another function (e.g., inside a power, a square root, a sine, or an exponent). Ideally, the derivative of $u$ should also appear somewhere in the integrand.
2.  **Differentiate:** Find the differential $du$ by taking the derivative of your chosen $u$.
    $$du = \frac{du}{dx} \cdot dx$$
3.  **Isolate $dx$:** Solve for $dx$ so you can replace it in the original integral.
4.  **Substitute:** Rewrite the entire integral in terms of $u$. **All $x$'s must disappear.**
5.  **Integrate:** Solve the new, simpler integral with respect to $u$.
6.  **Back-Substitute:** If it is an *indefinite* integral, replace $u$ back with the original expression in terms of $x$.

---

#### Example 1: Indefinite Integral

**Problem:** Calculate $\int 2x(x^2 + 1)^4 \, dx$

**1. Choose $u$:**
The "inside" function is usually the complex part inside the parentheses.
Let $u = x^2 + 1$.

**2. Differentiate:**
$$\frac{du}{dx} = 2x \implies du = 2x \, dx$$

**3. Substitute:**
Notice that $2x \, dx$ is exactly what we have in the integral. We can replace $(x^2+1)$ with $u$ and $(2x \, dx)$ with $du$.
$$\int (x^2 + 1)^4 \cdot 2x \, dx = \int u^4 \, du$$

**4. Integrate:**
$$\int u^4 \, du = \frac{u^5}{5} + C$$

**5. Back-Substitute:**
Replace $u$ with $(x^2 + 1)$.
$$\text{Answer: } \frac{(x^2 + 1)^5}{5} + C$$

---

#### Example 2: Definite Integral (Changing Bounds)

When dealing with definite integrals (integrals with limits), you must **change the limits of integration** from $x$-values to $u$-values.

**Problem:** Calculate $\int_{0}^{1} x(x^2 + 1)^3 \, dx$

**1. Choose $u$:**
Let $u = x^2 + 1$.

**2. Find $du$:**
$$du = 2x \, dx \implies dx = \frac{du}{2x}$$

**3. Change Limits:**
* **Lower limit:** When $x = 0$, $u = 0^2 + 1 = 1$.
* **Upper limit:** When $x = 1$, $u = 1^2 + 1 = 2$.

**4. Substitute:**
$$\int_{1}^{2} x(u)^3 \cdot \frac{du}{2x}$$
The $x$'s cancel out:
$$\frac{1}{2} \int_{1}^{2} u^3 \, du$$

**5. Integrate and Evaluate:**
(Note: You do *not* back-substitute to $x$ because we changed the bounds to $u$).
$$\frac{1}{2} \left[ \frac{u^4}{4} \right]_{1}^{2}$$
$$= \frac{1}{8} (2^4 - 1^4)$$
$$= \frac{1}{8} (16 - 1) = \frac{15}{8}$$

---

## When to use Substitution
Look for these patterns:
* **Function and its Derivative:** e.g., $\int \cos(x) \sin(x) \, dx$ (Derivative of sine is cosine).
* **Composite Functions:** Expressions like $e^{x^2}$, $\sqrt{5x+2}$, or $\frac{1}{3x-4}$.
* **Logarithmic Forms:** Integrals that look like $\int \frac{g'(x)}{g(x)} \, dx$, which integrate to $\ln|g(x)|$.