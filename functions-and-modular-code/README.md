<h1>
  <span class="headline">Intermediate Python for Scripting</span>
  <span class="subhead">Functions and Modular Code Organization</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to Understand how to define and use functions in Python and how to write modular and reusable code using functions.

Welcome to the fascinating world of functions in Python! Functions are a fundamental building block of any programming language, and mastering them is crucial for writing clean, reusable, and modular code. 

# Defining and Calling Functions

At its core, a function is a block of code that performs a specific task. It takes input, processes it, and optionally returns a result. In Python, we define a function using the `def` keyword, followed by the function name and a pair of parentheses. Inside the parentheses, we can specify parameters that the function accepts. Here's an example:

``` python
def greet(name):
    print(f"Hello, {name}!")
```

In this example, we define a function called `greet` that takes a parameter `name`. The function body is indented and contains a single line of code that prints a personalized greeting.

To call a function, we simply use its name followed by a pair of parentheses and provide the necessary arguments, if any. For instance, to call the `greet` function, we can do:

``` python
greet("Alice")  # Output: Hello, Alice!
```

# Function Parameters and Arguments

Functions can accept parameters, which are variables that receive the values passed to the function when it is called. Parameters allow functions to be more flexible and reusable by enabling them to work with different data.

In the `greet` function example, `name` is a parameter that accepts a value when the function is called. The value passed to the function is called an argument. In the line `greet("Alice")`, `"Alice"` is the argument that is passed to the name parameter.

Python supports different types of function parameters:

1. **Required parameters**
  These are parameters that must be provided when calling the function. In the greet function, name is a required parameter.

2. **Default parameters**
  We can assign default values to parameters, making them optional. If an argument is not provided for a default parameter, the function uses the default value. Here's an example:

``` python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")
```

  In this modified version of the `greet` function, `greeting` is a default parameter with a default value of `"Hello"`. We can call the function with or without providing a value for `greeting`:

``` python
greet("Alice")  # Output: Hello, Alice!
greet("Bob", "Hi")  # Output: Hi, Bob!
```

3. **Variable-length parameters**
  Python allows functions to accept a variable number of arguments using `*args` and `**kwargs` syntax. `*args` is used to pass a variable number of non-keyword arguments, while `**kwargs` is used to pass a variable number of keyword arguments. Here's an example:

``` python
def sum_numbers(*args):
    total = 0
    for num in args:
        total += num
    return total
```

In this example, the `sum_numbers` function accepts any number of arguments and returns their sum. We can call the function with multiple arguments:

``` python
result = sum_numbers(1, 2, 3, 4, 5)
print(result)  # Output: 15
```

# Return Values and Variable Scope

Functions can return values using the `return` statement. The return statement allows a function to send a value back to the caller and exit the function. Here's an example:

``` python
def square(num):
    return num ** 2
```

In this example, the `square` function takes a number `num` and returns its square using the `return` statement.

When a function is called, a new local scope is created. Variables defined inside a function are local to that function and cannot be accessed from outside the function. Variables defined outside the function, in the global scope, can be accessed inside the function. Here's an example:

``` python
x = 10  # Global variable

def print_x():
    print(x)  # Accessing global variable

def modify_x():
    x = 20  # Local variable
    print(x)

print_x()  # Output: 10
modify_x()  # Output: 20
print(x)  # Output: 10
```

In this example, `x` is a global variable defined outside the functions. The `print_x` function can access and print the value of `x`. The `modify_x` function creates a new local variable `x` and assigns it a value of `20`, which is separate from the global `x`. Modifying the local `x` inside the function does not affect the global `x`.

# Recursive Functions

Recursion is a programming technique where a function calls itself to solve a problem by breaking it down into smaller sub-problems. A recursive function has a base case that determines when the recursion should stop and a recursive case that calls the function with a modified input. Here's an example of a recursive function that calculates the factorial of a number:

```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)
```

In this example, the `factorial` function calculates the factorial of a number `n`. The base case is when `n` is equal to `0`, in which case the function returns `1`. The recursive case multiplies `n` with the factorial of `n - 1`, which is obtained by calling the `factorial` function itself with a smaller input.

Recursive functions can be powerful for solving problems that have a recursive nature, such as traversing tree-like structures or implementing divide-and-conquer algorithms. However, it's important to ensure that the recursive function has a well-defined base case to avoid infinite recursion.

# Best Practices for Writing Functions

When writing functions, it's important to follow best practices to make your code more readable, maintainable, and reusable. Here are some key best practices:

1. **Naming**
  Use descriptive and meaningful names for functions that clearly indicate their purpose. Follow the convention of using lowercase letters and underscores for function names (e.g., `calculate_average`, `get_user_input`).

2. **Single Responsibility Principle**
  Functions should have a single, well-defined responsibility. Each function should do one thing and do it well. Avoid creating functions that have multiple unrelated tasks.

3. **Input Validation**
  Validate the input parameters of a function to ensure they meet the expected criteria. Handle invalid input gracefully and provide appropriate error messages or raise exceptions if necessary.

4. **Commenting**
  Write comments to explain the purpose, parameters, and return values of a function. Use docstrings to provide a clear and concise description of what the function does.

5. **Return Values**
  Functions should return meaningful values that can be used by the caller. Avoid returning `None` or `False` to indicate success or failure. Instead, use exceptions or return explicit values.

6. **Code Reusability**
  Strive to write functions that are modular and reusable. Break down complex tasks into smaller, reusable functions that can be used in different parts of your code.

7. **Testing**
  Test your functions thoroughly to ensure they work as expected. Write unit tests to verify the behavior of individual functions and integration tests to check how functions work together.

By following these best practices, you can write clean, efficient, and maintainable code that leverages the power of functions in Python.

# Exercise

Implement a function called `calculate_average` that takes a list of numbers as input and returns the average of those numbers. Test your function with different input lists.
