---
title: Command
---

- What is the command pattern?
id:: 61623546-8e69-4ea3-b68b-e9c75627d847
	 - The **command pattern** allows encapsulation of the requests or operations into separate objects. It decouples the objects that send requests from the objects responsible for executing those requests.
id:: 44b860ef-5081-44dd-b91e-15d3126bdc0c

	 - Consider an example where the client is accessing the methods of an API directly throughout the application. What will happen if the implementation of that API changes? The change will have to be made everywhere the API is being used. __To avoid this, we could make use of abstraction and separate the objects requesting from those implementing the request__. Now, if a change occurs, only the object making the call will need to change.
id:: ff35a464-9e68-4084-a2ec-966a518dba83

	 - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FqI0VnWeN05.png?alt=media&token=1a130bee-74e8-4f15-8a3a-81fc4b2fc4df)
id:: 70aa1826-b477-4b94-bccf-35b685dceec4

	 - The diagram above captures the essence of the command pattern:
id:: 29c5f694-14d7-492d-82fa-855fc7c231b7
		 - **Invoker**: asks the command to carry out the request
id:: 3e5eaa57-b8fc-44b7-9cae-367dbbda517a

		 - **Command**: has information about the action and binds it to the __receiver__ by invoking the corresponding operation on it
id:: f81ca585-4524-4682-b9a9-502fc9c32d09

		 - **Receiver**: knows how to perform the operations associated with the command
id:: e94253fd-ebe2-4109-a699-6ce796f7251c

		 - **Client**: creates a command and sets the __receiver__ who’ll receive the command
id:: 6f892330-0bfe-4fc4-abe8-3f0ab46ae22d

	 - In plain words
id:: cfc7f55b-cf85-4404-8af3-259ef161d976
		 - Allows you to encapsulate actions in objects. The key idea behind this pattern is to provide the means to decouple client from receiver.
id:: 1a1d20bd-e3bb-4a16-9702-601589a70e02

	 - Wikipedia says
id:: 5bfb390c-6ccd-40e6-8ecc-bb8470089e71
		 - In object-oriented programming, the command pattern is a behavioural design pattern in which an object is used to encapsulate all information needed to perform an action or trigger an event at a later time. This information includes the method name, the object that owns the method and values for the method parameters.
id:: 399d6626-9980-40a3-9115-78bc8c71a9b9

	 - example 
id:: 7c0569e0-ceed-4bb2-a823-6096be76fd74
		 - 
```javascript
class Command {
  execute() {};
}

//TurnOnPrinter command
class TurnOnPrinter extends Command {
    
    constructor(printingMachine) {
        super();
        this.printingMachine = printingMachine;
        this.commandName = "turn on" 
    }
    
    execute() {
        this.printingMachine.turnOn();
    }
}

//TurnOffPrinter command
class TurnOffPrinter extends Command {

  constructor(printingMachine) {
    super();
    this.printingMachine = printingMachine;
    this.commandName = "turn off" 
  }
  
  execute() {
    this.printingMachine.turnOff();
  }
  
}

//Print command
class Print extends Command {

  constructor(printingMachine) {
    super();
    this.printingMachine = printingMachine;
    this.commandName = "print" 
  }
  
  execute() {
    this.printingMachine.print();
  }
  
}

//Invoker
class PrinterControlPanel {
    pressButton(command) {
        console.log(`Pressing ${command.commandName} button`);
        command.execute();
    }
}

//Reciever: 
class PrintingMachine {

  turnOn() {
    console.log('Printing machine has been turned on');
  }
  
  turnOff() {
    console.log('Printing machine has been turned off');
  }

  print(){
      console.log('The printer is printing your document')
  }
}


const printingMachine = new PrintingMachine();
const turnOnCommand = new TurnOnPrinter(printingMachine);
const turnOffCommand = new TurnOffPrinter(printingMachine);
const printCommand = new Print(printingMachine)
const controlPanel = new PrinterControlPanel();
controlPanel.pressButton(turnOnCommand);
controlPanel.pressButton(turnOffCommand);
controlPanel.pressButton(printCommand);
```
id:: 66eed107-d142-4b3a-9b05-c620e9b2231d

	 - when to use command pattern 
id:: 53aad854-df54-45f3-8d8a-48f3812d81c6
		 - queue and execute requests at different times
id:: 81ec0a4d-a23a-4ad0-836e-fb0370321e57

		 - perform operations such as reset or undo
id:: b3fb5d81-4d06-4493-ba26-235f005c3c6a

		 - keep a history of requests made
id:: a6cbcc3b-2734-4546-9250-29375b917715
