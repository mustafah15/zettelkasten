---
title: Visitor
---

- What is the visitor pattern?
id:: b30ee049-4ff6-4518-9848-4ff7aba9b6a1
	 - The visitor pattern allows the definition of new operations to the collection of objects without changing the structure of the objects themselves. This allows us to separate the class from the logic it implements.

	 - The extra operations can be encapsulated in a **visitor** object. The objects can have a **visit** method that accepts the **visitor** object. The **visitor** can then make the required changes and perform the operations on the object that received it. This allows the developers to make future extensions, extend the libraries/frameworks, etc.

	 - In plain words
		 - Visitor pattern lets you add further operations to objects without having to modify them.

	 - Wikipedia says
		 - In object-oriented programming and software engineering, the visitor design pattern is a way of separating an algorithm from an object structure on which it operates. A practical result of this separation is the ability to add new operations to existing object structures without modifying those structures. It is one way to follow the open/closed principle.

	 - When to use the visitor pattern?
		 - Similar operations need to be performed on different objects of a data structure

		 - Specific operations need to be performed on different objects in the data structure

		 - You want to add extensibility to libraries or frameworks

	 - 
```javascript
class Visitor {
    visit(item){}
}

class BookVisitor extends Visitor {
    visit(book) {
        var cost=0; 
        if(book.getPrice() > 50) 
        { 
            cost = book.getPrice()*0.50 
        } 
        else{
            cost = book.getPrice()
        }     
        console.log("Book name: "+ book.getName() + "\n" + "ID: " + book.getID() + "\n" + "cost: "+ cost); 
        return cost; 
    }
}

class Book{
    constructor(id,name,price){
        this.id = id
        this.name = name
        this.price = price
    }
    getPrice(){
        return this.price
    }
    getName(){
        return this.name
    }
    getID(){
        return this.id
    }
    accept(visitor){
        return visitor.visit(this)
    }
}

var visitor = new BookVisitor()
var book1 = new Book("#1234","lordOftheRings",80)
book1.accept(visitor)
```
