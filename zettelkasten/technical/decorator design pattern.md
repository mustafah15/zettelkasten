---
tags:
  - design-patterns
  - software-design
  - oop
type:
  - fleeting
related: "[[structural design patterns]]"
aliases:
  - decorator design pattern
---
- The decorator pattern focuses on adding properties, functionalities, and behavior to existing classes dynamically. The additional decoration functionalities aren’t considered essential enough to be a part of the original class definition as they can cause clutter. Hence, the __decorator pattern__ lets you modify the code without changing the original class.
- Unlike the creational patterns, the decorator pattern is a structural pattern that does not focus on object creation but rather decoration. Hence, it doesn’t rely on prototypal inheritance alone; it takes the object and keeps adding decoration to it. This makes the process more streamlined.
- In plain words

- Decorator pattern lets you dynamically change the behavior of an object at run time by wrapping it in an object of a decorator class.

- Wikipedia says
>In object-oriented programming, the decorator pattern is a design pattern that allows behaviour to be added to an individual object, either statically or dynamically, without affecting the behaviour of other objects from the same class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows functionality to be divided between classes with unique areas of concern.

#### When to use the decorator pattern?

JavaScript developers can use the decorator pattern when they want to easily modify or extend the functionality of an object without changing its base code.
It can also be used if an application has a lot of distinct objects with the same underlying code. Instead of creating all of them using different subclasses, additional functionalities can be added to the objects using the decorator pattern.
A simple example is __text formatting__, where you need to apply different formatting such as bold, italics, and underlining to the same text.


```javascript

class Decorator {

constructor(collection, behaviors, objectIdFields = []) {
    if(_.isNil(collection) || !_.isArray(behaviors) || _.isEmpty(behaviors)) {
        throw new DecoratorIllegalArgumentError('invalid collection or behaviors');
    }

    if(!_.isEmpty(objectIdFields)) {
        this.objectIdFields = objectIdFields;
    }

    this.collection = collection;
    this.behaviors = behaviors;    
}

async insertOne(doc) {
    if(_.isNil(doc)) {
        throw new DecoratorIllegalArgumentError('invalid document');
    }

    for(const aBehavior of this.behaviors) {
        try {
            await aBehavior.beforeInsertOne(doc);
        } catch(error) {
            throw error;
        }
    }

    const result = await this.collection.insertOne(doc);

    return result.ops[0];
}
}
```

