# Collections In-depth
- Str or string, the immutable sequence of Unicode codepoints
- list, the mutable sequence of objects
- dict, the mutable mapping from immutable keys to mutable objects
- Tuple, the immutable sequence of objects
- Range for arithmetic progressions of integers
- Set, a mutable collection of unique immutable objects.

## Tuples
Tuples in Python are immutable sequences of arbitrary objects. Once created, the objects within them cannot be replaced or removed, and new elements cannot be added
Tuples have a similar literal syntax to lists except that they are delimited by parentheses rather than square brackets.
### student_tuple.py
```python
student = ("dora", 10, 110.5)  # Student tuple with name, age, height
print("student", student)
print("name", student[0], "age", student[1], "height", student[2])  # access elements in the tuple
print("Number of elements in the tuple", len(student))
# Iterate thru items tuple
for item in student:
    print(item)
# concatenate tuple
student = student + (30, 25)  # add weight and bmi
print("student", student)
# Repetition with * operator
print("students", student * 2)

# Nested tuple
rectangle = ((10, 0), (10, 5), (15, 0), (15, 20))
print("Rectangle represented on coordinate plane", rectangle)

# Use index operator to get inner elements in the tuple
print("Co-Ordinate", rectangle[0])
print("Access element inside the Co-Ordinate", rectangle[0][0])

# Single element tuple
student = ("dora",)
print("Single element tuple", student)

# Empty tuple
student = ()
print("Empty tuple", student)

# Parentheses is optional
student = "dora", 10, 110.5  # Student tuple with name, age, height
print("student", student)

# Return tuples
def min_max(items):
    return min(items), max(items)
print("Mix max of the elements in list", min_max([1, 2, 3, 4, 5]))

# Tuple unpacking
# Tuple unpacking is a destructuring operation, which allows us to unpack data structures into named references.
low, high = min_max([1, 2, 3, 4, 5])
print("low", low, "high", high)

print("Simple swapping")
a, b = "hello", "world"
print(a, b)
# swapping
a, b = b, a
print(a, b)

# Constructing tuple from a list
student = tuple(["dora", 10, 110.5])
print("student tuple from list", student)

# Constructing tuple from a string
student = tuple("dora")
print("student tuple from string", student)

# Membership testing
print("5 in (1,2,3,4,5)", 5 in (1, 2, 3, 4, 5))
print("5 not in (1,2,3,4,5)", 5 not in (1, 2, 3, 4, 5))
```
```bash
student ('dora', 10, 110.5)
name dora age 10 height 110.5
Number of elements in the tuple 3
dora
10
110.5
student ('dora', 10, 110.5, 30, 25)
students ('dora', 10, 110.5, 30, 25, 'dora', 10, 110.5, 30, 25)
Rectangle represented on coordinate plane ((10, 0), (10, 5), (15, 0), (15, 20))
Co-Ordinate (10, 0)
Access element inside the Co-Ordinate 10
Single element tuple ('dora',)
Empty tuple ()
student ('dora', 10, 110.5)
Mix max of the elements in list (1, 5)
low 1 high 5
Simple swapping
hello world
world hello
student tuple from list ('dora', 10, 110.5)
student tuple from string ('d', 'o', 'r', 'a')
5 in (1,2,3,4,5) True
5 not in (1,2,3,4,5) False
```
## Str
Str is a homogeneous immutable sequence of Unicode codepoints

- Concatenation of strings is supported using the plus operator
- joining large numbers of strings the join method should be preferred
- We can then split them string using the split() method
- partition(), which divides a string into three sections, the part before the separator, the separator itself, and the part after the separator. Partition returns a tuple, so this is commonly used in conjunction with tuple unpacking.
- Use format() to insert values into strings

### str_indepth.py
```python
# Length of the string
print("length: ", len("Hello World"))

# String concatenation using +
print("concatenation using + operator: ", "Hello" + "World")

# Join Method
print("Join method: ", "".join(["Hello" , "World"]))
print("Join with semicolon: ", ";".join(["Hello" , "World"]))

# split method
print("split by semicolon", "Hello;World".split(";"))

# partitioning
source, seperator, dest = "hyderbad:newyork".partition(":")
print("source, seperator, dest =", source, seperator, dest)

# Use format() to insert values into strings
print("Welcome to {0}".format("India"))
print("Welcome to {0},current temperature is {1} centigrade ".format("India", 30))
print("Welcome to {0}. I hope you like {0}".format("India"))

# If keyword arguments are supplied to formats, then named fields can be used instead of indexes.
print("Welcome to {country}".format(country="India"))

p = (10, 20, 30)
print("Coordinates x={point[0]},y={point[1]},z={point[2]}".format(point=p))

# We pass the whole math module to format using a keyword argument
import math
print("Math constants: pi={m.pi}, e={m.e}".format(m=math))

#Format strings also give us a lot of control over field alignment and floating point formatting.
print("Math constants: pi={m.pi:.3f}, e={m.e:.4f}".format(m=math))
```
```bash
length:  11
concatenation using + operator:  HelloWorld
Join method:  HelloWorld
Join with semicolon:  Hello;World
split by semicolon ['Hello', 'World']
source, seperator, dest = hyderbad : newyork
Welcome to India
Welcome to India,current temperature is 30 centigrade
Welcome to India. I hope you like India
Welcome to India
Coordinates x=10,y=20,z=30
Math constants: pi=3.141592653589793, e=2.718281828459045
Math constants: pi=3.142, e=2.7183
```
## Range
 A range is a type of sequence used for representing an arithmetic progression of integers. Ranges are created by calls to the range constructor.
 ### range__demo.py
