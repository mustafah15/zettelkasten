---
tags:
  - design-patterns
  - oop
type:
  - fleeting
related: "[[behavioural design patterns]]"
aliases:
  - strategy design pattern
---
- what is sa trategy pattern?

- Consider the example of sorting, We implemented bubble sort but the data started to grow and bubble sort started getting very slow. In order to tackle this we implemented Quick Sort. But now although the quick sort algorithm was doing better for large datasets, it was very slow for smaller datasets. In order to handle this we implemented a strategy where for small datasets, bubble sort will be used, and for larger, quick sort.
- In plain words

- Strategy pattern allows you to switch the algorithm or strategy based on the situation.

- Wikipedia says
>in computer programming, the strategy pattern (also known as the policy pattern) is a behavioural software design pattern that enables an algorithm's behavior to be selected at runtime.


**Programmatic example**

Translating our example from above. First of all we have our strategy interface and different strategy implementations

```PHP
interface SortStrategy
{
    public function sort(array $dataset): array;
}

class BubbleSortStrategy implements SortStrategy
{
    public function sort(array $dataset): array
    {
        echo "Sorting using bubble sort";

        // Do sorting
        return $dataset;
    }
}

class QuickSortStrategy implements SortStrategy
{
    public function sort(array $dataset): array
    {
        echo "Sorting using quick sort";

        // Do sorting
        return $dataset;
    }
}
```

And then we have our client that is going to use any strategy

```PHP
class Sorter
{
    protected $sorterSmall;
    protected $sorterBig;

    public function __construct(SortStrategy $sorterSmall, SortStrategy $sorterBig)
    {
        $this->sorterSmall = $sorterSmall;
        $this->sorterBig = $sorterBig;
    }

    public function sort(array $dataset): array
    {
        if (count($dataset) > 5) {
            return $this->sorterBig->sort($dataset);
        } else {
            return $this->sorterSmall->sort($dataset);
        }
    }
}
```


