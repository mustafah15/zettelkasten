---
tags:
  - oop
  - design-patterns
related: "[[creational design patterns]]"
type:
  - literature
---
The **singleton pattern** is a type of creational pattern that restricts the instantiation of a class to a **single** object. This allows the class to create an instance of the class the first time it is instantiated. However, on the next try, the existing instance of the class is returned. __No new instance is created__.

Singleton pattern is actually considered an anti-pattern and overuse of it should be avoided. It is not necessarily bad and could have some valid use-cases but should be used with caution because it introduces a global state in your application and change to it in one place could affect the other areas and it could become pretty difficult to debug. The other bad thing about them is it makes your code tightly coupled plus mocking the singleton could be difficult.

### **When to use the singleton pattern?**
The singleton pattern is mostly used in cases where you want a single object to coordinate actions across a system. Singletons are mostly used by:
- **Services:** services can be singleton since they store the state, configuration, and provide access to resources. Therefore, it makes sense to have a single instance of a service in an application.
- **Databases:** when it comes to database connections.
- **Configurations:** if there is an object with a specific configuration, you don’t need a new instance every time that configuration object is needed.

```typescript
class MyClass
{
	private static _instance: MyClass;
	private constructor()
	{
	    //...
	}
	
	public static get Instance()
	{
	    // Do you need arguments? Make it a regular static method instead.
	    return this._instance || (this._instance = new this());
	}
}

const myClassInstance = MyClass.Instance;

```

