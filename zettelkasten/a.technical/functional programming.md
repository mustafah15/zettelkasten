---
tags:
  - software-design
type: permanent
parent: "[[programming paradigms]]"
aliases:
  - fp
  - FP
---
- **Core Idea**: Treats computation as the evaluation of mathematical functions without changing state or data.
- **Characteristics**:
    - Supports [[higher-order functions]] (functions that operate on other functions).
    - [[pure functions]]
    - 
- **Advantages**:
    - Facilitates parallelism due to immutability.
    - Makes debugging and testing easier with pure functions.
- **Disadvantages**:
    - May be less intuitive for developers accustomed to imperative programming.
    - Recursion can lead to performance issues if not optimised.
- **Examples**: Haskell, Lisp, Scala, Elixir.