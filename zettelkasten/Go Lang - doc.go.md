---
tags:
  - goLang
type:
  - literature
---
#### `doc.go`: a special file

There is an unofficial convention to write a special file, in each Go package, that will describe the purpose of this package. Almost like a README, but intended for developers only. This file is named `doc.go`, and is called a package header. You’ll find one in most packages you use, if you venture in there.

The `doc.go` file contains no Go code, only one uncommented line: the package. And before that line, a verbose description of what the package is about. This is where we can tell how to properly use the package, in which order to call functions, and what we shouldn’t forget to `defer`, if need be.

The comments prior to the package name should be a multiline comment, where the first line starts with `Package pocketlog`, in our example. The capital matters, for code linters. Write this file, with every piece of information you deem important for the callers of our library. 

```go
/*
Package pocketlog exposes an API to log your work.
 
First, instantiate a logger with pocketlog.New, and giving it a threshold level.
Messages of lesser criticality won't be logged.
 
Sharing the logger is the responsibility of the caller.
 
The logger can be called to log messages on three levels:
  - Debug: mostly used to debug code, follow step-by-step processes
  - Info: valuable messages providing  insights to the milestones of a process
  - Error: error messages to understand what went wrong
*/
package pocketlog
```


#### The `go doc` command

One of the tools Go is shipped with is the `go doc` command. We’ve already mentioned it earlier to inspect the contents of standard packages. This command will give you the documentation of a package or symbol that the `go` command can find in the subdirectories. There is a minor limitation: `go doc` won’t go looking on the internet - it’s a local tool. This means that, in order to use it, you need to be working inside a project (with a `go.mod` file) for which the dependencies will have been downloaded - something that is achieved silently by some IDEs, but that can always be done manually with a `go mod download` command. In our case, we retrieve the documentation of the `pocketlog` package, and of the `New` function in the `pocketlog` package by running `go doc` command

https://go.dev/doc/comment
