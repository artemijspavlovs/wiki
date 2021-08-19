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

You can ensure that you're using the isolated python binary using the `which` command

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
$ type(9)
<class 'int'>
```

```python
$ type(9.0)
<class 'float'>
```

> If any math equation involves a float, the result will always be a **float**

### Math Operations

`+` addition

`-` subtraction

`*` multiplication

`/` division - **always returns a float**

```py
$ 10/25.0
0.4
```

`**` exponential - raise a number to a power

```py
$ 2**19
524288
```

`%` modulo - what is the remainder after putting second value into first

```py
$ 10%3
1
```

`//` integer division - returns an `int` after division, instead of `float`

```py
$ 10//3
3
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
