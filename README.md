# PythonREDay18
Presentation on introducing more intermediate python syntax for those new-er to the language.
Find on the web: [github.com/jakeschurch/PythonREDay18](https://www.github.com/jakeschurch/PythonREDay18)

Jake Schurch
3/23/18
ISA330
Group 15 REDay Presentation
***
### Table of Contents
- List Comprehension
- Error Handling
- PEP 484 Syntax

***
### List_Comprehension (lc)

##### Introduction
How many times have you found yourself doing this?
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

# Creating a new list from a list
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
strings = []

for num in numbers:
    strings.append(str(num))
# >>> print(strings) 
# Output: ['0', 1', '2', '3', '4', '5', '6', '7', '8', '9' '10']
```
We just used 6 lines _(whitespace included)_ of python code in order to make a new list.
Can this be done better? Yes, using **list comprehension** (lc)
***
##### What is lc?
Can be thought of as flipping a python for-loop statement into a one-liner statement:

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
strings = [str(num) for num in numbers]
# >>> print(strings) 
# Output: ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9' '10']
```
That's cool and all, but what if we wanted to filter the list using an if-statement? - **No Problem.**

Using a regular for-if-loop:
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

# create a new list from numbers only containing even numbers 
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evenNums = []

for num in numbers:
    if num % 2 == 0:
        evenNums.append(num)
# >>> print(evenNums)
# Output: [0, 2, 4, 6, 8, 10]
```
Using lc with a conditional statement:
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

# create a new list from numbers only containing even numbers 
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evenNums = [num for num in numbers if num % 2 == 0]
# >>> print(evenNums)
# Output: [0, 2, 4, 6, 8, 10]
```
Or even better:
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

evenNums = [num for num in range(11) if num % 2 == 0]
# >>> print(evenNums)
# Output: [0, 2, 4, 6, 8, 10]
```
***
#### Overall Benefits
- More compact
- Faster
- Idiomatic (better) 
- More human-readable
- Cleaner Code
***
### Error Handling
Sometimes things go wrong in Python. That's ok - why we have general **error handling**.
Error handling allows us from step out of a program's execution flow to undo operations or rollback part of our program.

#### Try-Except Block
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
def divide(a, b):
    return a/b
try: 
    num = divide(5, 0)
except ZeroDivisionError:
    print("You cannot divide by 0!")
# print(num)
# ...can we print num at this block?
```
Also can use a blank `except` block to catch any error, but...
***
### Try-Except-Else Block
Allows for conditional error handling
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

def divide(a, b):
    return a/b
try: 
    num = divide(5, 0)
except ZeroDivisionError:
    print("You cannot divide by 0!")
else:
    print(num)
```
***
### Try-Finally Block
To execute code that needs to be ran regardless of an error, add a `finally` block...this code will always execute.
Use error-handling to deal with exceptions and allow our code to continue to run the rest of the code.

To go back to our divide example:
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

def divide(a, b):
    try:
        num = a / b
    except ZeroDivisionError:
        print("You cannot divide by 0!")
        num = 0  # or maybe Null - it's up to you!
    finally:
        return num
# num will be returned by divide regardless of whether there is an error or not.
```
[see more on error handling & exceptions...](https://www.tutorialspoint.com/python/python_exceptions.htm)
***

### PEP 484
The PEP (Python Enhancement Proposal) 484 allows for type hinting. This allows us to annotate function/class arguments and outputs for _more idiomatic_ code (especially for those that are not familliar with your code).

Example of a function without type hinting: 

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

def add(a, b):
    return a + b
    
"""easily allow us to:
>>> foo = add('hello ', 'world')
print(foo)
Output: 'hello world'
or:
>>> bar = add(1, 2)
>>> print(bar)
Output: 3
"""
```
Type hinting may be a good idea in your Python code because Python is a dynamic-typed language; which means that we do not need to determine the type of a variable when we declare it.

With type hinting:
```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

def add(a: int, b: int) -> int:
    return a + b
```
Note that this does not make python static-typed, but acts only as a **hint** rather than a requirement.

[see more on PEP 484...](https://www.python.org/dev/peps/pep-0484/)
***


