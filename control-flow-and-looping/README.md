<h1>
  <span class="headline">Intermediate Python Lecture</span>
  <span class="subhead">Advanced Control Flow and Looping</span>
</h1>

**Learning objective:** By the end of this lesson, students will learn advanced control flow techniques and looping patterns and understand how to use list comprehensions and generator expressions.

Control flow and looping allow you to control the execution of your code based on certain conditions. Python provides several advanced control flow and looping techniques that can help you write more concise and efficient code.

# Nested Loops and Conditional Statements

Nested loops involve placing one loop inside another loop. This is useful when you need to iterate over multiple dimensions or perform actions based on combinations of values. Here's an example:

``` python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"({i}, {j})")
```

In this example, we have two nested `for` loops. The outer loop iterates over the values 1, 2, and 3, while the inner loop iterates over the same values for each iteration of the outer loop. The output will be all the combinations of `(i, j)` where both `i` and `j` range from 1 to 3.

Conditional statements, such as `if`, `elif`, and `else`, can also be nested to create more complex decision-making structures. Here's an example:

``` python
x = 10
y = 20

if x > 5:
    if y > 15:
        print("Both conditions are true")
    else:
        print("Only the first condition is true")
else:
    print("The first condition is false")
```

In this example, we have nested `if` statements. The outer `if` statement checks if `x` is greater than 5. If it is, the inner `if` statement checks if `y`is greater than 15. Depending on the values of `x` and `y`, different messages will be printed.

# Break, Continue, and Pass statements

Python provides three special statements that can be used to control the flow of loops: `break`, `continue`, and `pass`.

The break statement is used to prematurely exit a loop. When encountered, it immediately terminates the loop and transfers the control to the next statement after the loop. Here's an example:

``` python
for i in range(1, 6):
    if i == 4:
        break
    print(i)
```

In this example, the `for` loop iterates over the values 1 to 5. However, when `i` becomes 4, the `break` statement is encountered, and the loop is terminated. The output will be:

``` python
1
2
3
```

The `continue` statement is used to skip the rest of the current iteration and move to the next iteration of the loop. When encountered, it immediately jumps to the next iteration, skipping the remaining code block for the current iteration. Here's an example:

``` python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

In this example, the `for` loop iterates over the values 1 to 5. However, when i becomes 3, the `continue` statement is encountered, and the rest of the code block for that iteration is skipped. The output will be:

``` python
1
2
4
5
```

The `pass` statement is a null operation that does nothing. It is used as a placeholder when a statement is syntactically required but you don't want to execute any code. Here's an example:

``` python
for i in range(1, 6):
    if i == 3:
        pass
    else:
        print(i)
```

In this example, when `i` becomes 3, the `pass` statement is encountered, and nothing happens. The loop continues to the next iteration. The output will be:

``` python
1
2
4
5
```

# List Comprehensions

List comprehensions provide a way to create new lists based on existing lists or other iterable objects. They allow you to combine loops and conditional statements into a single line of code.

The basic syntax of a list comprehension is as follows:

``` python
new_list = [expression for item in iterable if condition]
```

- `expression` is the operation or calculation you want to perform on each item.

- `item` is the variable that represents each element in the iterable.

- `iterable` is the sequence or iterable object you want to iterate over.

- `condition` is an optional filter that specifies a condition to include an item in the new list.

Here's an example that demonstrates the power of list comprehensions:

``` python
numbers = [1, 2, 3, 4, 5]
squared_numbers = [x ** 2 for x in numbers if x % 2 == 0]
print(squared_numbers)  # Output: [4, 16]
```

In this example, we have a list of numbers. We use a list comprehension to create a new list `squared_numbers` that contains the squares of even numbers from the original list. The list comprehension iterates over each number `x` in numbers, squares it (`x ** 2`), and includes it in the new list only if `x` is even (`x % 2 == 0`).

List comprehensions can greatly simplify your code and make it more readable, especially when performing simple operations on lists.

# Iterators and Iterables

In Python, an iterable is an object that can be iterated over, such as a list, tuple, or string. An iterator is an object that represents a stream of data and provides methods for iterating over the elements.

You can create an iterator from an iterable using the `iter()` function. The iterator provides a `next()` method to retrieve the next element from the stream. When there are no more elements, the `next()` method raises the `StopIteration` exception.

Here's an example:

``` python
numbers = [1, 2, 3, 4, 5]
iterator = iter(numbers)
while True:
    try:
        number = next(iterator)
        print(number)
    except StopIteration:
        break
```

In this example, we create an iterator `iterator` from the numbers list using the `iter()` function. We then use a `while` loop to iterate over the elements of the iterator. The `next()` method retrieves the next element from the iterator. When there are no more elements, the `StopIteration` exception is raised, and we break out of the loop.

Iterators and iterables provide a way to work with sequences of data in a memory-efficient manner, as they allow you to retrieve elements one at a time instead of loading the entire sequence into memory.

# Exercise

Use list comprehension to create a new list containing the squares of all even numbers from 1 to 20. Print the resulting list.
