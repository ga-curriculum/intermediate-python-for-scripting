<h1>
  <span class="headline">Intermediate Python for Scripting</span>
  <span class="subhead">Function Parameters</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to utilize different types of function parameters, understand variable scope, and follow best practices for writing functions in Python.

## Function parameter types

Python supports different types of function parameters:

### 1. Required parameters

   These are parameters that must be provided when calling the function. In the greet function, name is a required parameter.

### 2. Default parameters

We can assign default values to parameters, making them optional. If an argument is not provided for a default parameter, the function uses the default value. Here's an example:

`intermediate_python.py`

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")
```

In this modified version of the `greet` function, `greeting` is a default parameter with a default value of `"Hello"`. We can call the function with or without providing a value for `greeting`:

`intermediate_python.py`

```python
greet("Alice")
# Prints: Hello, Alice!
greet("Bob", "Hi")
# Prints: Hi, Bob!
```

### 3. Variable-length parameters

Python allows functions to accept a variable number of arguments using `*args` and `**kwargs` syntax. `*args` is used to pass a variable number of non-keyword arguments, while `**kwargs` is used to pass a variable number of keyword arguments. Here's an example:

`intermediate_python.py`

```python
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total
```

In this example, the `sum_numbers` function accepts any number of arguments and returns their sum. We can call the function with multiple arguments:

`intermediate_python.py`

```python
result = sum_numbers(1, 2, 3, 4, 5)
print(result)
# Prints: 15
```

<div class="activity solo-exercise">
  <h2 class="title">Build a flexible function for number operations</h2>
  <span class="minutes">10 min</span>
</div>

Write a function called `process_numbers` that accepts any number of numerical arguments and sums their values.

Experiment with the function by adding your own tests or by modifying the operations performed.
