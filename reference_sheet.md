# Work in progress, come back later!

# Exam 2 Reference Materials
Check out the [reference materials from exam 1](https://github.com/tamu-edu-students/engr-102-exam1-review/blob/main/reference_sheet.md) for a review of those topics.

Topics:
1. [Dictionaries](#dictionaries)
2. [Review of Data Types](#review-of-data-types)
3. [Functions](#functions)
4. [Debugging](#debugging)
5. [File IO](#file-io)
6. [Modules](#modules)

## Dictionaries
In Python, dictionaries are created with curly braces `{}` and `key:value` pairs
```python
mydict = {"key 1" : "value 1", "key 2" : "value 2", "key 3" : "value 3"}
```

You can add new key-value pairs to an existing dictionary using the key inside square brackets `[]` and assigning the corresponding value. You can access the value of a key-value pair using square brackets.
```python
mydict = {} # create an empty dictionary

# add 3 new key:value pairs
mydict["x"] = 9
mydict["y"] = "Howdy"
mydict["z"] = [3, 6, 1]

# print things
print(mydict)          # entire dictionary
print(mydict["y"])     # value paired with key "y"
print(mydict["z"][0])  # first element in the value (list) paired with key "z"
```

You can also reassign a new value to an existing key
```python
mydict = {"x" : 9}
mydict["x"] = 5
print(mydict)
```

You can loop through the keys of a dictionary with a for loop
```python
mydict = {"x" : 9, "y" : "Howdy", "z" : [3, 6, 1]}
for key in mydict:
    print(f"{key} : {mydict[key]}")
```

## Review of Data Types
This class covers the following data types
| Data Type | Examples | Notes |
| :---: | :--- | :--- |
| Integer | `4`, `-2`, `-5`, `10` | immutable |
| Floating-point (float) | `1.999`, `2.0`, `-4.89`, `867.5309` | immutable |
| Boolean | `True` evaluates to `1`, `False` evaluates to `0` | immutable |
| String | `""`, `"Letters"`, `'my string'` | immutable |
| List | `[]`, `[1, 2, 3]` | mutable |
| Dictionary | `{}`, `{"one" : 1, "two" : 2}` | keys are immutable, values are mutable |
| Tuple | `()`, `(1, 2, 3)` | immutable |

Be careful when assigning a mutable data type in a tuple. The tuple's bindings are immutable, however the objects bound to it may change if they are a mutable data type.
```python
mylist = [1, 2, 3]
mytuple = (mylist, 10)
mylist[0] = 5
print(mytuple)
```

## Functions
Functions are defined before they are called. The first line is called the function header.
```python
def my_function():
    """this functions prints something"""
    print("something")
```

Functions can take in arguments. Default arguments must be defined from right to left.
```python
def myfun(a, b=12): # b has a default value of 12
    """this function adds a and b"""
    return a + b
```
Calling `myfun(1)` will return `13`. Calling `myfun(1, 2)` will return `3`.

Scope of variables refers to what part of your code has access to variables. Functions can read values assigned in main code, but they cannot reassign them. Variables assigned inside a function are local only to that function. For example, in the code below `a` is assigned the value `3` in main memory. That same value is passed to the function in the function call `myfun(a)`. A new variable `a` is created in function memory with a copy of the value `3`. Function memory `a` changes to `4`, but main memory `a` remains `3`. When we exit the function, all variables local to that function are removed from memory.
```python
def myfun(a):
    a += 1
    return a
a = 3
print(myfun(a), end="")
print(a)
```
will output `43`

## Debugging

## File IO

## Modules
