---
tags:
  - tools
related: "[[PHP]]"
type:
  - fleeting
---


### Union types [rfc](https://wiki.php.net/rfc/union_types_v2)

Given the dynamically typed nature of PHP, there are lots of cases where union types can be useful. Union types are a collection of two or more types that indicate that either one of those can be used.

```php
public function foo(Foo|Bar $input): int|float;
```

Note that `void` can never be part of a union type, since it indicates "no return value at all". Furthermore, `nullable` unions can be written using `|null`, or by using the existing`?` notation:

```php
public function foo(Foo|null $foo): void;

public function bar(?Bar $bar): void;
```


### JIT [rfc](https://wiki.php.net/rfc/jit)

The JIT — just in time — compiler promises significant performance improvements, albeit not always within the context of web requests. I've done my [own benchmarks](https://stitcher.io/blog/jit-in-real-life-web-applications) on real-life web applications, and it seems like the JIT doesn't make that much of a difference, if any, on those kinds of PHP projects.


### The nullsafe operator [rfc](https://wiki.php.net/rfc/nullsafe_operator)

If you're familiar with the [null coalescing operator](https://stitcher.io/blog/shorthand-comparisons-in-php#null-coalescing-operator) you're already familiar with its shortcomings: it doesn't work on method calls. Instead you need intermediate checks, or rely on `optional` helpers provided by some frameworks:

```php
$startDate = $booking->getStartDate();

$dateAsString = $startDate ? $startDate->asDateTimeString() : null;
```

With the addition of the nullsafe operator, we can now have null coalescing-like behaviour on methods!

```php
$dateAsString = $booking->getStartDate()?->asDateTimeString();
```

### Named arguments [rfc](https://wiki.php.net/rfc/named_params)

[Named arguments](https://stitcher.io/blog/php-8-named-arguments) allow you to pass in values to a function, by specifying the value name, so that you don't have to take their order into consideration, and you can also skip optional parameters!

```php
function foo(string $a, string $b, ?string $c = null, ?string $d = null) 
{ /* … */ }

foo(
    b: 'value b', 
    a: 'value a', 
    d: 'value d',
);
```

### Attributes [rfc](https://wiki.php.net/rfc/attributes_v2)

[Attributes](https://stitcher.io/blog/attributes-in-php-8), commonly known as _annotations_ in other languages, offers a way to add meta data to classes, without having to parse docblocks.

As for a quick look, here's an example of what attributes look like, from the RFC:

```php
use App\Attributes\ExampleAttribute;

#[ExampleAttribute]
class Foo
{
    #[ExampleAttribute]
    public const FOO = 'foo';
 
    #[ExampleAttribute]
    public $x;
 
    #[ExampleAttribute]
    public function foo(#[ExampleAttribute] $bar) { }
}
```

```php
#[Attribute]
class ExampleAttribute
{
    public $value;
 
    public function __construct($value)
    {
        $this->value = $value;
    }
}
```

Note that this base `Attribute` used to be called `PhpAttribute` in the original RFC, but was changed with [another RFC](https://wiki.php.net/rfc/attribute_amendments) afterwards. If you want to take a deep dive in how attributes work, and how you can build your own; you can read about [attributes in depth](https://stitcher.io/blog/attributes-in-php-8) on this blog.


### Match expression [rfc](https://wiki.php.net/rfc/match_expression_v2)

You could call it the big brother of the `switch` expression: `match` can return values, doesn't require `break` statements, can combine conditions, uses strict type comparisons and doesn't do any type coercion.

It looks like this:

```php
$result = match($input) {
    0 => "hello",
    '1', '2', '3' => "world",
};
```


### Constructor property promotion [rfc](https://wiki.php.net/rfc/constructor_promotion)

This RFC adds syntactic sugar to create value objects or data transfer objects. Instead of specifying class properties and a constructor for them, PHP can now combine them into one.

Instead of doing this:

```php
class Money 
{
    public Currency $currency;
 
    public int $amount;
 
    public function __construct(
        Currency $currency,
        int $amount,
    ) {
        $this->currency = $currency;
        $this->amount = $amount;
    }
}
```

You can now do this:

```php
class Money 
{
    public function __construct(
        public Currency $currency,
        public int $amount,
    ) {}
}
```



### Weak maps [rfc](https://wiki.php.net/rfc/weak_maps)

Built upon the [weakrefs RFC](https://wiki.php.net/rfc/weakrefs) that was added in PHP 7.4, a `WeakMap` implementation is added in PHP 8. `WeakMap` holds references to objects, which don't prevent those objects from being garbage collected.

Take the example of ORMs, they often implement caches that hold references to entity classes to improve the performance of relations between entities. These entity objects can not be garbage collected, as long as this cache has a reference to them, even if the cache is the _only_ thing referencing them.

If this caching layer uses weak references and maps instead, PHP will garbage-collect these objects when nothing else references them anymore. Especially in the case of ORMs, which can manage several hundreds, if not thousands of entities within a request; weak maps can offer a better, more resource-friendly way of dealing with these objects.

Here's what weak maps look like, an example from the RFC:

```php
class Foo 
{
    private WeakMap $cache;
 
    public function getSomethingWithCaching(object $obj): object
    {
        return $this->cache[$obj]
           ??= $this->computeSomethingExpensive($obj);
    }
}
```

