# Pytest

Pytest makes writing small, readable tests simple and scales to complex functional testing.

```python
import pytest

# Actual functions
def add(a, b):
    return a + b

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

# Basic Assertion
def test_add():
    assert add(2, 3) == 5

# Expecting Exceptions
def test_divide_by_zero():
    with pytest.raises(ValueError):
        divide(10, 0)

# Parameterized Testing (runs test for multiple inputs)
@pytest.mark.parametrize("a, b, expected", [
    (1, 2, 3),
    (5, 5, 10),
    (-1, 1, 0),
])

def test_add_multiple(a, b, expected):
    assert add(a, b) == expected
```
