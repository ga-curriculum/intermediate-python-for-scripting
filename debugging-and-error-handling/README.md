<h1>
  <span class="headline">Intermediate Python for Scripting</span>
  <span class="subhead">Debugging and Error Handling</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to debug Python code and understand how to handle and raise exceptions.

Debugging and error handling in Python involve identifying and fixing errors in your code and gracefully handling exceptions to prevent program crashes.

# Common Debugging Techniques

Debugging is the process of identifying and fixing errors or bugs in your code. Here are some common debugging techniques you can use:

1. **Print Statements**
  One of the simplest debugging techniques is to use print statements to output the values of variables or to track the flow of execution. By strategically placing print statements at different points in your code, you can observe the intermediate values and identify where the issue might be occurring.

Example:

``` python
def calculate_average(numbers):
    print("Numbers:", numbers)  # Debugging print statement
    total = sum(numbers)
    print("Total:", total)  # Debugging print statement
    average = total / len(numbers)
    print("Average:", average)  # Debugging print statement
    return average
```

2. **Debugging with an IDE**
  Integrated Development Environments (IDEs) like PyCharm, Visual Studio Code, or IDLE provide built-in debugging tools that allow you to set breakpoints, step through your code line by line, inspect variable values, and track the call stack. These debugging features can be extremely helpful in identifying and resolving issues in your code.

3. **Logging**
  Instead of using print statements, you can use Python's built-in `logging` module to log messages at different levels of severity (e.g., debug, info, warning, error). Logging provides a more structured and flexible way to track the execution of your code and can be especially useful for long-running or complex programs.

Example:

``` python
import logging

logging.basicConfig(level=logging.DEBUG)

def calculate_average(numbers):
    logging.debug("Numbers: %s", numbers)
    total = sum(numbers)
    logging.debug("Total: %s", total)
    average = total / len(numbers)
    logging.debug("Average: %s", average)
    return average
```

4. **Debugging with `pdb`**
  Python's built-in `pdb` module provides an interactive debugging environment that allows you to pause the execution of your code, inspect variables, and step through the code line by line. You can insert pdb statements in your code or run your script with the `python -m pdb` command to enter the debugging mode.

Example:

``` python
import pdb

def calculate_average(numbers):
    pdb.set_trace()  # Debugging breakpoint
    total = sum(numbers)
    average = total / len(numbers)
    return average
```

When the `pdb.set_trace()` line is executed, the program will pause, and you can use `pdb` commands to inspect variables, step through the code, and analyze the program's behavior.

These debugging techniques can help you identify and fix issues in your code more efficiently. It's important to choose the technique that suits your specific needs and preferences.

# Handling Exceptions with try-except Blocks

In Python, exceptions are raised when an error occurs during the execution of your code. If an exception is not handled properly, it can cause your program to crash. To gracefully handle exceptions and prevent program termination, you can use try-except blocks.

The basic syntax of a try-except block is as follows:

``` python
try:
    # Code that may raise an exception
except ExceptionType:
    # Code to handle the exception
```

Here's an example that demonstrates exception handling:

``` python
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print("Result:", result)
except ZeroDivisionError:
    print("Error: Cannot divide by zero!")
except ValueError:
    print("Error: Invalid input! Please enter a valid number.")
```

In this example, we attempt to convert user input to an integer and perform a division operation. If the user enters a non-numeric value, a `ValueError` exception will be raised. If the user enters zero, a `ZeroDivisionError` exception will be raised.

The try-except block allows us to catch and handle these exceptions separately. If a `ZeroDivisionError` occurs, the corresponding except block will be executed, and the message "Error: Cannot divide by zero!" will be printed. Similarly, if a `ValueError` occurs, the message "Error: Invalid input! Please enter a valid number." will be printed.

By using try-except blocks, you can handle exceptions gracefully and provide appropriate error messages or take alternative actions instead of letting the program crash.

# Raising Exceptions

In addition to handling exceptions, you can also raise exceptions explicitly in your code using the `raise` statement. This is useful when you want to indicate that a specific condition or error has occurred.

The syntax for raising an exception is as follows:

``` python
raise ExceptionType("Error message")
```

Here's an example that demonstrates raising an exception:

``` python
def calculate_square_root(number):
    if number < 0:
        raise ValueError("Cannot calculate square root of a negative number.")
    return number ** 0.5

try:
    result = calculate_square_root(-4)
    print("Result:", result)
except ValueError as e:
    print("Error:", str(e))
```

In this example, we define a function `calculate_square_root` that calculates the square root of a number. However, if the input number is negative, we raise a `ValueError` exception with a custom error message.
When we call the `calculate_square_root` function with a negative number, the exception is raised. We catch the exception using a try-except block and print the error message using the `str()` function to convert the exception object to a string.

Raising exceptions allows you to indicate and handle specific error conditions in your code and provides a way to communicate and propagate errors to the calling code.

# Creating Custom Exception Classes

Python allows you to define your own custom exception classes to represent specific error conditions in your code. Custom exception classes can inherit from the built-in `Exception` class or any of its subclasses.

Here's an example that demonstrates creating a custom exception class:

``` python
class NegativeNumberError(Exception):
    pass

def calculate_square_root(number):
    if number < 0:
        raise NegativeNumberError("Cannot calculate square root of a negative number.")
    return number ** 0.5

try:
    result = calculate_square_root(-4)
    print("Result:", result)
except NegativeNumberError as e:
    print("Error:", str(e))
```

In this example, we define a custom exception class called `NegativeNumberError` that inherits from the `Exception` class. We don't add any additional functionality to the class, so we use the `pass` statement as a placeholder.

We modify the `calculate_square_root` function to raise the `NegativeNumberError` exception when the input number is negative.

In the try-except block, we catch the `NegativeNumberError` exception specifically and print the error message.

Creating custom exception classes allows you to define more specific and meaningful error conditions in your code, making it easier to handle and communicate errors effectively.

Debugging and error handling are essential skills that will help you identify and resolve issues efficiently and gracefully handle exceptional situations in your programs.

# Exercise

Write a function that takes two numbers as input and divides the first number by the second. Handle the potential ZeroDivisionError exception and print an appropriate error message if the second number is zero.
