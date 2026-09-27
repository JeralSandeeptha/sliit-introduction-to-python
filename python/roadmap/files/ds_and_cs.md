# Data Structures and Control Flow

## Core Data Structures

| Structure | Mutable? | Ordered? | Duplicates? | Syntax Example |
| :--- | :--- | :--- | :--- | :--- |
| **List** | Yes | Yes | Yes | `[1, 2, 2, 3]` |
| **Tuple** | No | Yes | Yes | `(1, 2, 2, 3)` |
| **Set** | Yes | No | No | `{1, 2, 3}` |
| **Dictionary** | Keys: No, Values: Yes | Insertion order (3.7+) | Keys: No, Values: Yes | `{"lr": 0.01}` |

<br/>

## Key Operations & Advanced Features

- Set Operations:

```python
set_a = {1, 2, 3}
set_b = {3, 4, 5}
intersection = set_a & set_b  # {3}
union = set_a | set_b         # {1, 2, 3, 4, 5}
difference = set_a - set_b    # {1, 2}
```

<br/>

- Tuple Unpacking:

```python
loss, accuracy = 0.15, 0.98
```

<br/>

- Control Flow & Slicing:

    - Slicing format: `sequence[start:stop:step]` (stop is exclusive).

    - Negative indexing: `sequence[-1]` gets the last element. `sequence[::-1]` reverses a sequence.

<br/>

- AI Pipeline Connection
    - Dictionaries handle hyperparameters (`{"batch_size": 32`, `"epochs": 10}`).

    - Tuples store immutable metadata such as tensor dimensions (`(3, 224, 224)`).

    - Sets perform fast deduplication of text tokens or categorical tags.

<br/>

- Common Exam Pitfalls
    - Dictionary Keys: Keys must be hashable (immutable). Lists and dicts cannot be keys; tuples can.

    - Mutating Sequences in Loops: Modifying a list while iterating over it causes index shifts and skipped elements.