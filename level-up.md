## Recursive functions

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