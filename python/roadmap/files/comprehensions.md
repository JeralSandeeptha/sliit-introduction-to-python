# Comprehensions & Generators

Comprehensions

- List Comprehension: `[expression for item in iterable if condition]`
- Dict Comprehension: `{key_expr: val_expr for item in iterable}`
- Set Comprehension: `{expression for item in iterable}`

```python
# List comprehension with filtering
sq_evens = [x**2 for x in range(10) if x % 2 == 0]

# Dict comprehension
word_len = {word: len(word) for word in ["ai", "python", "model"]}
```

<br/>

## Map, Filter, Zip

- `map(func, iterable)`: Applies function to every item.

- `filter(func, iterable)`: Keeps items where `func(item)` is `True`.

- `zip(iter1, iter2)`: Combines iterables element-by-element into tuples.

<br/>

## Generators (yield)

Generators evaluate lazily (value by value on demand), saving memory compared to storing entire datasets in RAM.

```python
# Generator Function
def batch_generator(data, batch_size):
    for i in range(0, len(data), batch_size):
        yield data[i:i + batch_size]  # Pauses execution and returns value

# Generator Expression
gen_exp = (x**2 for x in range(1000000))  # Uses minimal memory
```

<br/>

## Common Exam Pitfalls

- Exhausting Generators: Generators can only be iterated over once. Once consumed, subsequent iterations yield nothing without re-instantiating.

- Over-nesting Comprehensions: Writing double/triple nested comprehensions damages readability. Fall back to standard loops when complexity increases.
