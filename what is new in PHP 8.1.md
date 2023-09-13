---
tags:
  - tools
related: "[[PHP]]"
type:
  - fleeting
---

### Enums [rfc](https://wiki.php.net/rfc/enumerations)

Enums will be added in PHP 8.1! If you're unsure what they can be used for, you can read about them [here](https://stitcher.io/blog/php-enums).

Adding enums would be a significant improvement in PHP, so I for one am very much looking forward to seeing enums arrive in PHP 8.1. To give you a quick preview of what they will look like, here's a code sample:

```php
enum Status {
  case Pending;
  case Active;
  case Archived;
}
```

And this is how they will be used:

```php
class Post
{
    public function __construct(
        private Status $status = Status::Pending;
    ) {}

    public function setStatus(Status $status): void
    {
        // …
    }
}

$post->setStatus(Status::Active);
```

You can find an in-depth analysis of how to use enums in [this post](https://stitcher.io/blog/php-enums).



### Array unpacking with string keys [rfc](https://wiki.php.net/rfc/array_unpacking_string_keys)

Array unpacking was already allowed in [PHP 7.4](https://stitcher.io/blog/new-in-php-74), but it only worked with numeric keys. The reason string keys weren't supported before is because there wasn't any consensus on how to merge array duplicates. The RFC cleanly solves this by following the semantics of `array_merge`:

```php
$array1 = ["a" => 1];

$array2 = ["b" => 2];

$array = ["a" => 0, ...$array1, ...$array2];

var_dump($array); // ["a" => 1, "b" => 2]
```

---


### `new` in initializers [rfc](https://wiki.php.net/rfc/new_in_initializers)

This RFC allows you to use the `new` keyword in function definitions as a default parameter, as well as in attribute arguments and other places.

```php
class MyController {
    public function __construct(
        private Logger $logger = new NullLogger(),
    ) {}
}
```


### Readonly properties [rfc](https://wiki.php.net/rfc/readonly_properties_v2)

Class properties can be marked as readonly, meaning they can only be written once.

```php
class PostData {
    public function __construct(
        public readonly string $title,
        public readonly DateTimeImmutable $date,
    ) {}
}
```

Trying to change a readonly property after it has been initialized will result in an error:

```php
$post = new Post('Title', /* … */);

$post->title = 'Other';

Error: Cannot modify readonly property Post::$title
```

### Pure intersection types [rfc](https://wiki.php.net/rfc/pure-intersection-types)

You already know about [union types in PHP 8.0](https://stitcher.io/blog/new-in-php-8#union-types-rfc), and intersection types are a similar feature. Where union types require the input to be one of the given types, intersection types require the input to be all of the specified types. Intersection types are especially useful when you're working with lots of interfaces:

```php
function generateSlug(HasTitle&HasId $post) {
    return strtolower($post->getTitle()) . $post->getId();
}
```

If you like this style of programming, you'd need to create a new interface `Sluggable` and implement it in `$post`, intersection types get rid of that overhead.

### Final class constants [rfc](https://wiki.php.net/rfc/final_class_const)

Class constants in PHP can be overridden during inheritance:

```php
class Foo
{
    public const X = "foo";
}
 
class Bar extends Foo
{
    public const X = "bar";
}
```

As of PHP 8.1, you can mark such constants as `final` in order to prevent this:

```php
class Foo
{
    final public const X = "foo";
}
 
class Bar extends Foo
{
    public const X = "bar";
    Fatal error: Bar::X cannot override final constant Foo::X
}
```




