---
tags:
  - oop
  - design-patterns
related: "[[creational design patterns]]"
type:
  - literature
---
The builder is a type of creational pattern that helps in building complex objects as It provides a flexible and step-by-step approach towards making these objects. It also keeps the representation and process of creation shielded.

- so when object construction is complicated, provide an API for doing it clearly.
- Consider the example of a restaurant that has to build a pizza for its customers. The building process has various stages
#### When to use
You can use this design pattern when building apps that require you to create complex objects. It can help you hide the construction process of building these objects

A good example would be a DOM, where you might need to create plenty of nodes and attributes. The construction process can get quite messy if you are building a complex DOM object. In cases like these, the builder pattern can be used.

another example is the query builder which requires multiple conditions and criteria before executing the query itself

#### Example 

```typescript
class Pizza {
size!: number;
pepperoni?: bool;
checken?: bool;
tomato?: bool;

constructor({
size,
pepperoni,
checken,
tomato,
}: {
size!: number;
pepperoni?: bool;
checken?: bool;
tomato?: bool;
}) {
this.size = size;
this.pepperoni = pepperoni;
this.checken = checken;
this.tomato = tomato;
}
}

class PizzaBuilder {
size!: number;
pepperoni?: bool;
checken?: bool;
tomato?: bool;

constructor(size) {
this.size = size;
}

addPepperoni()
{
 this.pepperoni = true;
 return this;
}

addChecken()
{
 this.checken = true;
 return this;
}

addTomato()
{
 this.tomato = true;
 return this;
}

build(): Pizza{
return new Pizza({...this});
}
}

let pizze = new PizzaBuilder(10).addTomato().addChecken().build();
```