```python
# Most typically we supply only the stop value
# range from 0 to 5
print("Range of 5:", range(5))

for i in range(5):
    print(i)

print("range specifying start and stop values")
# range specifying start and stop values
for i in range(5, 10):
    print(i)

# construct list from range
print("List from range", list(range(5)))

# Range with step argument
print("Range with step argument", list(range(5, 10, 2)))

print("Summary")
print("stop argument", range(5))
print("start,stop argument", range(5, 10))
print("start,stop,step argument", range(5, 10, 2))
```
```bash
Range of 5: range(0, 5)
0
1
2
3
4
range specifying start and stop values
5
6
7
8
9
List from range [0, 1, 2, 3, 4]
Range with step argument [5, 7, 9]
Summary
stop argument range(0, 5)
start,stop argument range(5, 10)
start,stop,step argument range(5, 10, 2)
```
**Note:** Because of the strong iteration primitives built into Python, ranges aren't widely used in modern Python code.
## List

```bash
names = ["dora", "spider man ", "papa smurf", "captain america", "mario"]
# The first element of the sequence is at index 0
print("First element in the list", names[0])
print("First element in the list", names[-0])
# The last element of the sequence is at index -1
print("First element in the list", names[-5])


# Slicing is a form of extended indexing which allows us to refer to portions of a list
print("Slicing")
print("Get three elements from index 1", names[1:1 + 3])
print("Get all elements in the except first and last", names[1:-1])
print("Get all elements in the list", names[0:])
print("Get all elements in the list from starting to index 2", names[:2])
print("All elements", names[:2], names[2:])
print("All elements", names[:])

# copying list
# You must be aware, however, that all of these techniques perform a shallow copy. That is, they create a new list containing the same object references as the source list, but don't copy the referred to objects.
names1 = names[:]
print("names1 is names", names1 is names)
print("names1 == names", names1 == names)

names1 = names.copy()
print("names1 is names", names1 is names)
print("names1 == names", names1 == names)

names1 = list(names)
print("names1 is names", names1 is names)
print("names1 == names", names1 == names)

print("Shallow copy demo")
a = [[1, 2], [2, 3]]
acopy = list(a)  # Note shallow copy
acopy[0][0] = 5
print(a[0])
print(acopy[0])
acopy[0] = [-1, -1]  # This is not a problem. We are changing whole element
print(a[0])
print(acopy[0])

# List repetition
l = [1, 2]
print("Repetition: ", l * 3)

print("list with 9 zero elements: ", [0] * 9)

# Note repetition is shallow
l = [0, 1]
new_l = l * 5
print("new_l", new_l)
l.append(-1)
print("new_l", new_l)
print(l)

# finding elements in list
names = ["dora", "spider man ", "papa smurf", "captain america", "mario"]
print("find dora", names.index("dora"))

# count the occurance of elements in the list
print("number of  doras in list", names.count("dora"))
```
```bash
First element in the list dora
First element in the list dora
First element in the list dora
Slicing
Get three elements from index 1 ['spider man ', 'papa smurf', 'captain america']
Get all elements in the except first and last ['spider man ', 'papa smurf', 'captain america']
Get all elements in the list ['dora', 'spider man ', 'papa smurf', 'captain america', 'mario']
Get all elements in the list from starting to index 2 ['dora', 'spider man ']
All elements ['dora', 'spider man '] ['papa smurf', 'captain america', 'mario']
All elements ['dora', 'spider man ', 'papa smurf', 'captain america', 'mario']
names1 is names False
names1 == names True
names1 is names False
names1 == names True
names1 is names False
names1 == names True
Shallow copy demo
[5, 2]
[5, 2]
[5, 2]
[-1, -1]
Repetition:  [1, 2, 1, 2, 1, 2]
list with 9 zero elements:  [0, 0, 0, 0, 0, 0, 0, 0, 0]
new_l [0, 1, 0, 1, 0, 1, 0, 1, 0, 1]
new_l [0, 1, 0, 1, 0, 1, 0, 1, 0, 1]
[0, 1, -1]
find dora 0
number of  doras in list 1

```

### [index](index.html)
