# Functions, Modules, and Error Handling

## Functions & Arguments

- Arguments: Positional, Keyword, Default, `*args` (positional tuple), `**kwargs` (keyword dictionary).

```python
def train_model(model_name, *layers, lr=0.001, **config):
    print(f"Model: {model_name}, Layers: {layers}, Config: {config}")

train_model("ResNet", 64, 128, lr=0.01, optimizer="Adam")
# layers = (64, 128), config = {'optimizer': 'Adam'}
```

- Scope Resolution (LEGB Rule): Local $\rightarrow$ Enclosing $\rightarrow$ Global $\rightarrow$ Built-in.

- Lambda Functions: Anonymous single-expression functions:

```python
square = lambda x: x ** 2
```

## Exception Handling

```python
try:
    weights = 1 / gradient
except ZeroDivisionError as e:
    print(f"Gradient vanished: {e}")
    weights = 0
except Exception as e:
    print(f"Generic error: {e}")
finally:
    print("Execution complete.")  # Always runs
```

<br/>

AI Pipeline Connection: Modular code separation prevents script duplication across preprocessing, model initialization, evaluation, and inference.

<br/>

Common Exam Pitfalls: Mutable Default Arguments: Never use a mutable type (`list`, `dict`) as a default argument.

```python
# BAD
def add_sample(sample, dataset=[]):
    dataset.append(sample)
    return dataset
# 'dataset' persists state across function calls! Use dataset=None instead.
```
