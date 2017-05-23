#Module
# Modules
 Simply, a module is a **file** consisting of Python code. A module can define functions, classes and variables
## Define module
Create a python script file **calc.py**
```python
def add(x, y):
    return x + y
def sub(x, y):
    return x - y
```
## Import module into repel
```python
>>> import calc
```
Imports all the functions in **calc.py**
Note: calc.py should be available in the same directory that you launched python shell
## Use the functions defined  in  calc module
```python
>>> import calc
>>> calc.add(10,20)
30
>>> calc.sub(10,20)
-10
>>>
```
## Import only specific functions
```python
>>> from calc import add
>>> add(10,20)
30
>>> sub(10,20)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'sub' is not defined
```
### [index](index.html)
