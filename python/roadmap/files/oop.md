# Object-Oriented Programming (OOP)

## Four Pillars of OOP

- `Encapsulation`: Restricting direct access to data. In Python, single underscore _var indicates protected by convention; double underscore __var triggers name mangling (private).

- `Inheritance`: Class inheriting attributes/methods from a parent class using super().

- `Polymorphism`: Subclasses overriding parent methods so identical interfaces behave differently based on object type.

- `Abstraction`: Exposing relevant functionality while hiding implementation details (e.g., using abc.ABC and @abstractmethod).

<br/>

## Class Skeleton & Decorators

```python
class Layer:
    def __init__(self, units):
        self.units = units          # Instance attribute
        self._weights = None        # Encapsulated attribute

    def forward(self, inputs):      # Instance method
        return inputs * self.units

    @classmethod
    def create_dense(cls, units):   # Class factory method
        return cls(units=units)

    @staticmethod
    def activation(x):             # Utility method (no self/cls)
        return max(0, x)           # ReLU
```

- AI Pipeline Connection: OOP underpins framework design in AI (e.g., inheriting from PyTorch's torch.nn.Module or scikit-learn's BaseEstimator to construct custom neural network layers or transformers).

- Common Exam Pitfalls
    - Missing `self`: Forgetting self as the first parameter in instance methods causes `TypeError: method() takes 0 positional arguments but 1 was given.`

    - Not calling `super().__init__()`: Subclasses fail to inherit initialization parameters if the parent constructor isn't explicitly called.
    