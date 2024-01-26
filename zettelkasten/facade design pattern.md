---
tags:
  - software-design
  - oop
  - design-patterns
type:
  - fleeting
aliases:
  - facade design pattern
related: "[[structural design patterns]]"
---

- what is facade pattern

- the word __facade_ _means a_ _deceptive front or appearance__. Following this definition, a facade pattern provides a simpler interface that hides the complex functionalities of a system. This is widely used in JavaScript libraries like jQuery.
- The facade pattern allows you to hide all the messy logic from the client and only display the clear and easy-to-use interface to them. This allows them to interact with an API easily in a less error-prone way and without accessing the inner workings directly.
- In plain words

**Facade pattern provides a simplified interface to a complex subsystem.**

- Wikipedia says
> A facade is an object that provides a simplified interface to a larger body of code, such as a class library.

- A simple example of the facade pattern is placing an order at a restaurant. Imagine yourself as a customer who wants to eat at a restaurant. You are the client in this scenario. Depending on the place you go to eat, it’s either the waiter will take your order, or you’ll place it at the counter. Then, you’ll wait for a few minutes and the next thing you know, your food will be served.
- How was your food made? Which chef was assigned the task of making your food? What ingredients were used? How much stock was used or left afterward? Who cleaned the kitchen after your food had been prepared? All of these complexities are hidden from you. These are the unnecessary details that you as a customer, don’t need to know.

**Programmatic Example**

Taking our computer example from above. Here we have the computer class

```PHP
class Computer
{
    public function getElectricShock()
    {
        echo "Ouch!";
    }

    public function makeSound()
    {
        echo "Beep beep!";
    }

    public function showLoadingScreen()
    {
        echo "Loading..";
    }

    public function bam()
    {
        echo "Ready to be used!";
    }

    public function closeEverything()
    {
        echo "Bup bup bup buzzzz!";
    }

    public function sooth()
    {
        echo "Zzzzz";
    }

    public function pullCurrent()
    {
        echo "Haaah!";
    }
}
```

Here we have the facade

```PHP
class ComputerFacade
{
    protected $computer;

    public function __construct(Computer $computer)
    {
        $this->computer = $computer;
    }

    public function turnOn()
    {
        $this->computer->getElectricShock();
        $this->computer->makeSound();
        $this->computer->showLoadingScreen();
        $this->computer->bam();
    }

    public function turnOff()
    {
        $this->computer->closeEverything();
        $this->computer->pullCurrent();
        $this->computer->sooth();
    }
}
```

Now to use the facade

```PHP
$computer = new ComputerFacade(new Computer());
$computer->turnOn(); // Ouch! Beep beep! Loading.. Ready to be used!
$computer->turnOff(); // Bup bup buzzz! Haah! Zzzzz
```
