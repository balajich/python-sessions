# Objects
In Python it's important to remember that everything is an object, primitive objects, functions, modules, and on and on

 We've already talked about and used variables in Python, but what exactly is a variable? What's going on when we do something as straightforward as assigning an integer to a variable? In this case, Python creates an int object with a value of 1000, an object reference with the name X, and arranges for X to refer to the int 1000 object. If we now modify the value of X with another assignment, what does not happen is a change in the value of the integer object. Integer objects in Python are immutable and cannot be changed. In fact, what happens is that Python creates a new **immutable integer** object with the value 500 and redirects the X reference to point at the new object. We now have no way of reaching the int 1000 object, and the Python garbage collector will reclaim it at some point

# Example
```python
x = 1000  # x refers integer object  with value 1000
print("x=", x)
x = 500  # now x refer with value 500, At this point 1000 eligible for garbage collection
print("x=", x)

```
```bash
x= 1000
x= 500
```
# id() function
which returns an integer identifier, which is unique and constant for the lifetime of the object
Much more commonly used than the id() function is the is operator, which tests for equality of identity. That is it tests whether two references refer to the same object.
## Example 1
```python
x = 10
print("id(x) is ", id(x))
y = 20
print("id(y) is ", id(y))
print("id(x) == id(y): ", id(x) == id(y))
```
```bash
id(x) is  1371953024
id(y) is  1371953184
id(x) == id(y):  False
```
## Example 2
```python
x = 10
print("id(x) is ", id(x))
x += 1
print("id(x) is ", id(x))
```
```bash
id(x) is  1371953024
id(x) is  1371953040
```
## Example 3
```python
x = [1, 2, 3]
y = [1, 2, 3]
print("x ", x)
print("y ", y)
print("x is y", x is y)
print("x == y", x == y)
```
```bash
x  [1, 2, 3]
y  [1, 2, 3]
x is y False
x == y True
```
**Note**:
- Value - equivalent "contents"
- Identity  - Same object
- Scalar data types are immutable
- Collections are mutable

## Example 4
```python
# Scalar types are immutables
x = "abc"
y = "abc"
print("x==y", x == y)
print("x is y", x is y)
# Collections are mutable
x = ["a", "b", "c"]
y = ["a", "b", "c"]
print("x==y", x == y)
print("x is y", x is y)
```
```bash
x==y True
x is y True
x==y True
x is y False
```
**Note:** value comparison is something that is defined programmatically. When you define types, you can control how that class determines value equality. In contrast, identity comparison is defined by the language, and you can't change that behavior.

# Argument passing
Objects are passed by copy of reference.

## Example 1
```python
def modify(y):
    y = y + 1  # integer objects are immutable. New object get created and reference is assigned to y
    print("y=", y)
x = 20
print("x= ", x)
modify(x)
print("x=", x)

```
```bash
x=  20
y= 21
x= 20
```
## Example 2
```python
def modify(y):  # y contains copy of reference x
    y.append(4)  # y refer to same object as x
    print("y=", y)
x = [1, 2, 3]
print("x=", x)
modify(x)
print("x=", x)
```
```bash
x= [1, 2, 3]
y= [1, 2, 3, 4]
x= [1, 2, 3, 4]
```
## Example 3
```python
def modify(y):  # y contains copy of reference x
    y = [1, 2, 3, 4]  # a new list object is created and assigned to y
    print("y=", y)
x = [1, 2, 3]
print("x=", x)
modify(x)
print("x=", x)
```
```bash
x= [1, 2, 3]
y= [1, 2, 3, 4]
x= [1, 2, 3]
```
## Example 4
```python
def modify(y):  # y contains copy of reference x
    y = None  # y is referring to NoneType but x reference is still alive
    print("y=", y)
x = [1, 2, 3]
print("x=", x)
modify(x)
print("x=", x)
```
```bash
x= [1, 2, 3]
y= None
x= [1, 2, 3]
```
# Return statement
It returns the same copied reference no new copy of object is created
## Example1
```python
def modify(y):
    return y  # returns same reference. No new object is created
x = [1, 2, 3]
y = modify(x)
print("x == y", x == y)
print("x == y", x is y)
```
```bash
x == y True
x == y True
```
## Example2
```python
def modify(y):
    return [1, 2, 3]  # returns new object
x = [1, 2, 3]
y = modify(x)
print("x == y", x == y)
print("x == y", x is y)
```
```bash
x == y True
x == y False
```
### [index](index.html)
