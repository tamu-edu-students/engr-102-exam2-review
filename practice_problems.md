# Work in progress, come back later!

# Exam 2 Practice Problems
The following problems are for practice when studying for Exam 2. It is recommended that you attempt them using pencil and paper (NOT an IDE) like you will for the exam. After attempting a problem, check your solution by typing it into your favorite IDE and debug.

The format for exam 2 is the same as exam 1. Several problems (multiple choice, true/false, fill in the blank, etc) will be autograded and no partial credit will be available. Partial credit will be available for code writing problems so please comment your code. 

During the exam calculators are not allowed, you won't need one anyway. In addition, you may NOT use your phone, the web to search for additional information, your laptop, your book, your notes, lectures on Canvas, or any electronic device.

- [Autograded Style Problems](#autograded-style-problems)
- [Code Writing Problems](#code-writing-problems)
- [Short Answer Problems](#short-answer-problems)

## Autograded Style Problems
*Go back and review your quizzes for additional autograded style problems including fill in the blank, multiple choice, multiple answer, and true/false type questions.*

For the following problems, write the output of the code. Don't forget `[]` `{}` and/or `,` as needed. Note that code snippets are intentionally not color coded as your printed exam will also be in black and white.

```
# problem 1
grades = [77, 82, 85, 88, 96, 97]
for i in range(1, 2):
    print(grades[i:-i], end="")
```
```
# problem 2
i = 0
j = -1
while i < 3:
    if j > 1:
        continue
        i += 2
    else:
        i += 1
    j += 1
print(f"{i} + j")
```
```
# problem 3
sum = 1
for i in range(1, 5):
    while i < 3:
        sum += i
        i += 1
        if sum % 2 == 0:
            sum += 1
            break
    else:
        sum *= i
    sum -= 2
print(sum)
```
```
# problem 4
a, i = 0, 3
while a <= 3:
    for i in range(1, 3):
        if i == 1:
            i += 1
            a += 1
        else:
            a += 11
print("\"A\" is for", f"{a}", "Apples", sep=" ", end="!")
```
```
# problem 5
j = 1
for i in range(0, 4, 2):
    print(f"{i+1}", f"{j+1}", sep=", ", end=", ")
    j += 2
print("and that's it", end="...or is it? ")
```
```
# problem 6
mydict = {"Ann" : 18, "Bob" : 20, "Charlie" : 19}
if "Joe" in mydict:
    print("Joe is here")
elif "Ann" in mydict:
    print("Hi Ann")
else:
    print("Anyone?")
```
```
# problem 7
name = {"Two" : "Rosewood"}
name[4] = "Lever"
name[2] = "Calendar"
name["Two"] = "Cartograph"
name["Two"] = "Sunspot"
print(name["Two"], name[2], sep=">")
```
```
# problem 8
mydict = {}
mylist = [1, 2, 3, 4, 5]
mydict["Length"] = len(mylist)
mydict["Max"] = max(mylist)
mydict["Min"] = min(mylist)
mydict["Crazy"] = mylist[1] * mylist[3] - mylist[-1]
for key in mydict:
    print(f"{key}: {mydict[key]}")
```
```
# problem 9
mydict = {"apple" : 2, "orange" : 3}
mydict["banana"] = 4
mylist = []
i = 0
print("Total fruit inventory equals: ", end="")   # empty string
for key in mydict:
    mylist.append(mydict[key])
    if i < len(mydict) – 1:
        print(mylist[i], key + "s", end=" + ")
    else:
        print(mylist[i], key + "s", end=" = ")
    i += 1
print(sum(mylist), "fruit")
```
```
# problem 10
mylist = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55]
mydict = {}
mysum = 0
for i in range(0, len(mylist) – 1, 2):
    if mylist[i] + mylist[i+1] <= 2 * mylist[i] + 4:
        mydict[i] = i + 1
    else:
        mydict[i] = i
for item in mydict:
    mysum += mydict[item]
print(mysum, mydict[4], sep=" : ")
```
```
# problem 11
mylist = ["apples", 4.5, True]
mytuple = ("oranges", 3, False)
mydict = {"bananas" : 2, "strawberries" : 12}
for key in mydict:
    mylist += [mydict[key]]
mytuple = [mytuple, mylist]
mylist[4] = 13
print(mytuple[0][1], mytuple[1][4], sep="00", end="1")
```
```
# problem 12
vector1 = (1, 2, 3)
vector2 = (2, 3, 4)
dotp = vector1 * vector2
print(f"The dot product is {dotp}")
```
```
# problem 13
mystr = "Howdy"
mylist = [2, 0, 2, 0]
mytuple = (mystr, mylist)
mytuple[1][3] = 9
print(mytuple)
```
```
# problem 14
def myfunc(x):
    a = 1
    print(x)
a = 5
myfunc(a)
print(a)
```
```
# problem 15
def plus1_3(x):
    return x + 1, x + 3
print(plus1_3(2)[0])
```
```
# problem 16
def myfun():
    """This function prints a message."""
    print("Gig 'em Aggies!")
help(myfun)
```
```
# problem 17
def myfunc(b, a):
    a = 3
    c = b + a
    return c, a
a, b = 3, 2
a, b = myfunc(a, b)
print(a, f"{b} = {a / b:.0f}", sep=" / ")
```
```
# problem 18
def add1(x):
    if x + 1 < 10:
        return x + 1
    else:
        return "Too big!"
print(add1(1), add1(29))
```
```
# problem 19
def myfunction(a, b=5, c):
    return a * b * c
print(myfunction(1, 2, 3))
```
```
# problem 20
def clip(v, lo=0, hi=10):
    if v < lo:
        return lo
    if v > hi:
        return hi
    return v
print(clip(15), clip(-1), clip(7))
```
```
# problem 21
def myfunc1(x=10, y=3, z=False):
    if z:
        var = x * y
    else:
        var = x / y
    return var
def myfunc2(myvar):
    if myvar > 5:
        return True
    elif myvar < 5:
        return False
    else:
        return 30
print(myfunc2(myfunc1()))
```
```
# problem 22
def myfunc(x, y="Green", z=100, Flag=False):
    if z == 100:
        z += 10
        return z, x
    elif y == "Green":
        Flag = True
        print(x, z)
        return x, z
    return Flag
out1, out2 = myfunc(10)
print(out1, out2)
```
```
# problem 23
def aplus(i):
    j = 0
    while i != 1:
        if i % 2 == 0:
            i /= 2
        else:
            i = i * 3 + 1
        j += 1
    return j
print(aplus(20))
```
```
# problem 24
def drawStar(a=6):
    print("*" * int(a))
a = "4"
drawStar(a)
```
```
# problem 25
def go(x):
    s = ""
    for i in range(1, x + 1):
        for j in range(1, i + 1):
            s += "# "
        s += "=\n"
    return s
print(go(2))
```
```
# problem 26
def combo(n):
    s, i = 0, 0
    while i < n:
        j = 0
        while j < 3:
            s += 1
            if j == 1:
                break
            j += 1
        else:
            s += 10
        i += 1
    return s
print(combo(2))
```
```
# problem 27
def A_function(one, two, three):
    list1 = []
    list2 = []
    for i in one:
        if i <= len(one) – 1:
            list1.append(one[i])
        if i % two == 0:
            list1.append(i)
        elif i % 3 == 1:
            list2.append(i + 1)
        return list1, list2
mylist = [4, 3, 22, 15, 7]
a, b = 3, 2
x, y = A_function(mylist, a, b)
print(y + x)
```
```
# problem 28
def f(a, b=2):
    return a * b
print(f"{f(3)}{f(3, 3)}")  # no space
```
```
# problem 29
def B_function(a, b):
    for i in a:
        if i == 5:
            continue
        if a[i] == "Cat":
            print(f"#{str(b.index(10))} {a[i]} {i}", end=" ")
            x = 2010
            break
a = [5, 10, 15, 20, 25]
b = {"Quinn" : "Cat", "Juliet" : "Dog", "Banjo" : "Dog"}
x = "2017"
B_function(b, a)
print(x)
```

## Code Writing Problems

## Short Answer Problems
