# Docstrings
 Let's look at how to add this self-documenting capability to our own module. API documentation in Python uses a facility called docstrings. Docstrings are literal strings, which occur as the first statement within a named block, such as a function or module.  Let's document the **add** function in calc module

# calc.py module
```python
"""Contains basic mathematical functions
Usage:
    import calc
    calc.add(1,2)
"""
def add(x, y):
    """ addes two numbers.
    Args:
       x: argument 1
       y: argument 2
    Returns:
       returns of sum of x and y       
    """
    return x + y
```
# Accessing documentation of add function in calc module in REPL
```bash
>>> from calc import *                      
>>> help(add)                               
Help on function add in module calc:        

add(x, y)                                   
    addes two numbers.                      
    Args:                                   
       x: argument 1                        
       y: argument 2                        
    Returns:                                
       returns of sum of x and y            
```
# Accessing calc module documentation
```bash
>>> help(calc)                            
Help on module calc:                      

NAME                                      
    calc                                  

DESCRIPTION                               
    Contains basic mathematical functions
    Usage:                                
        import calc                       
        calc.add(1,2)                     

FUNCTIONS                                 
    add(x, y)                             
        addes two numbers.                
        Args:                             
           x: argument 1                  
           y: argument 2                  
        Returns:                          
           returns of sum of x and y      
```                                        
 ### [index](index.html)
