---
tags:
  - software-design
  - oop
type:
  - fleeting
related: "[[SOLID]]"
---

The **Dependency Inversion Principle (DIP)** states that high-level modules should not depend on low-level modules, but rather both should depend on abstractions. The abstractions should not depend on details. Instead, the details should depend on abstractions.


The DIP reduces the number of dependencies and coupling among modules. It provides a layer of abstraction between lower and higher classes, allowing for changes in the lower class without making changes in the higher class. A few benefits of the DIP are as follows:

- It allows for the flexibility and stability of the software.
- It allows for the reusability of the application modules.
in the example below that violates this dependency inversion as the `PasswordReminder` depends directly on the implementation of `MySQLConnection` 
This breaks the dependency inversion principle as high-level modules  `PasswordReminder`  depend directly on low-level module `MySQLConnection` 

```php

class PasswordReminder {
	public function __construct(private MySQLConnection $dbConnection) {
		
	}
}

```

What are we supposed to do instead? according to the principle, high-level modules should depend on abstraction, not concrete implementation so we will add an interface to make `PasswordReminder`  use or depend on 


```php
interface DBConnection {
	public function connect();
}

class MySQLConnection implements DBConnection {
	public function connect() 
	{
		// implementation
	}
}

class PasswordReminder {
	public function __construct(private DBConnection $dbConnection) {
		
	}
}

```

now let's go to the second part of the rule low-level module too should depend on abstraction that's why `MySQLConnection` implements `DBConnection` 



see more [[inversion of control]]
