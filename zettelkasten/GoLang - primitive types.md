---
tags:
  - tools
  - goLang
related: "[[Go Lang]]"
type: permanent
---

## Go Primitive types
- boolean type -> default value is 0 / false
- numeric types
	- integers
		- int8 -> -128: 127
		- int16 -> -32 768: 32767
		- int32 -> -2 147 483 648: 2 147 483 647
		- int 64 -> big number 
		- unit8 -> 0: 255
		- unit16 -> 0: 65 535
		- unit32 -> bit number
	- float
	- complex numbers
		- complex64 example `1 + 2i`
		- complex128
		- get the real number part by using `real(var)`
		- get the imaginary part by using `imag(var)`
- text types
	- a `string` is any utf8 character so that makes it very powerful but that means the strings cannot encode every type of character that's available.
		- note that strings also are immutable in go
	- `rune` 
		-  a `string` is any utf32 character
		- can be created by assigning a single cote '' to a variable ex `r := 'a'`
			- runes are just a type alias for int32