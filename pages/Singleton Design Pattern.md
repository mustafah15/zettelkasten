---
title: Singleton Design Pattern
---

- The **singleton pattern** is a type of creational pattern that restricts the instantiation of a class to a **single** object. This allows the class to create an instance of the class the first time it is instantiated. However, on the next try, the existing instance of the class is returned. __No new instance is created__.
id:: c27ef76e-4e1c-4d71-b706-7c07e386b834
	 - Singleton pattern is actually considered an anti-pattern and overuse of it should be avoided. It is not necessarily bad and could have some valid use-cases but should be used with caution because it introduces a global state in your application and change to it in one place could affect the other areas and it could become pretty difficult to debug. The other bad thing about them is it makes your code tightly coupled plus mocking the singleton could be difficult.
id:: 862574eb-1e50-4924-bf75-676f6f6bda47

	 - **When to use the singleton pattern?**
id:: de6d90ee-43f1-4ea0-9929-0130698c74fb
		 - The singleton pattern is mostly used in cases where you want a single object to coordinate actions across a system. Singletons are mostly used by:
id:: 361b56be-51ed-4e9f-b574-76af0150306d
			 - **Services:** services can be singleton since they store the state, configuration, and provide access to resources. Therefore, it makes sense to have a single instance of a service in an application.
id:: 9befa5a4-feed-4914-8ccc-a5ba3a71e04e

			 - **Databases:** when it comes to database connections.
id:: 586c0b63-f082-4cec-9425-e88fc4be9cad

			 - **Configurations:** if there is an object with a specific configuration, you don’t need a new instance every time that configuration object is needed.
id:: 2f145035-5d9d-4fa2-8fda-57332bdbdebe

	 - 
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

	 - 
```javascript
let configure = null;
class ConfigureVals{
    constructor(initvalues){
        this.xpoint = initvalues.xpoint || 0;
        this.ypoint = initvalues.ypoint || 0;
        this.shape = initvalues.shape || null;
    }
    static getConfiguration(initvalues){
        if (!configure) {
            configure = new ConfigureVals(initvalues)
            }
            return configure;
    }
}
// coding config class object
```
id:: 35fed2dd-8939-4716-a774-32a86d38293a
