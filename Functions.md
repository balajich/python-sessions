# Functions
 Functions are defined using the def keyword followed by the function name, an argument list in parentheses, and a colon to start a new block. We use the return keyword to return a value form the function.
 ## Function
```python
def function_name(parameters):
    #function block
    return [expression]
```
## Function doesn't return
```python
>>> def hello_world():
...     print("Hello world")
...
>>> hello_world() # Calling the function from REPL Environment
Hello world
```

## Function with explicit return
```python
>>> def hello_world():                         
...     print("Hello World")                   
...     return                                 
...     print("This will not be executed")     
...                                            
>>> hello_world()                              
Hello World                                    
>>>                                            
```
Functions aren't required to explicitly return a value though. Perhaps they produce side effects. You can return early from a function by using the return keyword with no parameter. A return keyword without a parameter, or the implicit return at the end of a function, actually causes the function to return None, although remember that the REPL doesn't display None results, so we don't see them. By capturing the returned object into a named variable, we can test for None.

## Capture return values of a function
```python
>>> def add(a,b):
...     return a+b
...
>>> x=add(10,20) # calling add function and capturing result to x
>>> x
30
```
## Functions return none types
```python
>>> def add(x,y):
...     x+y
...
>>> sum=add(10,20)
>>> sum
>>> type(sum)
<class 'NoneType'>
>>> sum is None
True
```
## Print is not equivalent to return
```python
>>> def add(x,y):       
...     print(x+y)      
...                     
>>> sum=add(10,20)      
30                      
>>> sum                 
>>>                     
>>> sum is None         
True                    
```
### [index](index.html)
