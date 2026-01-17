# Python Module 06

#### Here, you will learn how to organize your code into modules and packages, master the art of `import`, understand the role of `__init__.py`, and avoid the trap of circular imports.

## **🐍 Modules & Packages**

In C, you use `#include "header.h"` to link files. In Python, we use Imports.
- A Module is simply a single file ending in .py.
- A Package is a directory containing modules and a special file called `__init__.py`.

### 1. The __init__.py file

This file is what tells Python: *"Hey, this directory is not just a folder, it's a Python Package containing modules you can import!"*.

Without it, you might not be able to import files from that folder properly (depending on your Python version).
- It can be empty (just to mark the directory as a package).
- It can contain code to initialize the package.
- It is executed the moment you import the package.

**Structure example:**
```
my_game/
├── __init__.py
├── player.py
└── level.py
```

### 2. The 3 Ways to Import
There are different ways to bring code from another module into your script. Let's use the `random` library as an example.

#### A. The Generic Import
You import the whole module. To use a function inside it, you must use the dot `.` syntax.
```python
import random

# You must specify 'random.' every time
number = random.randint(1, 10)
print(number)
```

#### B. The Specific Import
You import only what you need. You can use the function directly without the prefix.
```python
from random import randint

# You can use randint directly
number = randint(1, 10)
print(number)
```

#### C. The Alias Import (as)
You import a module or a function but give it a nickname. Very useful for long library names or to avoid conflicts.
```python
from random import randint as r

# 'r' is now the alias for 'randint'
number = r(1, 10)
print(number)
```

### 3. The Danger: Circular Imports 🔄

This is the "Chicken and the Egg" problem of Python.

Imagine two files:
- A.py needs something from B.py -> import B
- B.py needs something from A.py -> import A

When you run `A.py`, it tries to read `B`. `B` tries to read `A` but `A` hasn't finished reading yet! Python crashes (usually with an `ImportError` or `AttributeError`).

[!CAUTION]
> How to avoid this:
- Architecture: If A and B need each other, maybe they should be in the same file, or they should both import a third file `C.py`.
- Deferred Import: Put the import inside the function, not at the top of the file.
```python
def my_function():
    import B  # Only imports when function is called
    B.do_something()
```
