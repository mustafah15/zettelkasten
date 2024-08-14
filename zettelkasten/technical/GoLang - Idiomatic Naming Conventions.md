---
tags:
  - tools
  - goLang
parent: "[[Go Lang]]"
type: permanent
---
## Variables
a common abbreviation used in go

![[Screenshot 2023-12-24 at 15.13.01.png]]![[Screenshot 2023-12-24 at 15.14.18.png]]

using fewer letters in smaller scopes helps with readability from the GO point of view, but instead using the complete words in larger scopes 

- use mixedCap
- use all capitals for acronyms like API also `userID` to `uid`
- If the variable type is `bool`, its name should start with `Has`, `Is`, `Can` or `Allow`, etc.
- don't use underscore separating for var naming

## Functions and Methods

- Use camel case, exported functions should start with uppercase:

```GO
writeToDB // unexported, only visible within the package
WriteToDB // exported, visible within the package
```
## Constants

- Constant should use all capital letters and use underscore `_` to separate words.

## Files

- Go follows a convention where source files are all lower case with an underscore separating multiple words
- Compound file names are separated with
- _File names that begin with “.” or “_” are ignored by the go tool
- Files with the suffix `_test.go` are only compiled and run by the `go test` tool.