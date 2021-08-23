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
  - [Lists](#lists)
    - [Accessing List Values](#accessing-list-values)
    - [Checking if a list contains a value](#checking-if-a-list-contains-a-value)
    - [Slicing a List](#slicing-a-list)
    - [List Comprehensions](#list-comprehensions)
      - [List Comprehensions with Conditional Logic](#list-comprehensions-with-conditional-logic)
    - [List Methods](#list-methods)
      - [Adding Values to List](#adding-values-to-list)
      - [Removing Values from List](#removing-values-from-list)
      - [Other List Methods](#other-list-methods)
    - [Nested Lists ( Matrix )](#nested-lists--matrix-)
  - [Dictionaries](#dictionaries)
    - [Accessing Dictionary Values](#accessing-dictionary-values)
    - [Adding Values To Dictionary](#adding-values-to-dictionary)
    - [Dictionary Comprehensions](#dictionary-comprehensions)
    - [Dictionary Methods](#dictionary-methods)
      - [Adding Values to Dictionary](#adding-values-to-dictionary-1)
      - [Removing Values from Dictionary](#removing-values-from-dictionary)
      - [Other Dictionary Methods](#other-dictionary-methods)
    - [Using `in` with Dictionaries](#using-in-with-dictionaries)
  - [Tuples](#tuples)
    - [Tuple Methods](#tuple-methods)
  - [Sets](#sets)
    - [Set Comprehensions](#set-comprehensions)
    - [Set Methods](#set-methods)
      - [Adding Values to Sets](#adding-values-to-sets)
      - [Removing values from Sets](#removing-values-from-sets)
      - [Other Set Methods](#other-set-methods)
  - [Ternary Operator](#ternary-operator)
  - [Functions](#functions)
    - [Function Documentation / Doc Strings](#function-documentation--doc-strings)
    - [Scopes](#scopes)
    - [`*args` and `*kwargs`](#args-and-kwargs)
      - [\*args](#args)
      - [\*\*kwargs](#kwargs)
      - [Parameter Ordering](#parameter-ordering)
  - [Built-in Functions](#built-in-functions)
    - [General](#general)
    - [Math](#math)
    - [zips](#zips)
- [Advanced Python](#advanced-python)
  - [Debugging](#debugging)
  - [Modules](#modules)
    - [Module Installation](#module-installation)
    - [`__name__` variable](#__name__-variable)
  - [Object Oriented Programming (OOP)](#object-oriented-programming-oop)
      - [Class](#class)
      - [Object](#object)
    - [Why OOP?](#why-oop)
      - [Abstraction](#abstraction)
      - [Encapsulation](#encapsulation)
    - [Comparison](#comparison)
    - [Class Attribute Definition](#class-attribute-definition)
    - [Hands-on Classes](#hands-on-classes)
      - [Creating a class](#creating-a-class)
      - [Initiating a class](#initiating-a-class)
      - [Adding functionality](#adding-functionality)
      - [Instance attributes](#instance-attributes)
      - [Instance Methods](#instance-methods)
      - [Class Attributes](#class-attributes)
      - [`__repr__` method](#__repr__-method)
      - [Inheritance](#inheritance)
      - [Properties](#properties)
      - [Multiple Inheritance](#multiple-inheritance)
      - [Method Resolution Order ( MRO )'](#method-resolution-order--mro-)
      - [Polymorphism](#polymorphism)
  - [Iterators and Generators](#iterators-and-generators)
    - [Iterators and Iterables](#iterators-and-iterables)
    - [Generators](#generators)
      - [Generator Comprehensions](#generator-comprehensions)
  - [Decorators](#decorators)
    - [Higher Order Function](#higher-order-function)
    - [Decorators](#decorators-1)
      - [Preserving metadata](#preserving-metadata)
  - [Testing](#testing)

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

| Data Type  |                  Definition                   |           Description           |
| :--------: | :-------------------------------------------: | :-----------------------------: |
|  Boolean   |                 `var = True`                  |        `True` or `False`        |
|   String   |              `var = "hello git"`              |     sequence of characters      |
|  Integer   |                 `var = 2100`                  |           real number           |
|    List    |            `var = [1, 4, "tree"]`             |      an sequence of values      |
| Dictionary | `var = {"name": "Johny", "surname": "Bravo"}` | a collection of key:value pairs |

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
name = "Johny"
surname = "Bravo"
blog = "blog.artpav.dev"
```

- `f` strings - the preffered way to format strings in Python 3

```py
print(f"Hi there! My name is {name} {surname}, check out my blog at {blog}!")
# Hi there! My name is Johny Bravo, check out my blog at blog.artpav.dev!
```

- `.format` keyword - used in Python 2.6+

```py
print("Hi there! My name is {} {}, check out my blog at {}!".format(name,surname,blog))
# Hi there! My name is Johny Bravo, check out my blog at blog.artpav.dev!
```

You can change the order or reuse a value inside the string using index values of the variables.

```py
print("Hi there! My name is {1} {0}, check out my blog at {2}!".format(name,surname,blog))
# Hi there! My name is Johny Bravo, check out my blog at blog.artpav.dev!
```

- substritution using `%s`

```py
print("Hi there! My name is %s %s, check out my blog at %s!" % (name,surname,blog))
# Hi there! My name is Johny Bravo, check out my blog at blog.artpav.dev!
```

The substitution approach is not great because you can't reuse values. Value has to be specified for each `%s` special symbol.

## Boolean and Conditional

### Operators

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

## Lists

> Lists are defined using `[]`

### Accessing List Values

List values are exposed using their index value inside the list.

```py
tasks = ["Install Python", "Learn Python", "Take a break"]
print(tasks[0])
# Install Python
```

You can access last items in an array using negative indexes

```py
print(tasks[-1])
# Take a break
```

### Checking if a list contains a value

```py
"procrastinate" in tasks
# False
"Take a break" in tasks
# True
```

### Slicing a List

> `a_list[start:end:step]`

`start` - starting index

`end` - ending index

`step` - number of items to jump

> Creates a new list in memory

```py
countries=["uk", "ru", "us", "lv", "it"]
```

```py
# start from index 1
countries[1:]
# ['ru', 'us', 'lv', 'it']
```

```py
countries[-1:]
# ['it']
```

```py
countries[:2]
# ['uk', 'ru']
```

```py
# reverse a list
countries[::-1]
# ['it', 'lv', 'us', 'ru', 'uk']
```

### List Comprehensions

> One line way to act on an item in an iterable object

`[expression_for_item for item in iterable_object]`

```py
numbers = [0,1,2,3,4,5]
```

```py
# multiply each number by 10
[num*10 for num in numbers]
# [0, 10, 20, 30, 40, 50]
```

```py
# set the bool version of value for each item in the list
[bool(num) for num in numbers]
# [False, True, True, True, True, True]
```

#### List Comprehensions with Conditional Logic

```py
evens = [num for num in numbers if num % 2 == 0]
print(evens)
# [0, 2, 4]
```

```py
# multiply even numbers by 2
# divide odd numbers by 2
[num*2 if num % 2 == 0 else num/2 for num in numbers]
# [0, 0.5, 4, 1.5, 8, 2.5]
```

### List Methods

```py
numbers = [0,1,2,3,4,5]
```

#### Adding Values to List

`.append(value_to_add)` - add **one** value to the end of the list

```py
numbers.append(144)
numbers
# [0, 1, 2, 3, 4, 5, 144]
```

`.extend(values_to_add)` - add **multiple** values to the end of the list

```py
numbers.extend([12,32,44,59])
numbers
# [0, 1, 2, 3, 4, 5, 12, 32, 44, 59]
```

`.insert(index, value)` - add a value into specific location of the list

```py
numbers.insert(2, "something completely new")
numbers
# [0, 1, 'something completely new', 2, 3, 4, 5]
```

#### Removing Values from List

`.clear()` - empty the list

```py
numbers.clear()
numbers
# []
```

`.pop(index)` - remove an item at the provided index from the list, removes last if no index is provided. Returns what value was removed

```py
numbers.pop()
# 5
numbers
# [0, 1, 2, 3, 4]
```

```py
numbers.pop(0)
# 0
numbers
# [1, 2, 3, 4, 5]
```

`.remove(value)` - remove the first occurance of the value you provide

```py
numbers = [0,1,2,4,3,4,5]
numbers.remove(4)
numbers
# [0, 1, 2, 3, 4, 5]
```

#### Other List Methods

`.index(what_to_search_for, starting_index, ending_index)` - get the index of an item

```py
tasks = ["Install Python", "Learn Python", "Take break"]
tasks.index("Learn Python")
# 1
```

```py
numbers = [4,1,2,3,4,1,3,4,1]
print(f"searching between indexes 3 and 7\nlooking for 1,\nfound 1 at index {numbers.index(1,3,7)}")
# searching between indexes 3 and 7
# looking for 1,
# found 1 at index 5
```

`.count(value)` - return the number reoccurrences that a value has in the list

```py
nums = [4,1,2,3,4,1,3,4,1]
print(f"there {nums.count(4)} occurances of number 4 in the list")
# there 3 occurances of number 4 in the list
```

`.reverse()` - reverse the list ( uses the same list object, does not create a new object in memory )

```py
numbers = [0,1,2,3,4,5]
numbers.reverse()
numbers
# [5, 4, 3, 2, 1, 0]
```

`.sort()` - sort list in ascenting order

```py
numbers = [0,1,20,0.3,4,5]
numbers.sort()
numbers
# [0, 0.3, 1, 4, 5, 20]
```

`.join()` - create a string from all of the list items

```py
words = ["I", "want", "to", "create", "a", "wiki"]
' '.join(words)
# 'I want to create a wiki'
```

### Nested Lists ( Matrix )

**Used for**

- complex data structures
- game boards
- rows and columns for visualisation, tabulation and data grouping

```py
nested_list=[[1,2,3],[4,5,6],[7,8,9]]
nested_list[-1][1]
# 8
nested_list[1,2]
# 6
```

## Dictionaries

> Dictionaries are defined using `{}`

> a collection of key:value pairs

```py
user =  {
    "name": "Johny",
    "hobbies": ["learn", "teach", "work", "create"],
    "blog": "blog.artpav.dev",
    "wish": ["contribute to open source"]
}
```

### Accessing Dictionary Values

`dictionary["key"]`

```py
user["name"]
# 'Johny'
```

### Adding Values To Dictionary

```py
user["pet"] = "dog"
user
# {'name': 'Johny',
# 'hobbies': ['learn', 'teach', 'work', 'create'],
# 'blog': 'blog.artpav.dev',
# 'wish': ['contribute to open source'],
# 'pet': 'dog'}
```

### Dictionary Comprehensions

`{expression_key : expression_value for key, value in dictionary_name}`

```py
numbers = {
    "one":1,
    "two":2,
    "three":3
}

{key+key : value ** 2 for key, value in numbers.items()}

# {'oneone': 1, 'twotwo': 4, 'threethree': 9}
```

loop through numbers and create a dictionary where the key is the number and the value is whether it's odd or even.

```py
numbers = [1,2,3,4]
{ num:("even" if num % 2 == 0 else "odd") for num in numbers }
# {1: 'odd', 2: 'even', 3: 'odd', 4: 'even'}
```

### Dictionary Methods

```py
dictionary =  {
    "name": "Johny",
    "hobbies": ["learn", "teach", "work", "create"],
    "blog": "blog.artpav.dev",
    "wish": ["contribute to open source"]
}
```

`.values()` - return values for all properties in the dictionary

```py
dictionary.values()
# dict_values(['Johny', ['learn', 'teach', 'work', 'create'], 'blog.artpav.dev', ['contribute to open source']])
```

`.keys()` - return keys for all properties in the dictionary

```py
dictionary.keys()
# dict_keys(['name', 'hobbies', 'blog', 'wish'])
```

`.items()` - return key:value pairs for the dictionary

```py
dictionary.items(),
# dict_items([('name', 'Johny'), ('hobbies', ['learn', 'teach', 'work', 'create']), ('blog', 'blog.artpav.dev'), ('wish', ['contribute to open source'])])
```

`.get(key)` - retrieve value for a specific dictionary key

```py
dictionary.get("name")
# 'Johny'
```

#### Adding Values to Dictionary

`.update(new_item)` - put key:value pair into the dictionary

```py
phone_number = {"phone_number":"+xxxxxxxxx"}
dictionary.update(phone_number)
dictionary
# {'name': 'Johny',
# 'hobbies': ['learn', 'teach', 'work', 'create'],
# 'blog': 'blog.artpav.dev',
# 'wish': ['contribute to open source'],
# 'phone_number': '+xxxxxxxxx'}
```

#### Removing Values from Dictionary

`.clear()` - empty the dictionary

```py
dictionary.clear()
dictionary
# {}
```

`pop(key)` - remove a value by its key. Returns the value of the key that was removed

```py
dictionary.pop("wish")
# ['contribute to open source']
```

`.popitem()` - remove a random key:value pair from the dictionary

```py
dictionary.popitem()
# ('wish', ['contribute to open source'])
```

#### Other Dictionary Methods

`.copy()` - create a clone of dictionary in a separate object

```py
new_dictionary=dictionary.copy()
new_dictionary
# {'name': 'Johny', 'hobbies': ['learn', 'teach', 'work', 'create'], 'blog': 'blog.artpav.dev'}
new_dictionary == dictionary
# True
new_dictionary is dictionary
# False
```

`.fromkeys()` - create key:value pairs from strings

> useful to assign a value to a list of keys.

```py
{}.fromkeys(['email', 'passion', 'website'], None)
# {'email': None, 'passion': None, 'website': None}
```

### Using `in` with Dictionaries

> Looking in dictionaries keys be default, use `dictionary.values()` to override

```py
"name" in dictionary
# True
```

```py
"Johny" in dictionary.values()
# True
```

## Tuples

> Tuples are defined using `()`

- Tuples are **immutable**
- **Values cannot be added or removed** once tuple is created
- Used for constant values ( _for example - defining months of the year_ )

### Tuple Methods

List methods apply

## Sets

- Contain unique values
- Automatically remove duplicates
- Can't be indexes
- Are iterable objects

### Set Comprehensions

`{x**2 for item in set}`

### Set Methods

```py
tasks = {"Install Python", "Learn Python", "Take a break"}
```

#### Adding Values to Sets

`.add(new_value)` - add value to set, no error is returned if the value is already present.

```py
tasks.add(1)
tasks
# {'Learn Python', 1, 'Take a break', 'Install Python'}
```

#### Removing values from Sets

`.remove(value)` - remove value from a set, an error is thrown in case there is no such value.

```py
tasks.remove("Take a break")
tasks
# {'Learn Python', 'Install Python'}
```

`.discard(value)` - remove value from a set, no error is returned in case there is no such value

```py
tasks.discard("Take a break")
```

`.clear()` - empty the set

```py
tasks.clear()
tasks
# set()
```

#### Other Set Methods

`.copy()` - create a clone of the set in a separate object

```py
new_tasks = tasks.copy()
new_tasks
# {'Learn Python', 'Take a break', 'Install Python'}
new_tasks == tasks
# True
new_tasks is tasks
# False
```

`.intersection(compare_with_set)` - return common values between 2 sets

```py
set_one = {1,2,3,4,5}
set_two = {3,4,5,6,7,8}

set_one.intersection(set_two)
# {3, 4, 5}
```

`.isdisjoined(compare_with_set)` - return `bool` identifying whether the sets are not overlapping

```py
set_one = {1,2,3,4,5}
set_two = {3,4,5,6,7,8}

set_one.isdisjoint(set_two)
# False
# because they are overlapping
```

`.union(another_set)` - merge sets and create a new object

```py
set_one = {1,2,3,4,5}
set_two = {3,4,5,6,7,8}

set_three = set_one.union(set_two)
set_three
# {1, 2, 3, 4, 5, 6, 7, 8}
```

`.difference(compare_with_set)` - return the different values between 2 sets

```py
set_one = {1,2,3,4,5}
set_two = {4,5,6,7,8}

set_one.difference(set_two)
# {1,2,3}
```

`.difference_update(another_set)` - update set by removing the common values between sets

```py
set_one = {1,2,3,4,5}
set_two = {3,4,5,6,7,8}

set_one.difference_update(set_two)
set_one
# {1,2}
```

`issubset(another_set)` - are all elements from the original set included in another set

```py
set_one = {4,5}
set_two = {3,4,5,6,7,8}

set_one.issubset(set_two)
# True
# becase all items from set_one are in set_two
```

`issuperset(another_set)` - are all elements from the another set included in original set

```py
set_one = {4,5}
set_two = {3,4,5,6,7,8}

set_one.issuperset(set_two)
# False
# becase not all items from set_two are in set_one
```

## Ternary Operator

> shorter version of an if/else statement

```py
im_right = False
print("I was correct!" if im_right else "I was wrong")
```

## Functions

a function is initiated using `def` keyword

`return` keyword is used to retrieve data from a function and exit the function as the next step.

```py
def square_of_three():
    return 3**2

x = square_of_3()
print(x)
```

`parameter` - variable declaration in a function

`argument` - value for the parameter when using a function

```py
def exponent(number,power=2): # list of parameters, default value for power parameter
    return number**power

x = exponent(number=2) # argument value
print(x)
```

### Function Documentation / Doc Strings

```py
def my_awesome_function():
    '''
      Info: This function shows the documentation possibilities
    '''
    print("Read the docs")
```

```py
print(my_awesome_function.__doc__)

      Info: This function shows the documentation possibilities
```

### Scopes

`local` - variables that are defined inside a function and can't be used outside of it

```py
global_var = "I am a global variable"

def say_local(): #local variable, can't be used outside the function
    function_var = "I am a local variable"
    return f"{function_var}"

print(say_local())
# I am a local variable
print(function_var)
# Traceback (most recent call last):
#   File "<stdin>", line 1, in <module>
# NameError: name 'function_var' is not defined
print(global_var)
# I am a global variable
```

`global` - variables defined in the root of the code

> global variables have to be refereb using `global variable_name` syntax

```py
total = 0 # global variable
def increment():
    global total
    total += 1
    return total

print(increment())
```

`nonlocal` - variables defined in the parent function

> global variables have to be refereb using `nonlocal variable_name` syntax

```py
def parent():
    count = 0
    def child():
        nonlocal count # refers a variable in parent function
        count += 1
        return f"inner {count}"
    print(child())
    return f"outer {count}"
```

### `*args` and `*kwargs`

[Doc Reference](https://book.pythontips.com/en/latest/args_and_kwargs.html#args-and-kwargs)

#### \*args

- `*args` are stored as a tuple
- `*args` profide the possibility to input any number of arguments when calling a function
- args is the standard for defining dynamic arguments but any word can be used

```py
def sumnums(*args):
     return sum(args)

sumnums(1,2,3,4,5)
# 15
```

#### \*\*kwargs

- `*kwargs` are stored as a dictionary
- you have to iterate through kwargs to perform actions with the arguments

```py
def do_kwargs(**kwargs):
    for key, value in kwargs.items():
        print(f"{key} has a value of {value}")

# you have to define a * before variable in order to unpack something
do_kwargs(name="Elon", surname="Musk", planet="Mars")
```

#### Parameter Ordering

`def my_function( parameters, \*args, default_parameters, \*\*kwargs )`

## Built-in Functions

[Doc Reference](https://docs.python.org/3/library/functions.html)

Some of the more commonly used ones include:

### General

`all` - checks if **all items** in an **iterable object** are **`Truthy`**

`any` - checks if **any** item in the **iterable object** are **`Truthy`**

`reversed` returns a reversed list

`len` - returns the lenght of an object

`sorted` - creates a new object containing a sorted list, tuple or dictionary ( using `lambda` functions )

```python
# ,key= specifies how to sort data
> sorted(users,key=lambda user: user['username'])
# sort dict by name
```

`max`, `min` - get maximal and minimal value of object, list, tuple or string ( returns letter with highest/lowest digit value )

### Math

`abs` - the absolute value of a number $|-23| = 23$

`sum` - returns a sum of a set of elements

there’s an alternative in `math` module called `fsum`

`round` - returns a rounded value, rounds to `int` by **default**

`sorted` - sorts numbers in another object, does not change initial iterable object can be used on lists, tuples

### zips

- adds numbers with the same index in 2 lists into one tuple
- goes from left to right
- stops when the shortest iterable ends
- can have more then 2 objects

can return a list

```python
list(zip([1,2,3],[4,5,6]))
# Output : [(1, 4), (2, 5), (3, 6)]
```

```python
dict(zip([1,2,3],[4,5,6]))
# Output {1: 4, 2: 5, 3: 6}
```

# Advanced Python

## Debugging

[Doc Reference : Built-in Exceptions](https://docs.python.org/3/library/exceptions.html)

`raise` - raises an error of specific type

```py
raise ValueError("That's not something I expected")
# Traceback (most recent call last):
#   File "<stdin>", line 1, in <module>
# ValueError: That's not something I expected
```

`try except` - return different messages depending on the error type

```py
try: # main code block,
    do(stuff)
except: # ErrorType can be provided to work with specific Errors, example :
    TypeError:
        print("you encountered a type error") # what to do on error
except(RuntimeError, NameError):
    print("you encountered one of other errors")
```

`finally` - code will be executed always at the end of the script

```py
try:# main code block,
    do(stuff)
except:# what to do on error
else: # code block that runs if except is skipped
finally: # runs always in the end
    cleanup_tracks()
```

## Modules

[Doc Reference : Python Module Index](https://docs.python.org/3/py-modindex.html)

`import $MODULE_NAME` - regular import

`import $MODULE_NAME as $CUSTOM_REFERENCE_NAME` - import module and assign custom name to it

```py
import random as rnd

rnd.randint(1,123)
# 17
```

### Module Installation

`python -m pip install $MODULE_NAME`

### `__name__` variable

When you execute a command, the `__name__` variable is `__main__`.

When you import another file into another file, the value of `__name__` variable will be **the name of imported file**.

When importing a file, Python by default will run the command in the importable file.

**Example**

```py
# define a function
# print the name variable of the function
def say_something():
# execute the command inside the importable file only when the imported file is the main file
    print(f"something {__name__}")

if __name__ == "__main__":
    say_something()
```

```py
# in another file
# when you import, it will not run say_something by default
# because after importing the __name__ of the imported file will be changed to say_something
import say_something
def say_specific():
    print(f"specific {__name__}")

say_specific()
say_something()
```

## Object Oriented Programming (OOP)

> OOP is about representing something with an instance of code ( `class` and `objects of classes`) that has different properties ( `attributes` ) and it is able to perform actions using `methods`

#### Class

bluepring or specification of an object, classes can contain `methods` and `attributes`

**Example**

class `User`

`attribute` - every user **has**

- username
- password
- email

`methods` - every user **can**

- logout
- change_email
- post_article

#### Object

> An instance of a class is called `object`

### Why OOP?

> The primary goal of OOP is to encapsulate the code into logical, hierarchical groupings using `classes` so that you can reason about your code at a higher level

#### Abstraction

Exposing only relevant data (only public classes), hiding things that users should not access.

#### Encapsulation

> Grouping of public and private attributes and methods into programmatic `class`, making abstraction possible

**Example**

Designing a Deck clas you can make cards a private attribute since they are never accessed directly. You could use a public method in order to access cards.

`_cards` - **private** list attribute
`_max_cards` - **private** int attribute
`shuffle` - **public** method
`deal_card` - **public** method
`deal_hand` - **public** method
`count` - **public** method

### Comparison

**Attribute**

- defined on class and is the same for all instances
- defined for each object that is created from a class

**Method**

- defined for the class using `@classmethod` decorator
- defined by default when creating a method inside a class

### Class Attribute Definition

`ClassName.attribute_name` - regular attributes that are ment to be exposed externally

`ClassName._attribute_name` - private attributes or methods, **intended for class internal use only**

> Python does not have any restriction built into the language

### Hands-on Classes

#### Creating a class

class names have to be constructed in **CamelCase**

```py
class User:
  pass
```

#### Initiating a class

```py
my_new_user = User()
print(type(my_new_user))
# <class '__main__.User'>
```

#### Adding functionality

`__init__` [dunder method](https://www.geeksforgeeks.org/dunder-magic-methods-python/) - the **default action** that will be executed when class is called

`self` - attribute that refers to the instance of the class object that will be created from class

```py
class User:
  def __init__(self)
    print("User was created!")
```

#### Instance attributes

> additional attributes can be defined after the `self` attribute

```py
class User:
  def __init__(self, first_name, surname):
    print("User was created!")

my_new_user = User('Johny', 'Bravo')
```

in order to access `first_name` and `surname` attributes from a class object, they must be defined under the `__init__` method

```py
class User:
  def __init__(self, first_name, surname):
    self.name = first_name
    self.surname = surname

my_new_user = User('Johny', 'Bravo')
my_new_user.name
# 'Johny'
```

#### Instance Methods

New methods should be defined after dunder methods ( `__init__` etc.).

```py
class User:
  def __init__(self, first_name, surname):
    self.name = first_name
    self.surname = surname
  def full_name(self):
    return f"{self.name} {self.surname}"

my_new_user.full_name()
# 'Johny Bravo'
```

#### Class Attributes

> used to define a class level variable that is the same for all instances of the class

Examples

- keep track of a class property

```py
class User:
  overall_users = 0
  def __init__(self, first_name, surname):
    self.name = first_name
    self.surname = surname
  def full_name(self):
    return f"{self.name} {self.surname}"
```

- set limitations for specific properties

```py
class Pet:
    allowed_pet_species = ['cat', 'dog', 'fish', 'rat']
    def __init__(self, pet_name, specie)
        if specie not in Pet.allowed_pet_species:
            raise ValueError(f"You can't have a {specie} as a pet!")
        self.name = name
        self.specie = specie
```

#### `__repr__` method

> represents the default value when printing the object created from class

```py
class User:
    def __init__ (self, first_name, surname):
        self.name = first_name
        self.surname = surname
    def __repr__ (self):
        # when the object is called it will give back instance attribute'first_name'
        return f"{self.name}"

new_user = User("Johny", "Bravo")
```

without `__repr__`

```py
print(new_user)
# <__main__.User object at 0x05B37150>
```

with `__repr__`

```py
new_user
# Johny
```

#### Inheritance

> Inherited class **has access to all resources** available in the **parent** class

> `super().` defines that the attributes should be taken from the parent class

> Inherited classes are defined with NewClass(ParentClass)

```py
class User:
    def __init__ (self, first_name, surname, age):
        self.name = first_name
        self.surname = surname

class Moderator(User):
    def __init__ (self, first_name, surname, age, social_groups):
    # commonly used for defining the common attributes
      super().__init__(first_name, surname, age)
      self.social_groups = social_groups
```

#### Properties

> Are defined using `@property` decorator

> setters are defined using `@property_name.setter` syntax

```py
@property
def my_new_property(self):
    return self._internal_attr
# commonly used for retrieving a internal/private attribute

@some_property.setter: #
def my_new_property(self, new_value):
    self._internal_attr = value # commonly used to update internal/private attributes
```

#### Multiple Inheritance

> Consider not using it, please :)

```py
class User:
    def __init__(self, user_attribute):
        self.user_attribute = user_attribute
        print(f"init user, from {user_attribute}")

class Moderator():
    def __init__(self, moderator_attribute):
        self.moderator_attribute = moderator_attribute
        print(f"init moderator, from {moderator_attribute}")
```

you define multiple parent classes using `NewClass(ParentClassOne, ParentClassTwo)` syntax

```py
class Administrator(User, Moderator):
  def __init__(self, admin_attribute):
    User.__init__(self, admin_attribute)
    Moderator.__init__(self, admin_attribute)
    print(f"init admin, from {admin_attribute}")
```

#### Method Resolution Order ( MRO )'

> Returns the order in which, in case of inheritance, python will look for a method .

`ClassName.mro()`

`help(ClassName)`

```py
Administrator.mro()
# [<class '__main__.Administrator'>, <class '__main__.User'>, <class '__main__.Moderator'>, <class 'object'>]

help(Administrator)
# class Administrator(User, Moderator)
#  |  Administrator(admin_attribute)
#  |
#  |  Method resolution order:
#  |      Administrator
#  |      User
#  |      Moderator
#  |      builtins.object
```

#### Polymorphism

> Method in a **subclass** overrides the value of the method in the **parent** class

**Examples**

- Method from ChildClass with the same name as one in the ParentClass does different things

```py
class Animal:
    def speak(self):
        raise NotImplementedError("Subclass must define this method")

class Dog(Animal):
    def speak(self):
        return "Woof"

class Cat(Animal):
    def speak(self):
        return "Meow"

class Fish(Animal):
    pass

d = Dog()
print(d.speak())
# Woof
f = Fish()
print(f.speak())
# Traceback (most recent call last):
#   File "<stdin>", line 1, in <module>
#   File "<stdin>", line 3, in speak
# NotImplementedError: Subclass must define this method
```

## Iterators and Generators

### Iterators and Iterables

`iterator` - object that can be iterated upon

`iterable` - object that will be returned when `iter()` is called on an iterator

- `iter()` creates an iterable object from any other object
- `next()` returns the next object from iterable until `StopIteration` error is raised

### Generators

> All generators are iterables

| Regular Function |                    Generator Function |
| :--------------- | ------------------------------------: |
| uses `return`    |                          uses `yield` |
| returns **once** | can return `yield` **multiple times** |
| returns a value  |                   returns a generator |

- generator stores last state

```py
def count_to(max):
  count = 1
  while count <= max:
    yield count
    count += 1
```

```py
g = count_to(5)
g
# <generator object count_to at 0x109ec4f20>
list(g)
# [1,2,3,4,5]
next(g)
# Traceback (most recent call last):
#   File "<stdin>", line 1, in <module>
# StopIteration
```

1. Create a generator `g`
2. Retrieve values using `list(g)`
3. Try to get next object in the iterable using `next(g)`

> Fail, because all values were returned in `list(g)`

```py
g = count_to(5)
next(g)
# 1
next(g)
# 2
next(g)
# 3
next(g)
# 4
next(g)
# 5
next(g)
# Traceback (most recent call last):
#   File "<stdin>", line 1, in <module>
# StopIteration
```

1. Create a generator `g`
2. Try to get next object in the iterable using `next(g)`
3. Returns `count += 1` until condition is met, afterwards throws `StopIteration`

#### Generator Comprehensions

> Generator comprehension uses `()`

> Faster processing compared to list comprehensions

`(num for num in range(1,10))`

## Decorators

### Higher Order Function

> Function that accepts other functions as arguments or returns other functions

### Decorators

Functions that

- Wrap other functions and enhance their functionality
- Have special syntax, `@derocator_function`

#### Preserving metadata

Make sure that the metadata of called function is not replaced by the metadata of the **wrapper** function is fixed by `wraps` decorator

```py
from functools import wraps
```

**Before `wraps`**

```py
def log_function_data(func):
    def wrapper(*args, **kwargs):
        # Preversing metadata
        """THE WRAPPER function"""
        print(f"you are about to call {func.__name__}")
        print(f"here's the documentation: {func.__doc__}")
        return func(*args, **kwargs)
    return wrapper


@log_function_data
def add(a, b):
    """Adds 2 numbers together"""
    return a+b


print(add(12, 23))

# Preversing metadata
print(add.__doc__)
print(add.__name__)
print(help(add))
```

**After `wraps`**

```py
# import wraps
from functools import wraps


def log_function_data(func):
    @wraps(func)  # @wraps decorator with the function name that should be 'saved'
    def wrapper(*args, **kwargs):
        # Preversing metadata
        """THE WRAPPER function"""
        print(f"you are about to call {func.__name__}")
        print(f"here's the documentation: {func.__doc__}")
        return func(*args, **kwargs)
    return wrapper


@log_function_data
def add(a, b):
    """Adds 2 numbers together"""
    return a+b


print(add(12, 23))

# Preversing metadata
print(add.__doc__)
print(add.__name__)
print(help(add))
```

- Decorators can also be used to restrict arguments for function

```py
from functools import wraps


def no_kwargs(fun):
    @wraps(fun)
    def wrapper(*args, **kwargs):
        if kwargs:
            raise ValueError("YOU CAN'T USE KWARGS")
        return fun(*args, **kwargs)
    return wrapper


@no_kwargs
def greet(name):
    print(f"hello, {name}")


greet("art")

greet(name="art")
```

## Testing

[Great article on testing Python](https://realpython.com/python-testing/)

[Testing Python in VS Code](https://code.visualstudio.com/docs/python/testing)
