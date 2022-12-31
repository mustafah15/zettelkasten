---
title: Decorator pattern
---

- What is the decorator pattern?
id:: bc554fb7-adfc-42b4-9348-8498f05b2fb8
	 - The decorator pattern focuses on adding properties, functionalities, and behavior to existing classes dynamically. The additional decoration functionalities aren’t considered essential enough to be a part of the original class definition as they can cause clutter. Hence, the __decorator pattern__ lets you modify the code without changing the original class.
id:: e99fb00c-02cf-483c-acc6-8571a183a38a

	 - Unlike the creational patterns, the decorator pattern is a structural pattern that does not focus on object creation rather decoration. Hence, it doesn’t rely on prototypal inheritance alone; it takes the object and keeps adding decoration to it. This makes the process more streamlined. 
id:: c7c7f2b2-442f-4c17-b0c5-72179deb9315

	 - In plain words
		 - Decorator pattern lets you dynamically change the behavior of an object at run time by wrapping them in an object of a decorator class.

	 - Wikipedia says
		 - In object-oriented programming, the decorator pattern is a design pattern that allows behaviour to be added to an individual object, either statically or dynamically, without affecting the behaviour of other objects from the same class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows functionality to be divided between classes with unique areas of concern.

	 - When to use the decorator pattern?
id:: a4d7ed65-a4c8-4340-86a7-6f6424d3ec80
		 - JavaScript developers can use the decorator pattern when they want to easily modify or extend the functionality of an object without changing its base code.
id:: 91c8fb48-84a0-4dca-a5e3-647cda3166ee

		 - It can also be used if an application has a lot of distinct objects with the same underlying code. Instead of creating all of them using different subclasses, additional functionalities can be added to the objects using the decorator pattern.
id:: 3d621d51-6b5b-4121-8374-721b85d2ed98

		 - A simple example is __text formatting__, where you need to apply different formattings such as bold, italics, and underline to the same text.
id:: dfeb0fa3-0588-4e95-89f8-a5a3a8986fe4

	 - 
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
id:: 7263b14b-422e-4ef8-bb3d-9476b2e346f8
