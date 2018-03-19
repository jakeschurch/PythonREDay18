Find on the web: [github.com/jakeschurch/PythonREDay18](github.com/jakeschurch/PythonREDay18)

Jake Schurch
3/23/18
ISA330
Group 15 REDay Presentation
***
### Table of Contents
- List Comprehension
- Error Handling
- PEP 484 Syntax
- Decorators (if we have time!)
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
Can be thought of as flipping a python for-loop into a one-liner statement:

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
strings = [str(num) for num in numbers]
# >>> print(strings) 
# Output: ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9' '10']
```
That's cool and all, but what if we wanted to filter the list using an if-statement: **No Problem.**

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

evenNums = [num for num in range(11) if num %2 == 0]
# >>> print(evenNums)
# Output: [0, 2, 4, 6, 8, 10]
```
***
##### Overall Benefits
- More compact
- Faster
- Idiomatic (better) 
- More human-readable
- Cleaner Code
***
### Error Handling
Sometimes things go wrong in Python. That's ok - why we have general **error handling**.
Error handling allows us from step out of a program's execution flow to undo operations or rollback part of our program.
[Python - More on Error Handling](https://www.tutorialspoint.com/python/python_exceptions.htm)

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
### Try-Except-Else Block
Allows for conditional 
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
# ...can we print num at this block?
```
***
### PEP 484
TODO
### Decorators
TODO
### Further Reading 
TODO
