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

> One line way to perform an action on item in an iterable object

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

`.append(value_to_add)` - adds **one** value to the end of the list

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

`.clear()` - empties the list

```py
numbers.clear()
numbers
# []
```

`.pop(index)` - remove item at the provided index from the list, removes last if no index is provided. Returns what value was removed

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

`.count(value)` - return the number reoccurances that a value has in the list

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

> Dictionaries are defined using {}

> a collection of key:value pairs

```py
user =  {
    "name": "artemijs",
    "hobbies": ["learn", "teach", "work", "create"],
    "blog": "blog.artpav.dev",
    "wish": ["contribute to open source"]
}
```

### Accessing Dictionary Values

`dictionary["key"]`

```py
user["name"]
# 'artemijs'
```

### Adding Values To Dictionary

```py
user["pet"] = "dog"
user
# {'name': 'artemijs',
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
    "name": "artemijs",
    "hobbies": ["learn", "teach", "work", "create"],
    "blog": "blog.artpav.dev",
    "wish": ["contribute to open source"]
}
```

`.values()` - return values for all properties in the dictionary

```py
dictionary.values()
# dict_values(['artemijs', ['learn', 'teach', 'work', 'create'], 'blog.artpav.dev', ['contribute to open source']])
```

`.keys()` - return keys for all properties in the dictionary

```py
dictionary.keys()
# dict_keys(['name', 'hobbies', 'blog', 'wish'])
```

`.items()` - return key:value pairs for the dictionary

```py
dictionary.items(),
# dict_items([('name', 'artemijs'), ('hobbies', ['learn', 'teach', 'work', 'create']), ('blog', 'blog.artpav.dev'), ('wish', ['contribute to open source'])])
```

`.get(key)` - retrieve value for a specific dictionary key

```py
dictionary.get("name")
# 'artemijs'
```

#### Adding Values to Dictionary

`.update(new_item)` - put key:value pair into the dictionary

```py
phone_number = {"phone_number":"+xxxxxxxxx"}
dictionary.update(phone_number)
dictionary
# {'name': 'artemijs',
# 'hobbies': ['learn', 'teach', 'work', 'create'],
# 'blog': 'blog.artpav.dev',
# 'wish': ['contribute to open source'],
# 'phone_number': '+xxxxxxxxx'}
```

#### Removing Values from Dictionary

`.clear()` - empties the dictionary

```py
dictionary.clear()
dictionary
# {}
```

`pop(key)` - removes a value by its key. Returns the value of the key that was removed

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

`.copy()` - creates a clone of dictionary in a separate object

```py
new_dictionary=dictionary.copy()
new_dictionary
# {'name': 'artemijs', 'hobbies': ['learn', 'teach', 'work', 'create'], 'blog': 'blog.artpav.dev'}
new_dictionary == dictionary
# True
new_dictionary is dictionary
# False
```

`.fromkeys()` - creates key:value pairs from strings

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
"artemijs" in dictionary.values()
# True
```
