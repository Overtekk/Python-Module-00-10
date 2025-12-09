# Python Module 00

#### Here, you will learn the basic of Python, functions, variables, print(), cast, input(), if, elif, range() and some mores.


## 📌 The Norme
You need to respect the norme **Flake8**. You can install it using:
```bash
pip install flake8
```
Use it with:
```bash
python3 -m flake8
```
I advice you to create an alias for it in your .zshrc for example, mine is:
```bash
alias flake8="python3 -m flake8"
```
Don't forget to reload your terminal after that (or `source ~/.zshrc`)

## 🐍 The Language
In Python, we don't use semicolon `;`, we don't use brackets `{` to define blocks of code. Instead, we use **Indentation**.

### 1. Indentation is Law
In C, indentation is just for style/readability (Norminette). In Python, it is **syntax**.
- A block of code (like inside an `if` or a function) starts with a colon `:`.
- Everything inside that block **must** be indented (usually 4 spaces).
- Once you stop indenting, you are out of the block.

```C
C style
if (a > b)
{
  printf("Hello");
}
```
```python
# Python style
if a > b:
    print("Hello") # Inside the if
print("Done")      # Outside the if
```

### 2. No Compilation, Only Interpretation
Forget `cc`, or `make`. Python is an **interpreted language**. You execute the script directly, and the interpreter reads it line by line from top to bottom.
```bash
python3 my_script.py
```
*So, if there is an error line 54, the program might run lines 1-53 before crashing.*

### 3. Variables you will not declare
You don't declare types (`int`, `char *`). Python figures it out for you at runtime. This is called Dynamic Typing.
```python
x = 42          # x is now an Integer
x = "Hello"     # x is now a String (It's possible, but be careful!)
```
> [!CAUTION]
> Just because you can change a variable's type doesn't mean you should. Keep it consistent to avoid confusion.
> Python will let you change whenever you want, but your program *might* not work as expected.

### 4. Printing text is more easy... I think?
Forget `%d`, `%s`, and `ft_printf`. The modern way to print variables inside strings is using **f-strings** (formatted strings). Just put an `f` before the quotes and use `{}` for variables.
```python
name = "Romain"
level = 10

print(f"Player {name} is level {level}")
```
> [!NOTE]
> You can use the old way but it's way better to use `f`.
```python
name = "Romain"
level = 10

print("Player " + name + " is level " + str(level))
```

### 5. Functions you will continue to declare
Obviously, you will need functions to make your code. But instead of writing a return type, here you juste write:
```python
def add(a, b):
    return a + b
```

### 6. You can works now!
Know that you know the basics, you can start coding in Python. I will not teach you how to use range(), how if works, conditions, etc. Python have a large documentation on the internet and it's a very easy to discover things by yourself. Just try before checking code of other people.

---
