# Python Functions, Modules and Packages

## 1. Differences Between Functions, Modules, and Packages

### Functions

A function in Python is a block of code that performs a specific task. Functions are defined using the `def` keyword and can take inputs, called arguments. They are a way to encapsulate and reuse code.

**Example:**

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("Alice")
print(message)
```

In this example, `greet` is a function that takes a `name` argument and returns a greeting message.

### Modules

A module is a Python script containing Python code. It can define functions, classes, and variables that can be used in other Python scripts. Modules help organize and modularize your code, making it more maintainable.

**Example:**

Suppose you have a Python file named `my_module.py`:

```python
# my_module.py
def add(a, b):
    return  a + b
result = add (2, 4)
print(result)
```

You can use this module in another script:

```python
import my_module

result = my_module.add(10, 5)
print(result)

```
In this case, `my_module` is a Python module containing the `add` function and a variable `result`.



### __name__ == "__main__"  Idiom(Running Code Conditionally in Python Scripts)

__name__ == "__main__"
In Python, if __name__ == "__main__": is a common pattern used to distinguish between code that should run when a script is executed directly versus when it is imported as a module.

🔹 1. __name__ – What is it?
In every Python file, there's a built-in variable called __name__.

When a Python file is run directly, __name__ is set to "__main__".

When the same file is imported as a module, __name__ is set to the module's name (like module1, etc.).


🔹 2. The Conditional: if __name__ == "__main__":
This is a conditional check to see whether the current file is being run directly or being imported.

✅ If running the file directly — it runs the code inside the if block.

❌ If the file is imported — it skips the code inside the if block.

## Note: This lets you run certain code only when the file is run directly, not when it's imported

```python
# module1.py

def add(a, b):
    return a + b

print(f"module1 name is: {__name__}")

if __name__ == "__main__":
    result = add(2, 4)
    print("Running directly:", result)
```
When you run module1.py directly:
python3 module1.py

Output
```yaml
module1 name is: __main__
Running directly: 6
```

When you import module1 from another script:

```python
# module2.py

import module1

result = module1.add(10, 2)
print("From module2:", result)
```

python3 module2.py
```pgsql
module1 name is: module1
From module2: 12
```

1. __name__ – What is it?
In every Python file, there's a built-in variable called __name__.

When a Python file is run directly, __name__ is set to "__main__".

When the same file is imported as a module, __name__ is set to the module's name (like module1, math, etc.).




### Packages

A package is a collection of modules organized in directories. Packages help you organize related modules into a hierarchy. They contain a special file named `__init__.py`, which indicates that the directory should be treated as a package.

**Example:**

Suppose you have a package structure as follows:

```
my_package/
    __init__.py
    module1.py
    module2.py
```

You can use modules from this package as follows:

```python
from my_package import module1

result = module1.function_from_module1()
```

In this example, `my_package` is a Python package containing modules `module1` and `module2`.

## 2. How to Import a Package

Importing a package or module in Python is done using the `import` statement. You can import the entire package, specific modules, or individual functions/variables from a module.

**Example:**

```python
# Import the entire module
import math

# Use functions/variables from the module
result = math.sqrt(16)
print(result)

# Import specific function/variable from a module
from math import pi
print(pi)
```

In this example, we import the `math` module and then use functions and variables from it. You can also import specific elements from modules using the `from module import element` syntax.

## 3. Python Workspaces

Python workspaces refer to the environment in which you develop and run your Python code. They include the Python interpreter, installed libraries, and the current working directory. Understanding workspaces is essential for managing dependencies and code organization.

Python workspaces can be local or virtual environments. A local environment is the system-wide Python installation, while a virtual environment is an isolated environment for a specific project. You can create virtual environments using tools like `virtualenv` or `venv`.

**Example:**

```bash
# Create a virtual environment
python -m venv myenv

# Activate the virtual environment (on Windows)
myenv\Scripts\activate

# Activate the virtual environment (on macOS/Linux)
source myenv/bin/activate
```

Once activated, you work in an isolated workspace with its Python interpreter and library dependencies.
