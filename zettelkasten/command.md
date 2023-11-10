---
tags:
  - design-patterns
  - oop
  - software-design
type:
  - fleeting
related: "[[design patterns]]"
aliases:
  - command design pattern
---
- The **command pattern** allows encapsulation of the requests or operations into separate objects. It decouples the objects that send requests from the objects responsible for executing those requests.
- Consider an example where the client is accessing the methods of an API directly throughout the application. What will happen if the implementation of that API changes? The change will have to be made everywhere the API is being used. __To avoid this, we could make use of abstraction and separate the objects requesting from those implementing the request__. Now, if a change occurs, only the object making the call will need to change.
![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FqI0VnWeN05.png?alt=media&token=1a130bee-74e8-4f15-8a3a-81fc4b2fc4df)

**Programmatic Example**

First of all we have the receiver that has the implementation of every action that could be performed

```PHP
// Receiver
class Bulb
{
    public function turnOn()
    {
        echo "Bulb has been lit";
    }

    public function turnOff()
    {
        echo "Darkness!";
    }
}
```

then we have an interface that each of the commands are going to implement and then we have a set of commands

```PHP
interface Command
{
    public function execute();
    public function undo();
    public function redo();
}

// Command
class TurnOn implements Command
{
    protected $bulb;

    public function __construct(Bulb $bulb)
    {
        $this->bulb = $bulb;
    }

    public function execute()
    {
        $this->bulb->turnOn();
    }

    public function undo()
    {
        $this->bulb->turnOff();
    }

    public function redo()
    {
        $this->execute();
    }
}

class TurnOff implements Command
{
    protected $bulb;

    public function __construct(Bulb $bulb)
    {
        $this->bulb = $bulb;
    }

    public function execute()
    {
        $this->bulb->turnOff();
    }

    public function undo()
    {
        $this->bulb->turnOn();
    }

    public function redo()
    {
        $this->execute();
    }
}
```

Then we have an `Invoker` with whom the client will interact to process any commands

```PHP
// Invoker
class RemoteControl
{
    public function submit(Command $command)
    {
        $command->execute();
    }
}
```

Finally let's see how we can use it in our client

```PHP
$bulb = new Bulb();

$turnOn = new TurnOn($bulb);
$turnOff = new TurnOff($bulb);

$remote = new RemoteControl();
$remote->submit($turnOn); // Bulb has been lit!
$remote->submit($turnOff); // Darkness!
```

Command pattern can also be used to implement a transaction based system. Where you keep maintaining the history of commands as soon as you execute them. If the final command is successfully executed, all good otherwise just iterate through the history and keep executing the `undo` on all the executed commands.



- when to use command pattern
	- queue and execute requests at different times
	- perform operations such as reset or undo
	- keep a history of requests made