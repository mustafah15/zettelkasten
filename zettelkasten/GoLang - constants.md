---
tags:
  - tools
  - goLang
related: "[[Go Lang]]"
type:
  - literature
---
## Naming Convention 
just need to use const word instead of using naming convention like `MY_CONST`
```GO
const myConst int = 42
fmt.Printf("%v, %T\n", myConst, myConst)
```
## Typed Constants

constant can be any [[GoLang - primitive types]]

## Untyped Constants 
the type of the constant would be inferred by the compiler in that case 

## Enumerated Constants 
note that `iota` is scoped to a constant block
see more on iota [here](https://dev.to/ankitmalikg/how-use-iota-in-golang-3hcb#:~:text=iota%20is%20a%20keyword%20in,a%20common%20theme%20or%20sequence.)

```GO
const (
	a = iota
	b
	c
)
const (
	a2 = iota
)

func main() {
	fmt.Printf(a) // 0
	fmt.Printf(b) // 1
	fmt.Printf(c) // 2
	fmt.Printf(a2) // 0
}

```