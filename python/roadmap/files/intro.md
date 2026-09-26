# Introduction to Python Programming

- No need `int`, `float`, `str`, `bool`. Python uses dynamic typing like `a = 10` / `name = "Jeral"`

<br/>

- Operators:
    - **Arithmetic**: `+`, `-`, `*`, `/` (float division), `//` (floor division), `%` (modulo), `**` (exponentiation)
    - **Comparison**: `==`, `!=`, `>`, `<`, `>=`, `<=`
    - **Logical**: `and`, `or`, `not` (short-circuit evaluation)

<br/>

- I/O & String Formatting:
    
    - `input()` always returns a string
    - Use `f-strings` for clean output formatting:
    
    ```python
    name = "Loss"
    val = 0.04239
    print(f"Current {name}: {val:.3f}")  # Output: Current Loss: 0.042
    ```

<br/>

- File Handling (CSV Basic I/O):

    ```python
    import csv

    with open('data.csv', mode='r') as file:
        reader = csv.reader(file)
        for row in reader:
            print(row)
    ```

<br/>

- AI Pipeline Connection:

Python is the standard language for AI due to its clear syntax, fast prototyping capability, and direct bindings to high-performance C/C++ backends (e.g., **PyTorch**, **NumPy**)

- Exam Pitfalls:
    - `7 / 2` returns `3.5` (float), while `7 // 2` returns `3` (int).
    - `input()` Type Conversion: Forgetting to cast `input()` to `int` or float when doing math operations results in a `TypeError` or string concatenation bugs (e.g., `"5" + "5"` yields `"55"`).
