# Type System
Python can be characterized as having a dynamic and strong type system. Dynamic typing means that the type of an object reference isn't resolved until the program is running and needn't be specified up front when the program is written.
## Dynamic Type system
In a dynamic type system objects types are only resolved at runtime
```python
def add(x, y):
    print(x + y)
add(1, 2) # add int
add(10.1, 11.2) # add float
add("abc", "xyz")# add string
add([1, 2], [3, 4]) # add list
```
```bash
3
21.299999999999997
abcxyz
[1, 2, 3, 4]
```
## Strong type system
Common definition is that the language will not in general implicitly convert objects between types
```python
def add(x, y):
    print(x + y)
add("This is string", 10)  # This leads to error     
```
```bash
print(x + y)
TypeError: must be str, not int
```
**Note**: The exception being the conversion to bool used for if statements and while-loop predicates.

## Object references (variables) has no types
```python
x = "abc"  # x is binded to string
print(x)
x = 1  # x can be rebinded to integer
print(x)
```
```bash
abc
1
```
### [index](index.html)
