**Table of Contents**

- [Poetry for Python](#poetry-for-python)
- [REPL - Read, Evaluate, Print, Loop](#repl---read-evaluate-print-loop)
- [Basic Data Types](#basic-data-types)
- [Functions](#functions)
  - [Scope inside the function](#scope-inside-the-function)
- [Advanced Data Structures](#advanced-data-structures)
  - [Lists](#lists)

## [Poetry for Python](https://python-poetry.org/)

Package manager for python - similar to npm for node

**Basic commands:**

- `poetry new <project_name>` : creates a new project
- `poetry add <dependency_name>`: adds dependency - similar to `npm install`
- `poetry shell`: enters into the virtual env. Here you can access the installed packages

## REPL - Read, Evaluate, Print, Loop

REPL is more like a scratch area. Isn't it cool!

**Basic commands:**

- `type()` - returns the type of the input
- `dir()` - returns list of all the properties on the input object
- `help()` - gives info about the input

## Basic Data Types

```python
# f-strings
name = "Abhilash"
greeting = f"Hello, {name}"

print(greeting)  # Hello, Abhilash
```

## Functions

There are 2 types of function arguments - **positional**, **named** arguments. named aguments with default values are called as **keyword** arguments.
Arguments without default values are required by Python. All of the required arguments go first. They are then followed by the optional keyword arguments.

**Note**: In Python, default arguments are evaluated only once – when the function is defined. Not each time the function is called. That means if you use a value that can be changed, it won’t behave like you’d expect it to.

```python
# Don't do this!
 def add_five_to_list(my_list=[]):
     my_list.append(5)
     return my_list

# This works like we expected it to.
add_five_to_list() # [5]
# Huh?
add_five_to_list() # [5, 5]
# We see that the original `my_list` is still being modified.
add_five_to_list() # [5, 5, 5]
```

### Scope inside the function

You can’t change variables defined outside of the function inside of the function. If you try to, your changes will only apply while the function is running. Once the function is done running, the value goes back to what it was before your function ran.

An appropriate use is when using a constant, a variable defined in all caps, with the words separated by underscores

```python
name = "Nina"
print(f"Name outside of function: {name}") # Name outside of function: Nina

def try_change_name():
    name = "Max"
    print(f"Name inside of function: {name}")

try_change_name() # Name inside of function: Max

print(f"Name outside of function: {name}") # Name outside of function: Nina
```

## Advanced Data Structures

### Lists

Used for storing similar items, and in cases where items need to be added or removed.
There are 2 ways to sort list items - sorting a copy of your list, in-place sort

```python
# Sort copy of list
lottery_numbers = [1, 4, 32423, 2, 45, 11]

sorted(lottery_numbers) # [1, 2, 4, 11, 45, 32423]
lottery_numbers # [1, 4, 32423, 2, 45, 11]

sorted(lottery_numbers, reverse=True) # [32423, 45, 11, 4, 2, 1]
lottery_numbers # [1, 4, 32423, 2, 45, 11]


# In-place sorting
lottery_numbers = [1, 4, 32423, 2, 45, 11]

lottery_numbers.sort()
lottery_numbers # [1, 2, 4, 11, 45, 32423]

lottery_numbers.sort(reverse=True)
lottery_numbers # [32423, 45, 11, 4, 2, 1]

words = ["Umbrella", "Fox", "Apple"]

words.sort()
words # ['Apple', 'Fox', 'Umbrella']
```

**Note**: We can think of the built-in methods (sorted, etc) as **pure functions**. They won't change the passed arguments. Methods on the class can change their internal values!
