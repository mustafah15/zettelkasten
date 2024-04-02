---
tags:
  - goLang
---
Sometimes, you want to pass a variable number of parameters to your function - none, exactly one, or more. The best approach in this case is offered by Go’s variadic function syntax. The last argument of a function can be of the type `...{some type}`. When calling such a function, the user can provide any number of parameters - from 0 to too many. Inside the function, we can access the parameters as we would access elements from a slice, using the `[2]` notation.The most used variadic functions are the `fmt.Printf` ones. 

