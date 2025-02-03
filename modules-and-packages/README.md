<h1>
  <span class="headline">Intermediate Python</span>
  <span class="subhead">Modules and Packages</span>
</h1>

**Learning objective:** By the end of this lesson, students will understand how to create, import, and use modules in Python. They'll also learn about packages and how to organize code into directories.

As your Python projects grow larger and more complex, organizing your code becomes crucial for maintainability and reusability. This is where modules and packages come into play.

# Creating and Importing Modules

A module is a Python file that contains definitions and statements. It allows you to organize related code into a single unit. To create a module, simply save your Python code in a file with a `.py` extension.
For example, let's say we have a file named `math_utils.py` with the following content:

``` python
def square(x):
    return x ** 2

def cube(x):
    return x ** 3
```

To use the functions defined in the `math_utils` module, we need to import it into our main Python script. We can import the entire module or specific functions from the module. Here's an example:

``` python
import math_utils

result1 = math_utils.square(5)
result2 = math_utils.cube(3)

print(result1)  # Output: 25
print(result2)  # Output: 27
```

In this example, we import the entire `math_utils` module using the `import` statement. We can then access the functions defined in the module using the dot notation (`module_name.function_name`).

Alternatively, we can import specific functions from the module using the from keyword:

``` python
from math_utils import square, cube

result1 = square(5)
result2 = cube(3)

print(result1)  # Output: 25
print(result2)  # Output: 27
```

In this case, we import only the `square` and `cube` functions from the `math_utils` module. We can use these functions directly without the module name prefix.

# Built-in and Custom Modules

Python comes with a rich collection of built-in modules that provide a wide range of functionality out of the box. These modules are part of the Python Standard Library and can be imported directly without any additional installation.

Some commonly used built-in modules include:

- **`math`:** Provides mathematical functions and constants.
- **`random`:** Generates pseudo-random numbers and provides random-related utilities.
- **`datetime`:** Handles date and time operations.
- **`os`**: Provides functions for interacting with the operating system.
- **`sys`**: Provides access to system-specific parameters and functions.

In addition to built-in modules, you can create your own custom modules to organize and reuse your code. Custom modules can be shared across different projects or with other developers.

# Packages and Directory Structures

A package is a way to organize related modules into a directory hierarchy. It allows you to group modules logically and avoid naming conflicts.
To create a package, you need to follow a specific directory structure. Here's an example:

``` python
my_package/
    __init__.py
    module1.py
    module2.py
    subpackage/
        __init__.py
        module3.py
```

In this example, `my_package` is the package directory. It contains an `__init__.py` file, which can be empty or contain initialization code for the package. The `module1.py` and `module2.py` files are modules within the package, and the `subpackage` directory is a nested package inside `my_package`.

To use modules from a package, you need to import them using the dot notation. For example:

``` python
from my_package.module1 import some_function
from my_package.subpackage.module3 import another_function
```

The `__init__.py` file plays a special role in packages. It is executed when the package is imported and can contain initialization code, variable definitions, or import statements for the package.

# Importing Modules from Packages

When importing modules from packages, you can use various import styles depending on your needs. Here are a few common import styles:

1. Importing a specific module from a package:

``` python
from package_name import module_name
```

2. Importing a specific function or class from a module in a package:

``` python
from package_name.module_name import function_name, class_name
```

3. Importing an entire package:

``` python
import package_name
```

4. Importing all modules from a package:

``` python
from package_name import *
```

It's generally recommended to use explicit imports (options 1 and 2) to avoid naming conflicts and improve code readability.

By organizing your code into modules and packages, you can create a structured and maintainable codebase. Modules allow you to encapsulate related functionality, while packages provide a hierarchical structure for organizing modules.

# Exercise

Create a module called `geometry` that contains functions for calculating the area and perimeter of various shapes (e.g., circle, rectangle, triangle). Import and use these functions in a separate Python script.
