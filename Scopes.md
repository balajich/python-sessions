# Variable scope and lifetime
Not all variables are accessible from all parts of our program, and not all variables exist for the same amount of time. Where a variable is accessible and how long it exists depend on how it is defined. We call the part of a program where a variable is accessible its scope, and the duration for which the variable exists its **lifetime**.

# Scopes
There are four main type scopes in python.
- Local
- Enclosing
- Global
- Built-in

**Note** : It's important to note that scopes in Python do not correspond to the source code blocks as demarcated by indentation. For-loops, with-blocks, and the like do not introduce new nested scopes.


## Local
Those names defined inside the current function.
### Example 1
```python
def fun():
    i = 10  # local scope
    print("i=", 10)

fun()
print(i)  # this leads to error because i is local scope
```
```bash
i= 10
    print(i)  # this leads to error because i is local scope
NameError: name 'i' is not defined

```
### Example 2
Blocks will not create a new scope
```python
def fun():
    if(1):
        i = 10  # still local scope there is no block scope in python
    print("i=", 10)
fun()

```
```bash
i= 10

```

## Enclosing
Those names defined inside any and all enclosing functions
### Example 1
```python
def outer():
    i = 10
    def inner():
        print("inner i=", i)    
    inner()
    print("Outer i=", i)

outer()
```
```bash
inner i= 10
Outer i= 10
```
### Example 2
```python
def outer():
    i = 10
    def inner():
        i = 30  # This will create new local variable i instead of using outer i
        print("inner i=", i)    
    inner()
    print("Outer i=", i)

outer()
```
```bash
inner i= 30
Outer i= 10
```
### Example 3
```python
def outer():
    i = 10
    def inner():
        nonlocal i
        i = 30  #This will refer outer i
        print("inner i=", i)    
    inner()
    print("Outer i=", i)

outer()
```
```bash
inner i= 30
Outer i= 30
```
### Example 4
```python
def outer():
    def inner():
        i = 10
    inner()
    print("Outer i=", i) # this leads to error because variable in in inner function cannot be accessed out side

outer()
```
```bash
print("Outer i=", i) # this leads to error because variable in in inner function cannot be accessed out side
NameError: name 'i' is not defined
```
## Global
Those names defined at the top level of a module. Each module brings with it a new global scope.
A variable which is defined in the main body of a file is called a global variable. It will be visible throughout the file, and also inside any file which imports that file. Global variables can have unintended consequences because of their wide-ranging effects – that is why we should almost **never use them**.

### Example 1
```python
i = 10  # global scope
def fun1():
    print("fun1 i=", i)
def fun2():
    print("fun2 i=", i)
fun1()
fun2()
```
```bash
fun1 i= 10
fun2 i= 10
```
### Example 2
```python
i = 10  # global scope
def fun1():
    print("fun1 i=", i)
def fun2():
    i = 20  # This will created a new local variable i
    print("fun2 i=", i)
fun1()
fun2()
fun1()
```
```bash
fun1 i= 10
fun2 i= 20
fun1 i= 10
```
### Example 3
```python
i = 10  # global scope
def fun1():
    print("fun1 i=", i)
def fun2():
    global i  # This will refer to global variable i
    i = 20   
    print("fun2 i=", i)
fun1()
fun2()
fun1()
```
```bash
fun1 i= 10
fun2 i= 20
fun1 i= 20
```
## Built-in
Those names built into the Python language through the special built-ins module
### custom_print.py
```python
import sys
def print(x):
    sys.stdout.write("logger message: "+str(99) + '\n')
print(10) # instead of buit in scope print. Global scope print is used
```
```bash
logger message: 99
```
### custom_print_usage_demo.py
```python
from custom_print import  print
print(10) # instead of buit in scope print. Global scope print defined in custom_print module is used
```
```bash
logger message: 99
```
# Assignment operator
```python
a = 0

def fun1():
    print("fun1: a=", a)
def fun2():
    a = 10  # By default, the assignment statement creates variables in the local scope
    print("fun2: a=", a)
def fun3():
    global a  # refer global variable
    a = 5
    print("fun3: a=", a)

fun1()
fun2()
fun1()
fun3()
fun1()
```
```bash
fun1: a= 0
fun2: a= 10
fun1: a= 0
fun3: a= 5
fun1: a= 5
```
## Sum up
```python
# This is a global variable
a = 0

if a == 0:
    # This is still a global variable
    b = 1

def my_function(c):
    # this is a local variable
    d = 3
    print("c=", c)
    print("d=", d)
    print("a=", a)
    print("b=", b)

# Now we call the function, passing the value 7 as the first and only parameter
my_function(7)

# a and b still exist
print("a=", a)
print("b=", b)

# c and d don't exist anymore -- these statements will give us name errors!
print(c)
print(d)

```
```bash
c= 7
d= 3
a= 0
b= 1
0
1
    print(c)
NameError: name 'c' is not defined

```

### [index](index.html)
