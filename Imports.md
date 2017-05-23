# import
import functions, classes , objects ,variables from a moudle

# calc.py Module
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
# Import only one function from module
```python
>>> from calc import add
>>> add(1,2)
3
>>> sub(1,2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'sub' is not defined
```
# Import multiple functions from module
```python
>>> from calc import (add,sub)   
>>> add(1,2)                     
3                                
>>> sub(1,2)                     
-1                               
>>>                              
```
# Import all function from the module
```python
>>> import calc    
>>> calc.add(1,2)  
3                  
>>> calc.sub(1,2)  
-1                 
>>> calc.mul(1,2)  
2                  
>>>                
```
# Import all function from the module only for REPL
```python
>>> from calc import *  
>>> add(1,2)            
3                       
>>> mul(1,2)            
2                       
>>> sub(1,2)            
-1                      
>>>                     
```
### [index](index.html)
