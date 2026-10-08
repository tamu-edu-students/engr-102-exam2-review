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
```
# problem 30
x = 4
y = timestwo(x)
def timestwo(x):
    return x * 2
print(y)
```
```
# problem 31
number = input("Enter a number: ")  # assume the user enters 5.0
try:
    x = int(number)
    print(f"x is the integer {x}")
except:
    x = float(number)
    print(f"x is the float {x}")
```
```
# problem 32
mystr = "Howdy! Welcome to Texas A&M Engineering!"
mylist = mystr.split()
newstr = ""  # empty string
for i in range(3, len(mylist)):
    newstr += mylist[i] + " "
print(mylist[0][:5] + " " + newstr[:-2] + " students! ")
```
```
# problem 33
a, b = 3, 0
countStr = ""  # empty string
while a > b:
    try:
        c = a / b
        countStr += str(a)
    except:
        countStr += str(b)
        a -= 1
countList = list(countStr)
for i in range(len(countList)):
    countList[i] = float(countList[i])
print(sum(countList), countList.count(0), sep=":", end="!")
```
```
# problem 34
mystring = "   \t\n123abc   \n"
out_value = "::".join(mystring.strip().split("23a"))
print(out_value)
```
```
# problem 35
mystring = "AXVRL:2025/11/07"
mylist = mystring.split(":")
mylist[1] = mylist[1].split("/")
for i in range(len(mylist)):
    if i == 0:
        print(mylist[i][-3:], "\t", sep="", end="")  # both empty str
    else:
        print(f"{mylist[i][1]}\t{mylist[i][2]}\t{mylist[i][0]}")
```
```
# problem 36
mylist = [5, 3, 7, 9, 1, 2]
mylist.pop()
mylist.insert(2, 4)
mylist.sort()
for num in mylist:
    print(num, end = " ")
```
```
# problem 37
def output(mystr, num):
    outstring = mystr
    with open("results.csv", "w") as outfile:
        for i in range(num):
            outfile.write(outstring[-1] + ",")
            outstring = outstring[:-1]
        outfile.write(mystr[0])
    return outstring
print(output("tacocat", 6))
```
```
# problem 38
import numpy as np
mygrid = np.arange(1, 10).reshape(3, 3)
for i in range(len(mygrid)):
    mygrid[i][i] = 5
print(mygrid)
```
```
# problem 39
mystr = "2-g:gig'em\n3-s:aggies\n1-o:whoop"
mylist = mystr.split("\n")
good = 0
for item in mylist:
    key, word = item.strip().split(":")
    key = key.split("-")
    if word.count(key[1]) >= int(key[0]):
        good += 1
print(good)
```
```
# problem 40
import numpy as np
x = np.linspace(1.0, 10.0, 10)
y = x ** 2 – 1
with open("zfile.txt", "w") as zfile:
    zfile.write("x\ty\n")
    for i in range(len(x)):
        mystr = str(x[i]) + "\t" + str(y[i])
        zfile.write(mystr + "\n")
with open("zfile.txt") as myfile:
    all_of_it = myfile.read().split("\t")
output = ",".join(all_of_it)
print(output)
```

Problem 41<br>
The file `scores.csv` contains the following text:
```
ID,Score1,Score2,Score3
121,30,50,90
045,90,70,80
217,60,60,85
```
Write the output of the following code.
```
with open("scores.csv") as file1:
    count = 0
    score_dict = {}
    for i in file1:
        i = i.strip().split(",")
        score_dict[i[0]] = i[1:]
del(score_dict["ID"]
avg1, avg2, avg3 = 0, 0, 0
for i in score_dict:
    avg1 += int(score_dict[i][0])
    avg2 += int(score_dict[i][1])
    avg3 += int(score_dict[i][2])
value = [avg1/len(score_dict), avg2/len(score_dict), avg3/len(score_dict)]
print(value)
```

Problem 42<br>
What are the contents of the file `afile2.csv` after the following lines of code have executed?
```
nextfile = open("afile2.csv", "w")
nextfile.write("\t".join("1,2,3\n".split(",")))
nextfile.write("\t".join("4,5,6\n".split(",")))
list1 = ".".join(["5", "6", "7", "8", "9"])
nextfile.write(list1)
nextfile.close()
```
```
# problem 43
mystr = "1.1".join("1,2,3".split(","))
mystr2 = mystr.split(".")
mysum = 0
for num in mystr2:
    mysum += int(num)
print(mysum)
```

Problem 44<br>
Given the list: `my_list = [1, 2, 3, 4, 5]`, which of the following code snippets below will output `1, 3, 5`? Choose all that apply.
```
# answer A
for i in range(0, 5, 2):
    print(my_list[1], end=", ")
```
```
# answer B
i = 0
out = my_list[i]
while i < 4:
    print(out, end=", ")
    i += 2
    out = my_list[i]
print(out)
```
```
# answer C
for i, value in enumerate(my_list):
    if value % 2 == 1 and i < 4:
        print(my_list[i], end=", ")
print(my_list[-1])
```
```
# answer D
i = 1
out = my_list[i]
while i < 5:
    print(out, end=", ")
    i += 2
    out = my_list[i]
print(out)
```
```
# answer E
for i in range(len(my_list)):
    if i % 2 == 0:
        print(my_list[i], end="")
        if i + 1 < len(my_list):
            print(", ", end="")
```
```
# answer F
count = 0
for i in my_list:
    if i % 2 == 1 and count < 4:
        print(i, end=", ")
    elif count == 4:
        print(i)
    count += 1
```
```
# answer G
for i in my_list:
    print(my_list[i], end=", ")
```

