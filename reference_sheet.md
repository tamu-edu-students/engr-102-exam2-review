# Work in progress, come back later!

# Exam 2 Reference Materials
Check out the [reference materials from exam 1](https://github.com/tamu-edu-students/engr-102-exam1-review/blob/main/reference_sheet.md) for a review of those topics.

Topics:
1. [Dictionaries](#dictionaries)
2. [Review of Data Types](#review-of-data-types)
3. [Functions](#functions)
4. [Debugging](#debugging)
5. [File IO](#file-io)
6. [String Processing](#string-processing)
7. [Modules](#modules)

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

You can unpack a tuple to put each value into its own variable
```python
mytuple = 1, 2, 3
a, b, c = mytuple
```

You can easily swap variable values as well
```python
x = 7
y = 6
x, y = y, x
print(x, y)
```

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

Functions can only return one object, but if that object is a tuple it can contain multiple values.
```python
def myfun(a, b=12): # b has a default value of 12
    """this function adds, subtracts, multiplies, and divides a and b"""
    return a + b, a - b, a * b, a / b
print(myfun(6))
ans = myfun(1, 2)
print(f"a+b:{ans[0]} a-b:{ans[1]} a*b:{ans[2]} a/b:{ans[3]}")
```
will output 
```
(18, -6, 72, 0.5)
a+b:3 a-b:-1 a*b:2 a/b:0.5
```



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
The `try-except` block is a great way to catch run-time errors. Put code that may create a run-time error into the `try` block. Put your fix to the potential run-time error into the `except` block.
```python
try:
    a = int(input("Enter an integer: "))
    print("howdy" * a)
except:
    print("I said integer!")
```

Try-except blocks are useful when dealing with user input. In the code above, if the user enters `3` the output will be `howdyhowdyhowdy`. If the user enters `no` the output will be `I said integer!`. Another good use for a try-except block is to check if a file exists before attempting to read from it. 

## File IO
There are two ways to open a file. You need to specify a file identifier (variable name) in your code. You can use separate open/close commands, but don't forget to close your file using the same file identifier!
```python
myfile = open("my_file.txt")
# do stuff
myfile.close()
```

You can use the with/open command. This one doesn't require a separate close statement; the file will automatically close after executing all of the indented code.
```python
with open("my_file.txt") as myfile:
    # do stuff
```

Use file designators when opening a file to specify how you plan to use it
- `"r"` to read only
- `"w"` to write to a new file
- `"a"` to append to an existing file (cursor will be placed at the end of the file)
- `"r+"` to read and write to an existing file (cursor will be placed at the beginning of the file)

If no designator is specified, `"r"` will be used. Be careful when using `"w"`! If the file exists, its contents will be deleted!

```python
with open("new_file.txt", "w") as myfile:
    # this will create a new file named new_file.txt

myfile = open("old_file.txt", "a")
# this will open an existing file for you to add to the end
myfile.close()
```

There are many ways to read from a file. The examples below use a file identifier of `myfile`.
- `myfile.read()` will read the entire file into one string
- `myfile.readline()` will read one line of the file
- `myfile.readlines()` will read the entire file into a list of strings, with each line as an element in the list
- `list(myfile)` will read the entire file into a list of strings, with each line as an element in the list (same as readlines)

You can also loop through the lines in a file
```python
for line in myfile:
    print(line) # this will print the file double spaced
```

You can also use a while loop
```python
next_line = myfile.readline()
while next_line != "":
    print(next_line) # this will also print the file double spaced
    next_line = myfile.readline()
```

Use the `write` command to write to your file. Note that the write command only takes a single string. It does NOT include a newline character (`\n`) so you need to remember to add it to your string.
```python
myfile.write("some text\n")
myfile.write("next line\n")
myfile.write("1+2=")
myfile.write(f"{1+2}")
```

## String Processing
You can remove leading and trailing whitespace (space, tab, and newline characters) from a string using `<str>.strip()`
```python
mystr = "\t      blue sky   \n".strip() # this will remove the spaces at the beginning and end (NOT the middle)
print(mystr)
```
will output `blue sky`

You can split a string into a list of strings using `<str>.split()`. By default, this will split on whitespace (space, tab, and newline characters). Or you can specify which character to split on.
```python
mystr = "line 1\nline 2\nline 3\n"
mylist = mystr.split("\n")
print(mylist)
```
will output `['line 1', 'line 2', 'line 3', '']`. Note the empty string at the end of the list due to the final newline character in the string. To prevent this from happening, use `<str>.strip()` before `<str>.split("\n")`. You can chain these in a single line of code.
```python
mystr = "line 1\nline 2\nline 3\n"
mylist = mystr.strip().split("\n")
print(mylist)
```
will output `['line 1', 'line2', 'line3']`

You can join a list of strings into a single string using `<str>.join(<list of strings>)`
```python
mystr = "\t1,2,3,4,5  \n"
mylist = mystr.strip().split(",")
newlist = []
for i in range(len(mylist)):
    newlist.append(f"{float(mylist[i]) ** 2:.0f}")
newstr = "0".join(newlist)
print(newstr)
```
will output `10409016025`

## Modules
You can import an entire module like this
```python
import math
# type <module name>.<function> or <module name>.<constant> to use what you imported
print(math.cos(math.pi / 4))
```

You can rename an entire module like this
```python
import math as m
# type the redefined name of the module to use what you imported
print(m.sqrt(2))
```

You can import just the functions you want like this
```python
from math import sqrt
# no need to type the module name to use what you imported
print(sqrt(2))
```

You can rename the functions you import like this
```python
from math import sqrt as sr, sin as s, pi as pie
# no need to type the module name to use what you imported
# type the redefined name(s) of the function(s)
print(sr(2))
print(s(pie / 4))
```

Make sure you are familiar with the `numpy` and `matplotlib` tutorials that your team learned in [Lab Topic 12 (team)](https://github.com/tamu-edu-students/engr-102-lab-12-team)

Revised Fall 2026 SNR
