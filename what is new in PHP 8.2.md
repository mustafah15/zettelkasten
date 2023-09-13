---
tags:
  - tools
related: "[[PHP]]"
type:
  - fleeting
---


### Readonly classes [rfc](https://wiki.php.net/rfc/readonly_classes)

Readonly properties were [introduced in PHP 8.1](https://stitcher.io/blog/php-81-readonly-properties). This RFC builds on top of them, and adds syntactic sugar to make all class properties readonly at once. Instead of writing this:

```php
class Post
{
    public function __construct(
        public readonly string $title, 
        public readonly Author $author,
        public readonly string $body,
        public readonly DateTime $publishedAt,
    ) {}
}
```

You can now write this:

```php
readonly class Post
{
    public function __construct(
        public string $title, 
        public Author $author,
        public string $body,
        public DateTime $publishedAt,
    ) {}
}
```

Functionally, making a class readonly is entirely the same as making every property readonly; but it will also prevent dynamic properties being added on a class:

```php
$post = new Post(/* … */);

$post->unknown = 'wrong';

Uncaught Error: Cannot create dynamic property Post::$unknown
```

Note that you can only extend from readonly classes if the child class is readonly as well.

PHP has changed quite a lot, and readonly classes are a welcome addition.


### Deprecate dynamic properties [rfc](https://wiki.php.net/rfc/deprecate_dynamic_properties)

I'd say this is a change for the better, but it will hurt a little bit. Dynamic properties are deprecated in PHP 8.2, and will throw an `ErrorException` in PHP 9.0:

```php
class Post
{
    public string $title;
}

// …

$post->name = 'Name';
```

Keep in mind that classes implementing `__get` and `__set` will still work as intended:

```php
class Post
{
    private array $properties = [];
    
    public function __set(string $name, mixed $value): void
    {
        $this->properties[$name] = $value;
    }
}

// …

$post->name = 'Name';
```


### `null`, `true`, and `false` as standalone types [rfc](https://wiki.php.net/rfc/null-false-standalone-types)

PHP 8.2 adds three new types — or something that looks like it. We'll avoid going down the rabbit hole of [type safety](https://stitcher.io/blog/liskov-and-type-safety) in this post, but technically `null`, `true`, and `false` could be considered valid types on their own. Common examples are PHP's built-in functions, where `false` is used as the return type for when an error occurs. For example in `file_get_contents`:

```php
file_get_contents(/* … */): string|false
```

Before PHP 8.2, you could already use `false` together with other types as a union; but now it can be used as a standalone type as well:

```php
function alwaysFalse(): false
{
    return false;
}
```

The same now also goes for `true` and `null`.

### Disjunctive Normal Form Types [rfc](https://wiki.php.net/rfc/dnf_types)

DNF types allow us to combine [union](https://stitcher.io/blog/new-in-php-8#union-types-rfc) and [intersection](https://stitcher.io/blog/new-in-php-81#pure-intersection-types-rfc) types, following a strict rule: when combining union and intersection types, intersection types must be grouped with brackets. In practice, that looks like this:

```php
function generateSlug((HasTitle&HasId)|null $post) 
{
    if ($post === null) {
        return '';
    }

    return 
        strtolower($post->getTitle()) 
        . $post->getId();
}
```

In this case, `(HasTitle&HasId)|null` is the DNF type.

It's a nice addition, especially since it means that we can now have nullable intersection types, which is probably the most important use case for this feature.

### Constants in traits [rfc](https://wiki.php.net/rfc/constants_in_traits)

You can now use constants in traits:

```php
trait Foo 
{
    public const CONSTANT = 1;
 
    public function bar(): int 
    {
        return self::CONSTANT;
    }
}
```

You won't be able to access the constant via the trait's name, either from outside the trait, or from inside it.

```php
trait Foo 
{
    public const CONSTANT = 1;
 
    public function bar(): int 
    {
        return Foo::CONSTANT;
    }
}

Foo::CONSTANT;
```

You can however access the constant via the class that uses the trait, given that it's public:

```php
class MyClass
{
    use Foo;
}

MyClass::CONSTANT; // 1
```


