# Exercises
## Write a python calculator module that has addition, subtraction, multiplication and division functions.
### calc.py
```python
def add(x, y):
    return x + y
def sub(x, y):
    return x - y
def mul(x, y):
    return x * y
def div(x, y):
    return x / y
```
## Create a demo script to use calculator module and import all the functions in it
### calc_demo.py
```python
import calc
print("Add: ",calc.add(1,2))
print("Sub: ",calc.sub(1,2))
print("Mul: ",calc.mul(1,2))
print("Div: ",calc.div(1,2))
```
```bash
$ python calc_demo.py      
Add:  3                    
Sub:  -1                   
Mul:  2                    
Div:  0.5                  
```
## Import only addition function
### calc_demo_only_add.py
```python
from calc import add
print("Add: ",add(1,2))
```
## Import only add as  addition alias
### calc_demo_add_as_alias.py
```python
from calc import add as addition
print("Addition: ",addition(1,2))
```
### [index](index.html)
