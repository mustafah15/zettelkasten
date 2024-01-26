---
tags:
  - book-notes
  - software-design
related: "[[POSD - choosing names]]"
type:
  - literature
aliases:
  - names should be precise
---
the most common problem with names is that they are too generic or vague; as a result, it's hard for threaders to tell what the name refers to; the reader may assume that the name refers to something different from reality, consider the following method declaration

```c++
/**
* Returns the total number of underlets this object is managing.
*/
int IndexletManager::getCount() {}
```
the term count is too generic: count of what? if someone sees an invocation of this method, they are unlikely to know what it does unless they read its documentation. A more precise name like `getActiveIndexlets` or `numIndexlets` will be better with one of these names, readers will probably be able to guess what the method returns without having to look at its documentation.

like all rules, the rule about choosing precise names has a few exceptions.
- For example, it's fine to use generic names like i and j as loop iteration variables, as long as the loops only span a few lines of code. if you can see the entire range of usage of a variable. The variable's meaning will probably be obvious from the code so you don't need a long name.
- it's also possible for a name to  be too specific, such as in this declaration for a method that deletes a range of text;
```c++
void delete(Range selection) {}
```
- the argument name selection is too specific. since it suggests that the text being deleted is always selected in the user interface. However this method can be invoked on any range of text, selected or not, thus the argument name should be more generic, such as `range`

if you find it difficult to come up with a name for a particular variable that is precise, intuitive, and not too long, this is a red flag. it suggests that the variable may not have a clear definition or purpose. when this happens consider alternative factoring.
### hard to pick a name
if it's hard to find a simple name for a variable or method that creates a clear image of the underlying object, that is a hint that the underlying object may not have a clean design. #[[software design red flags]]
### vague name
if a variable or method name is broad enough to refer to many different things, then it doesn't convey much information to the developer and the underlying entity is more likely to be misused #[[software design red flags]]
