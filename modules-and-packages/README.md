<h1>
  <span class="headline">Intermediate Python for Scripting</span>
  <span class="subhead">Modules and Packages</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand how to import and use modules in Python.

## Using built-in modules

Python comes with a rich collection of built-in modules that provide a wide range of functionality out of the box. These modules are part of the Python Standard Library and can be imported directly without any additional installation.

Some commonly used built-in modules include:

- **`math`:** Provides mathematical functions and constants.
- **`random`:** Generates pseudo-random numbers and provides random-related utilities.
- **`datetime`:** Handles date and time operations.
- **`os`**: Provides functions for interacting with the operating system.
- **`sys`**: Provides access to system-specific parameters and functions.

In addition to built-in modules, you can create your own custom modules to organize and reuse your code. Custom modules can be shared across different projects or with other developers.

## Importing modules from packages

When importing modules from packages, you can use various import styles depending on your needs. There are many different input styles, but we'll look at a couple of the most common ones:

### Importing an entire package

The most straightforward way to import a package is to use the `import` statement followed by the package name. This imports the entire package, allowing you to access its functionality.

Syntax:

```python
import package_name
```

Example:

`intermediate_python.py`

```python
import math
```

This imports the entire `math` package, allowing you to access its functions and constants using the `math.` prefix. For example, to calculate the square root of a number, you would use:

`intermediate_python.py`

```python
result = math.sqrt(16)
print(result)  # Output: 4.0
```

### Import a specific module from a package

Syntax:

```python
from package_name import module_name
```

Example:

`intermediate_python.py`

```python
from math import sqrt
```

This imports the `sqrt` function from the `math` module, allowing you to use it directly without prefixing it with `math.`.

By using this syntax, to calculate the square root of a number, you can use    `sqrt()` directly:

`intermediate_python.py`

```python
result = sqrt(25)
print(result)  # Output: 5.0
```

<div class="activity solo-exercise">
  <h2 class="title">Create a custom module</h2>
  <span class="minutes">5 min</span>
</div>

Access the constant `pi` in the `math` module. Print the value of `pi` to the console.
