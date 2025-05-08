# CTP-EOS Coding Standards

Welcome to the CTP-EOS Linux coding standards guide. These guidelines are designed to ensure consistency, readability, and maintainability of code across our projects. Adhering to these standards will help foster a clean and organized codebase that is easy to work with for all contributors.

---

## General Guidelines

- **Clarity First**: Always prioritize clarity over cleverness. Write code that is easy to understand for others (and yourself in the future).
- **Consistency**: Consistent formatting and style help reduce the mental load of reading the code. Follow the style conventions established here.
- **Small, Modular Functions**: Functions should do one thing, and do it well. Keep functions small and focused on a single task.
- **Descriptive Names**: Use meaningful and descriptive names for variables, functions, classes, and methods. Avoid single-letter names except for loop indices.
- **Commenting and Documentation**: Write comments where necessary to explain why something is being done, especially if it’s not immediately obvious. Use docstrings for all public functions, classes, and methods.

---

## Code Style

### 1. **Indentation and Spacing**

- **Spaces over Tabs**: Use spaces for indentation, **2 spaces per level**.
- **No trailing spaces**: Remove trailing whitespace at the end of lines.
- **Blank Lines**: Use blank lines to separate functions and classes for readability.
  - 2 blank lines before class and function definitions.

```python
# Correct:
def some_function():
  pass
  
  
class MyClass:
  pass
```

- **Avoid excessive blank lines**: Don’t add extra blank lines unless needed for logical grouping.

### 2. **Line Length**

- **Maximum line length**: Limit lines to **80 characters**. This improves readability and makes it easier to view code in smaller windows or on mobile devices.

### 3. **Naming Conventions**

- **Variables**: Use `snake_case` for variable names.
- **Functions**: Use `snake_case` for function names.
- **Classes**: Use `CamelCase` for class names.
- **Constants**: Use `UPPER_CASE` for constants.
- **Modules and filenames**: Use `snake_case` for module and file names.

```python
# Correct:
my_variable = 10
def some_function():
  pass
  
class MyClass:
  pass
  
MY_CONSTANT = 3.14
```

### 4. **String Formatting**

- **Use f-strings (Python 3.6+)** for string interpolation when possible. It's more readable and efficient than other methods.
  
```python
# Correct:
name = "John"
greeting = f"Hello, {name}!"

# Avoid:
greeting = "Hello, {}".format(name)
```

### 5. **Imports**

- **Standard Library imports** first, followed by 3rd-party imports, then local imports. Keep imports sorted alphabetically.

```python
# Correct:
import os
import sys

import requests

from mymodule import my_function
```

### 6. **Error Handling**

- **Always handle exceptions properly**. Do not leave generic `except:` blocks. Always be specific with the exception type.
  
```python
# Correct:
try:
    value = int("123")
except ValueError:
    print("Invalid number format")
```

- **Avoid overuse of exceptions**: Exceptions should only be used for truly exceptional situations, not for control flow.

### 7. **Commenting**

- Use **docstrings** to describe all functions, classes, and methods. The docstring should explain the "what", "why", and "how" of the code.
  
```python
def add_numbers(a, b):
    """
    Adds two numbers together and returns the result.

    Parameters:
    a (int): First number.
    b (int): Second number.

    Returns:
    int: The sum of the two numbers.
    """
    return a + b
```

- Use inline comments sparingly, and only when necessary. If a section of code is self-explanatory, no comment is needed.

### 8. **Version Control**

- **Commit Messages**: Write clear, concise commit messages that describe the "why" behind a change. Use the imperative mood in commit messages (e.g., “Fix bug” or “Add feature”).
  - Follow this format for commit messages:
    ```
    [TYPE] Subject (in present tense)
    
    Detailed explanation of the change if necessary.
    ```
    Example:  
    ```
    [Fix] Resolve null pointer exception in the database module
    ```

- **Branch Naming**: Use descriptive branch names for features or fixes.
  - Use `feature/` for new features, `bugfix/` for bug fixes, and `hotfix/` for urgent fixes.

---

## Python Specific Guidelines

- **PEP 8 Compliance**: Follow [PEP 8](https://pep8.org/) for Python coding style.
- **Avoid Using `from module import *`**: Explicitly import what you need. This makes it clear where each function, variable, or class is coming from.
  
```python
# Correct:
from math import pi, sqrt

# Avoid:
from math import *
```

- **Type Hinting**: Use Python type hints for function signatures.

```python
def add_numbers(a: int, b: int) -> int:
    return a + b
```

---

## Code Review Guidelines

- **Small Pull Requests**: Break down your work into small, manageable pull requests that are easy to review.
- **Explain Your Decisions**: If the code review process brings up concerns, provide explanations for your design choices.
- **Test Your Code**: Ensure that all changes pass the tests before submitting a pull request.

---

## Testing

- **Test-Driven Development (TDD)**: Write tests before implementing code. Test all edge cases and ensure your code behaves as expected.
- **Unit Tests**: Use unit tests to test individual functions and methods.
- **Integration Tests**: Use integration tests to check that the components of your system work together as expected.

```bash
# Run tests using pytest
pytest tests/
```

---

## Documentation

- **README**: Every project should have a clear `README.md` with instructions on how to install, configure, and run the project.
- **Docstrings**: All functions, methods, and classes must have appropriate docstrings explaining their functionality.

---

## Conclusion

These coding standards are here to ensure that all contributors can work in a consistent, efficient, and collaborative environment. Following these practices will help keep the codebase clean and maintainable for years to come.

Thank you for following the CTP-EOS coding standards! Happy coding! 🛸




