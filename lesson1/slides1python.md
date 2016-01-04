Python
======
- Python is the preferred language for most Raspberry Pi libraries/coding/features/etc
- You can code in anything really (it is just a computer with a linux distro)
- However libraries do exist for Python for doing things like handling the pins

Basics of Python
================
- Whitespace is critical in Python
- Code blocks determined by indentation level
- Indentation can be tabs or spaces (any number) as long as it is consistent
- For clarity though, we will use 4 spaces, which is the standard in most projects


A basic Python program
======================

```python

import os

filenames = os.listdir(".")

if len(filenames) == 0:
	print("You have no files")
else:
	print("Files on your system:")
	for filename in filenames:
		print(filename)

```

Instructor notes: Point out library importing (namespaces), function calling, dynamic typing, if statements, print functions and for loops.
Identify that the colon ends a line that introduces a new block (such as an if statement, for loop or function definition)


Running Python Scripts
======================
- Python "scripts" are just text files (normally with the `.py` extension)
- They can be run directly using: `python script_name.py`
- Can be run as executable scripts too, as daemons, or any other way to run a program in Linux


Python 2 vs 3
=============
TODO: check what Raspbian uses, use that as default
- If starting a new project, use Python 3
- Only use Python 2 if you are integrating with a legacy system


Functions
=========

```python

def add(a, b):
    return a + b
    
def multiply(a, b):
    sum = 0
    for i in range(b):
        sum += a
    return a  # You can just do "a * b", this is just an example

print("3 + 4 =", add(3, 4))
print("3 * 4 =", multiply(3, 4))

```

User Input
==========
```python

your_name = input("Enter your name: ")
print("Hello", your_name, "!")

```

Random Numbers
==============
```python

from random import randint

print(randint(0, 2))
```
- Useful for testing things, or completing the exercises


Exercises
=========

1. Create a function that plays rock-paper-scissors
2. Create a loop that plays lots of games between random inputs
3. Create a program that plays game against user
4. Create a report on the average win/loss for the user, after a given number of games played
