# The Python 3 Programming Language

- [The Python 3 Programming Language](#the-python-3-programming-language)
- [Sources](#sources)
    - [Additional Resources](#additional-resources)
    - [Cheat Sheets](#cheat-sheets)
- [Virtual Environments](#virtual-environments)
    - [Using Virtual Environments](#using-virtual-environments)
- [Python Basics](#python-basics)
  - [Math Data Types](#math-data-types)
    - [Math Operations](#math-operations)
  - [Variables](#variables)
    - [Variable Definition](#variable-definition)
    - [Naming Convensions](#naming-convensions)
  - [Data Types](#data-types)
  - [Escape Sequences](#escape-sequences)
  - [Concatination](#concatination)
    - [Formatting Strings](#formatting-strings)
  - [Boolean and Conditional](#boolean-and-conditional)
    - [Operators](#operators)
      - [Comparison Operators](#comparison-operators)
      - [Logical Operators](#logical-operators)
      - [`is` vs `==`](#is-vs-)
    - [Conditional Statements](#conditional-statements)
  - [Loops](#loops)
    - [`for` Loops](#for-loops)
    - [Ranges](#ranges)
    - [Enumerate](#enumerate)
    - [`while` Loops](#while-loops)
    - [Exiting a Loop in a Controlled Manner](#exiting-a-loop-in-a-controlled-manner)
      - [while](#while)
      - [for](#for)
      - [breaking keywords](#breaking-keywords)

# Sources

[The Modern Python 3 Bootcamp](https://www.udemy.com/course/the-modern-python3-bootcamp/) by [Colt Steele](https://www.udemy.com/user/coltsteele/)

[Zero to Mastery: Complete Python Developer in 2021](https://www.udemy.com/course/complete-python-developer-zero-to-mastery/) by [Andrei Neagoie](https://www.udemy.com/user/andrei-neagoie/)

> Zero to Mastery have opened their own [Academy](https://academy.zerotomastery.io), which has become one of the few learning sources that I use on daily basis.

### Additional Resources

[Built In Functions](https://docs.python.org/3/library/index.html)

[Standard Libraries](https://https://docs.python.org/3/library/index.html)

[Awesome Python](https://github.com/vinta/awesome-python)

[Awesome Python Books](https://github.com/Junnplus/awesome-python-books)

[Free Python Courses](https://github.com/EbookFoundation/free-programming-books/blob/master/courses/free-courses-en.md#python)

### Cheat Sheets

Personal Favorite [devghints.io](https://devhints.io/python)

[github.com/gto76](https://github.com/gto76/python-cheatsheet)

[github.com/aneagoie](https://github.com/aneagoie/ztm-python-cheat-sheet)

# Virtual Environments

Python virtual environment provides an isolated copy of Python. Packages are installed only inside the virtual environment, instead of the system.

```bash
pip3 install virtualenv
```

### Using Virtual Environments

The following commands will create and activate the virtual environment

```bash
python -m venv $PROJECT_NAME

source $PROJECT_NAME/bin/activate
```

You can ensure that you're using the isolated python binary via the `which` command

```bash
which python3
which pip3
```

To deactivate the virtual environment, run the `deactivate` command from your shell

You can reuse the packages that were installed in the virtual environment by exporting them to a file

```bash
# export currently installed packages to requirements.txt file
pip3 freeze --local > requirements.txt
```

and installing them on a different host / inside another virtual environment.

```bash
pip3 install -r /path/to/requirements.txt --user $(whoami)
```

# Python Basics

## Math Data Types

```python
type(9)
# <class 'int'>
```

```python
type(9.0)
# <class 'float'>
```

> If any math equation involves a float, the result will always be a **float**

### Math Operations

`+` addition

`-` subtraction

`*` multiplication

`/` division - **always returns a float**

```py
10/25.0
# 0.4
```

`**` exponential - raise a number to a power

```py
2**19
# 524288
```

`%` modulo - what is the remainder after putting second value into first

```py
10%3
# 1
```

`//` integer division - returns an `int` after division, instead of `float`

```py
10//3
# 3
```

## Variables

### Variable Definition

Python is a [dynamically typed](https://stackoverflow.com/a/1517670) language, meaning you don't have to specify variable type when writing code.

```py
my_var = 199
a_long_variable_that_describes_things = "hi, I'm a variable"
```

you can also define multiple variables at once

```py
var_1, var_2, var_3 = 1, 'tree', 7.0
```

### Naming Convensions

You can find more information in [this detailed guide](https://pythonguides.com/python-naming-conventions/) and in the [PEP8 Style Guide](https://www.python.org/dev/peps/pep-0008/#naming-conventions)

- **variables** should be defined in `snake_case`
- **constants** should be all-caps in `SNAKE_CASE`
- **classes** are usually named using `CamelCase`
- program variables that should not be touched are identified with `__underscores_on_both_sides__`

- variable name must start with an **alphabet** or **underscore** ( `_` ) symbol
- variable names can only contain `A-Z,a-z,0-9` and underscore( `_` ).

## Data Types

Python is a dynamically typed language, which means that data types can be changed when reassigning value.

| Data Type  |                     Definition                     |           Description           |
| :--------: | :------------------------------------------------: | :-----------------------------: |
|  Boolean   |                    `var = True`                    |        `True` or `False`        |
|   String   |                `var = "hello git"`                 |     sequence of characters      |
|  Integer   |                    `var = 2100`                    |           real number           |
|    List    |               `var = [1, 4, "tree"]`               |      an sequence of values      |
| Dictionary | `var = {"name": "artemijs", "surname": "pavlovs"}` | a collection of key:value pairs |

## Escape Sequences

> Escape sequences are used to represent certain special characters within string literals and character literals.

[python.org - String and Bytes literals](https://docs.python.org/3/reference/lexical_analysis.html#string-and-bytes-literals)

```py
"I need to use \"double quotations\" all the time"
# "I need to use "double quotations" all the time"
```

## Concatination

> Joining character strings

```py
string1 = 'hello'
string2 = 'github'
string3 = string1 + " " + string2

print(string3)
# hello github
```

### Formatting Strings

There are 3 ways to format strings in Python

```py
name = "Artemijs"
surname = "Pavlovs"
blog = "blog.artpav.dev"
```

- `f` strings - the preffered way to format strings in Python 3

```py
print(f"Hi there! My name is {name} {surname}, check out my blog at {blog}!")
# Hi there! My name is Artemijs Pavlovs, check out my blog at blog.artpav.dev!
```

- `.format` keyword - used in Python 2.6+

```py
print("Hi there! My name is {} {}, check out my blog at {}!".format(name,surname,blog))
# Hi there! My name is Artemijs Pavlovs, check out my blog at blog.artpav.dev!
```

You can change the order or reuse a value inside the string using index values of the variables.

```py
print("Hi there! My name is {1} {0}, check out my blog at {2}!".format(name,surname,blog))
# Hi there! My name is Artemijs Pavlovs, check out my blog at blog.artpav.dev!
```

- substritution using `%s`

```py
print("Hi there! My name is %s %s, check out my blog at %s!" % (name,surname,blog))
# Hi there! My name is Artemijs Pavlovs, check out my blog at blog.artpav.dev!
```

The substitution approach is not great because you can't reuse values. Value has to be specified for each `%s` special symbol.

## Boolean and Conditional

### Operators

|Comparison Operators|

#### Comparison Operators

| Operator | Explanation                                            |
| :------: | :----------------------------------------------------- |
|   `==`   | True if value `a` **is** equal to value `b`            |
|   `!=`   | True if value `a` **is not** equal to value `b`        |
|   `>`    | True if value `a` **is greater** then value `b`        |
|   `<`    | True if value `a` **is smaller** then value `b`        |
|   `>=`   | True if value `a` **is greater or equal** to value `b` |
|   `<=`   | True if value `a` **is smaller or equal** to value `b` |

#### Logical Operators

`and` - Evaluates to `True` if `a` and `b` are truthy

```py
if weekday and working_hours:
  work()
```

`or` - Evaluates to `True` if `a` or `b` are truthy

```py
if weekend or holiday:
  relax()
```

`not` - Evaluates to `True` if the opposite of the value is true

```py
if not weekend:
  work()
```

#### `is` vs `==`

`==` checks whether the values are the same

```py
a = 1 # assigns value 1 to var 'a'
a == 1
# True
a is 1
# True, because both point to the same location in memory
```

```py
a = [1,2,3,4]
b = [1,2,3,4]
a == b
# True
a is b
# False, because lists were created in different memory locations
```

`is` checks whether the objects are the same and they are located in the same place in memory

```py
b = c
b is c
# True
```

### Conditional Statements

Return a value depending on whether expression returns [Truthy or Falsy](https://www.freecodecamp.org/news/truthy-and-falsy-values-in-python/) values

```py
if True:
    return "What you're saying is absolutely True!"
```

As an example, can be used to return a different greeting, depending on a role.

```py
if role == "Admin":
    print("Greetings, Administrator")
elif role == "User":
    print("Hi there, User!")
else:
    print("Hello, stranger!")
```

## Loops

### `for` Loops

> Performs an action on each item in an [iterable object](https://pythonbasics.org/iterable/)

```py
for item in iterable_object:
    perform_action_on(item)
```

```py
arr = [1,2,3,4]
for item in arr:
    print(item)
```

```py
# OUTPUT:
1
2
3
4
```

### Ranges

> Generates an iterable object consistinf of integers, by default starts from 0 and does not include the last item

```py
rng = range(7)
# creates a range from 0 to 6
for i in rng:
     print(i)
```

```py
# OUTPUT:
0
1
2
3
4
5
6
```

`range(1,9)` - creates a range from 1 to 8

`range(1,10,2)` - creates a range from 1 to 9, jumping forward 2 numbers at a time

`range(1,7,-1)` - creates a range from 7 to 1

### Enumerate

> Take an index value of an iterable object and return index value + object value as key:value pairs

```py
my_string = 'string'
for index, char in enumerate(my_string):
    print(index, char)
```

```py
# OUTPUT:
0 s
1 t
2 r
3 i
4 n
5 g
```

### `while` Loops

> Perform an action while an expression is truthy

```py
value = 1
while value <= 4:
  print(value)
  value +=1
```

```py
# OUTPUT:
1
2
3
4
```

### Exiting a Loop in a Controlled Manner

#### while

```py
while True:
    command = input("type 'exit' to stop this ")
    if command == "exit": # exit the loop if the input is equal to 'exit'
        break
```

```py
# OUTPUT:
type 'exit' to stop this a
type 'exit' to stop this dont stop
type 'exit' to stop this exit
# exits the loop
```

#### for

```py
for x in range(1,103):
	print(x)
	if x == 5: # exit the loop if x is equal to 5
		break
```

#### breaking keywords

`break` - exits from current enclosing loop

`continue` - proceed to the top of the current enclosing loop

`pass` - do nothing
