---
tags:
  - software-design
  - design-patterns
  - oop
aliases:
  - template method design pattern
type:
  - fleeting
related: "[[design patterns]]"
---
- what is the template method pattern

- The template Method is used prominently in frameworks. Each framework implements the invariant pieces of a domain's architecture and defines "placeholders" for all necessary or interesting client customization options. In so doing, the framework becomes the "centre of the universe", and the client customizations are simply "the third rock from the sun". This inverted control structure has been affectionately labeled "the Hollywood principle" - "don't call us, we'll call you".
- In plain words: The template method defines the skeleton of how a certain algorithm could be performed but defers the implementation of those steps to the children's classes.

- Wikipedia says
>In software engineering, the template method pattern is a behavioral design pattern that defines the program skeleton of an algorithm in an operation, deferring some steps to subclasses. It lets one redefine certain steps of an algorithm without changing the algorithm's structure.


![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fsoftware-architecture%2FAN3dcshEX-.png?alt=media&token=65501f6b-3fb5-48af-913b-a76b235d0f16)




**Programmatic Example**

Imagine we have a build tool that helps us test, lint, build, generate build reports (i.e. code coverage reports, linting report etc) and deploy our app on the test server.

First of all we have our base class that specifies the skeleton for the build algorithm

```PHP
abstract class Builder
{

    // Template method
    final public function build()
    {
        $this->test();
        $this->lint();
        $this->assemble();
        $this->deploy();
    }

    abstract public function test();
    abstract public function lint();
    abstract public function assemble();
    abstract public function deploy();
}
```

Then we can have our implementations

```PHP
class AndroidBuilder extends Builder
{
    public function test()
    {
        echo 'Running android tests';
    }

    public function lint()
    {
        echo 'Linting the android code';
    }

    public function assemble()
    {
        echo 'Assembling the android build';
    }

    public function deploy()
    {
        echo 'Deploying android build to server';
    }
}

class IosBuilder extends Builder
{
    public function test()
    {
        echo 'Running ios tests';
    }

    public function lint()
    {
        echo 'Linting the ios code';
    }

    public function assemble()
    {
        echo 'Assembling the ios build';
    }

    public function deploy()
    {
        echo 'Deploying ios build to server';
    }
}
```

And then it can be used as

```PHP
$androidBuilder = new AndroidBuilder();
$androidBuilder->build();

// Output:
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

$iosBuilder = new IosBuilder();
$iosBuilder->build();

// Output:
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server
```
