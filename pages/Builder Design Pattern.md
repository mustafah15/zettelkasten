---
title: Builder Design Pattern
---

- The builder is a type of creational pattern that helps in building complex objects as It provides a flexible and step-by-step approach towards making these objects. It also keeps the representation and process of creation shielded.
id:: f1e63131-0a5a-483a-a641-c6a30987d8a6
	 - so when object construction is complicated, provide an API for doing it clearly.
id:: 507cacbe-72af-4b66-9d9f-a216f3f415fd

	 - Consider the example of a restaurant that has to build a pizza for its customers. The building process has various stages
id:: 793c1fae-04f3-4251-917c-d02e8f98d698

	 - **When to use**:  You can use this design pattern when building apps that require you to create complex objects. It can help you hide the construction process of building these objects.
id:: 4c0ac02a-183e-482d-9bd9-ef0f6a603d46
		 - A good example would be a DOM, where you might need to create plenty of nodes and attributes. The construction process can get quite messy if you are building a complex DOM object. In cases like these, the builder pattern can be used.
id:: 7c7aa489-0282-458d-b7b4-e32ef2b614f3

		 - another example is the query builder which requires multiple conditions and criteria before executing the query itself 
id:: 9491f668-c2dc-4455-a71f-8b81fee5015a

	 - code example:
id:: eb17b992-d3f9-4b15-861a-fa296f9085e2
		 - 
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
id:: ed69fa76-3645-4b39-8637-b98299505d4e