Problem 45<br>
Which of the code snippets below produces the same output as: 
```
for i in range(4):
    print(f"{i+1}", end="")
```
Choose all that apply.
```
# answer A
for j in range(4):
    print(f"{j+1}", end="")
```
```
# answer B
i = 0
while i <= 3:
    print(f"{i+1}", end="")
    i += 1
```
```
# answer C
for i in range(1, 5):
    print(i, end="")
```
```
# answer D
for i in range(5):
    if i == 4:
        break
    print(i + 1, end="")
```

Problem 46<br>
After executing the two lines of code below, which of the following potential third lines of code will **NOT** result in an error? Choose all that apply.
```
# Execute the following two lines of code first
the_list = [3, "5", 0]
the_str = "A1B2C3"
## third line of code goes here ##
```
- `1_var = {the_list[1]:the_str}`
- `myvar = the_list[the_str[1]]`
- `a_var = the_list[0] + int(the_str[-1])`
- `some_var = the_str, the_list`
- `the_var = the_str[the_str[2]]`
- `a = the_str[the_list[2]]`

Problem 47<br>
Which of the following lines of code correctly opens an existing file? Choose all that apply.
- `myfile = open("grades.csv", "r")`
- `with open("data.dat", "r+") as my-file:`
- `myfile = open("stats.csv", "w")`
- `with open("datafile.txt", "a") as myfile:`
- `this_file = open("weather.odb", a+)`
- `with open("barcodes.txt") as bfile:`

Problem 48<br>
Which of the following code snippets below will execute without error?
```
# answer A
listA = [1, 2, 3, 4, 5]
listB = [4, 6, 8, 10, 12]
for i in range(5):
    listC += [listA[i] + listB[i]]
print(listC)
```
```
# answer B
listA = [6, 5, 4, 3, 2, 1]
listB = [1, 3, 5, 7, 9, 11]
listC = []
for i in range(1, 7):
    listC += [listA[i] + listB[i]]
print(listC)
```
```
# answer C
myList = [7, 8, 6, 4, 2]
for num in myList:
    if num < 3
        print(item)
```
```
# answer D
data_list = []
numbers.open("data.txt", "r")
for line in numbers:
    data_list.append(line.strip())
print(data_list)
```
```
# answer E
def myfunc(a, b=7, c):
    out1 = a + b / c
    out2 = a – c * b
    return out1, out2
a, b = myfunc(5, 2, 4)
```
```
# answer F
from math import sqrt
def func2(sigma, n):
    error = sigma / sqrt(n)
    return error
def func1(x):
    resid = 0
    avg = sum(x) / len(x)
    for i in x:
        resid += (i – avg) ** 2
    stdev = resid / (len(x) – 1)
    error = func2(stdev, len(x))
    return error
data = [2, 5, 3, 7, 4, 9, 1, 2, 5, 8, 9, 3, 4]
print(func1(data))
```
```
# answer G
from math import sqrt
mylist, square = [1, 3, 5, 7, 9], []
for i in mylist:
    square += i ^ 2
print(sum(square))
```

Problem 49<br>
What are the contents of the file `results.csv` after the following lines of code have executed?
```
def output(mystr, num):
    outstring = mystr
    with open("results.csv", "w") as outfile:
        for i in range(num):
            outfile.write(outstring[-1] + ",")
            outstring = outstring[:-1]
        if len(mystr) – num == 1:
            outfile.write(mystr[0])
        elif num < len(mystr):
            for i in range(len(mystr) – (num + 1), -1, -1):
                outfile.write(outstring[i] + ",")
        return outstring
output("tacocat", 5)
```

Problem 50<br>
Which of the code snippets below will execute without error? Choose all that apply.
```
# answer A
from numpy import *
a = arange(15).reshape(3, 5)
print(a)
```
```
# answer B
import numpy
a = arange(15).reshape(3, 5)
print(a)
```
```
# answer C
from math import *
a = math.sqrt(25)
print(a)
```
```
# answer D
import math
a = math.sqrt(25)
print(a)
```

Problem 51<br>
Write a single line of code to import either an entire module or just the required functions in such a way that the following code executes without error.
```
## Your single line of code here ##
import numpy as np
x = np.linspace(0, 10, 21)
y = 2 * x ** 2 – 6 * x – 4
z = x ** (1 / 2) + 6
a = x
pyp.plot(x, y, "k-", x, z, "rv", x, a, "b1")
pyp.xlabel("Time [ns]")
pyp.ylabel("Space [ly^3]")
pyp.title("Plot of Something Important")
pyp.show()
```

Problem 52<br>
Write a single line of code to import either an entire module or just the required functions in such a way that the following code executes without error.
```
## Your single line of code here ##
x = arange(0, 10.5, 0.5).reshape(7, 3)
```

## Code Writing Problems

## Short Answer Problems
