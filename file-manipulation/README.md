<h1>
  <span class="headline">Intermediate Python for Scripting</span>
  <span class="subhead">File Handling and Read/Write Operations</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to read from and write to files in Python and understand different file handling modes and their use cases.

File handling is an essential skill for any Python programmer. It allows you to read from and write to files, enabling you to store and retrieve data, log information, and interact with external resources.

# Opening and Closing Files

To work with files in Python, you first need to open them. The `open()` function is used to open a file and returns a file object that you can use to read from or write to the file.

The basic syntax for opening a file is as follows:

``` python
file_object = open(file_path, mode)
```

- `file_path` is a string that represents the path to the file you want to open.
mode is a string that specifies the purpose of opening the file. It can be one of the following:

  - `'r'`: Read mode (default). Opens the file for reading.

  - `'w'`: Write mode. Opens the file for writing, truncating the file if it already exists.

  - `'a'`: Append mode. Opens the file for writing, appending to the end of the file if it already exists.

  - `'x'`: Exclusive creation mode. Opens the file for exclusive creation, failing if the file already exists.

  - `'b'`: Binary mode. Used for non-text files, such as images or binary data.

  - `'t'`: Text mode (default). Used for text files.

Here's an example of opening a file in read mode:

``` python
file_object = open('example.txt', 'r')
```

It's important to close the file when you're done with it to free up system resources. You can close a file using the `close()` method:

``` python
file_object.close()
```

# Reading From and Writing To Files

## Reading from Files

Once you have opened a file, you can read its contents using various methods provided by the file object. Here are a few common methods for reading from files:

1. `read()`: Reads the entire contents of the file as a string.

``` python
file_content = file_object.read()
```

2. `readline()`: Reads a single line from the file.

``` python
line = file_object.readline()
```

3. `readlines()`: Reads all the lines of the file and returns them as a list of strings.

``` python
lines = file_object.readlines()
```

You can iterate over the lines of a file using a for loop:

``` python
for line in file_object:
    print(line)
```

Here's an example that demonstrates reading from a file:

``` python
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```

In this example, we use the `with` statement to open the file. The `with` statement automatically takes care of closing the file after the block of code is executed, even if an exception occurs.

## Writing to Files

To write to a file, you open the file in write mode (`'w'`) or append mode (`'a'`) and use the `write()` method to write content to the file.

Here's an example of writing to a file:

``` python
with open('output.txt', 'w') as file:
    file.write('Hello, World!\n')
    file.write('This is a new line.')
```

In this example, we open the file `output.txt` in write mode using the `with` statement. We then use the `write()` method to write two lines of text to the file.

If the file doesn't exist, it will be created. If the file already exists and you open it in write mode, its previous content will be truncated (deleted) before writing the new content.

To append content to an existing file without truncating it, you can open the file in append mode (`'a'`):

``` python
with open('output.txt', 'a') as file:
    file.write('This is an appended line.\n')
```

# File Handling Modes (Read, Write, Append)

In addition to the basic file handling modes (`'r'`, `'w'`, and `'a'`), there are a few more modes you can use:

- `'r+'`: Read and write mode. The file is opened for both reading and writing.

- `'w+'`: Write and read mode. The file is truncated if it exists, otherwise created, and opened for both writing and reading.

- `'a+'`:Append mode with read. The file is opened for both appending and reading.

These modes allow you to perform a combination of reading and writing operations on the file.

# File Handling Best Practices

To ensure safe and efficient file handling in your Python programs, consider the following best practices:

1. Always close files after you're done with them. Using the `with` statement is a convenient way to ensure that files are automatically closed.

2. Handle exceptions that may occur during file operations, such as `FileNotFoundError` or `IOError`. Use `try-except` blocks to catch and handle exceptions gracefully.

3. Be cautious when working with file paths. Use appropriate methods from the `os` module to handle file paths and ensure cross-platform compatibility.

4. Validate user input when dealing with file names or paths to prevent security vulnerabilities, such as path traversal attacks.

5. When working with large files, consider reading or writing data in chunks instead of loading the entire file into memory at once. This can help optimize memory usage and performance.

6. Use appropriate file handling modes based on your requirements. Choose the mode that provides the minimum necessary permissions to perform your desired operations.

# Exercise

Write a Python script that reads the contents of a text file, counts the number of lines, words, and characters, and writes the results to a new file.
