---
tags:
  - tools
type:
  - fleeting
related: "[[PHP]]"
---

PHP 8.1 introduced the feature of readonly property & PHP 8.2 introduced the new feature of `readonly` classes

The concept of `readonly` property in PHP is as simple as when a class property is declared using the `readonly` modifier, you cannot modify the property after initialization.

```PHP
<?php

class User 
{
   public readonly string $name;

   public function __construct(string $name) {
       // Legal initialization.
       $this->name = $name;
   }
}

$john = new User("John");
// Legal read.
var_dump($john->name); // string(4) "John"

// Illegal reassignment. It does not matter that the assigned value is the same.
$john->name = "John";
// Error: Cannot modify readonly property User::$name
?>
```

There are some important notes to remember about readonly properties in PHP.

- You can only apply `readonly` modifier on [typed properties](https://www.php.net/manual/en/language.oop5.properties.php#language.oop5.properties.typed-properties) . A readonly property without type constraints can be created using the [Mixed](https://www.php.net/manual/en/language.types.mixed.php) type.
- You can not assign `readonly` modifier on static properties.
- You can initialize the `readonly` property once, and only from the scope where it has been declared. Any other assignment or modification of the property will result in an Error exception.
-  You can not assign default value on `readonly` properties, because a `readonly` property with a default value is essentially the same as a [[PHP - class constant]], and thus not particularly useful.
- - You can not unset() `readonly` properties once they are initialized. However, it is possible to unset a `readonly` property prior to initialization, from the scope where the property has been declared.
- Not only plain assignments, any type of modification of `readonly` property will also result in an Error exception
- However, objects (or resources) stored in `readonly` properties may still be modified internally
### readonly classes
Now as we got the concept of `readonly property` it will be very easier for us to understand `readonly classes` in PHP.

If we define a class as `readonly` all the declared property of that class will automatically become `readonly` property.

```PHP
readonly class User
{
    public string $name;
    public string $gender;
}
```
So, `User::$name` and `User::$gender` are now `readonly` properties. To achieve this previously in PHP 8.1 we had to do something like:
```PHP
class User
{
    public readonly string $name;
    public readonly string $gender;
}
```

From this observation, we can say that readonly classes are syntactic sugar that will make all the declared properties of that class `readonly` properties.

So, we have to remember that, all those important notes that we described about `readonly` properties are still applicable here. Such as:

1. A `readonly` class can not contain untyped or static properties.
2. A `readonly` class's property cannot have a default value. etc.
3. Another important note to remember about readonly classes is that A readonly class can only be extended if, the child class is also a readonly class.
