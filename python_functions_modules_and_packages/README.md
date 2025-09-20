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





### Idiom(Running Code Conditionally in Python Scripts)
 
```python
__name__ == "__main__" 
```

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




### Packages

A package is a collection of modules organized in directories. Packages help you organize related modules into a hierarchy. They contain a special file named `__init__.py`, which indicates that the directory should be treated as a package.

**Example:**

Suppose you have a package structure as follows:

```
/repo/python/          # project root
│
├── main.py                  # entry script
│
└── mymath/                  # package folder
    ├── __init__.py          # exposes add() and sub()
    ├── add_module.py        # contains add()
    └── sub_module.py        # contains sub()
```

# mymath/add_module.py
```python
def add(a, b):
    return a + b

if __name__ == "__main__":
    print(add(3, 5))
```

# mymath/sub_module.py
``` python
def sub(a, b):
    return a - b

if __name__ == "__main__":
    print(sub(5, 3))

```

# mymath/__init__.py
``` python
from .add_module import add
from .sub_module import sub
```
# Import package in main script
``` Python
1. Import the whole package
import mymath 

result = mymath.add(2, 4) 
print(result)

result = mymath.sub(10, 3) 
print(result)
```
``` python 
2. Import a single function
from mymath import add 

result = add(5, 7) 
print(result)
```
``` python
3. Import multiple functions
from mymath import add, sub 

print(add(8, 12)) 
print(sub(20, 5))

```
``` python
4. Import with alias
import mymath as mm 

print(mm.add(3, 3)) 
print(mm.sub(9, 4))

```



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
