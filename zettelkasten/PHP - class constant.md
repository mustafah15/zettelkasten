---
tags:
  - tools
parent: "[[PHP]]"
type: permanent
---

Sometimes, you need to [define a constant](https://www.phptutorial.net/php-tutorial/php-constants/) that is specific to a [class](https://www.phptutorial.net/php-oop/php-objects/). In this case, you can use the PHP class constants.

To define a constant of a class, you use the `const` keyword. For example:

``` PHP
<?php  

class Circle {
	const PI = M_PI; 
}

```

In this example, we define the `PI` constant in the `Circle` class. By convention, a constant name is in uppercase. If the constant name contains multiple words, you can use the underscore (`_`) to separate the words, for example `MY_CONSTANT`.

Since a constant is defined per class, not per instance of the class, you use the `self` keyword to reference the constant inside the class. For example:


```PHP
class Circle {
	const PI = M_PI;
	private $radius;
	public function __construct(float $radius)
		{         
			$this->radius = $radius;
		 }
	public function area(): float
		{
			 return self::PI * $this->radius ** 2;
		}
}
```


In this example, we define the `Circle` class with the `$radius` property. Inside the `area()` method, we calculate the area of the circle using the radius and the `self::PI` constant.

When you define a constant in a class, its visibility is public by default. It means that you can also access the constant outside of the class.

To reference to the constant outside the class, you use the class name and `::` operator like this:

```PHP
echo Circle::PI;
```

### PHP class constants and inheritance

The following example illustrates how to define a constant in the parent class and override it in the child class. For example:

```PHP
abstract class Model {
	protected const TABLE_NAME = '';
    public static function all()
	{
		 return 'SELECT * FROM ' . static::TABLE_NAME;     
	 } 
 }
class User extends Model {     protected const TABLE_NAME = 'users'; }
class Role extends Model {     protected const TABLE_NAME = 'roles'; }  
echo User::all(); // SELECT * FROM users; echo Role::all(); // SELECT * FROM roles;`

```