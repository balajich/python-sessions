# Data Types in Python

## Scalar Types
Python comes with a number of built-in data types. These include primitive scalar types like integers, as well as collection types like dictionaries

ScalarTypes are
- int (42 bit)
- float (64 bit)
- None (The null object)
- bool (Ture or False)

Integers in Python are signed, literals in Python are specified in decimal, but may also be specified in binary with a 0b prefix, up top with a 0o prefix, or hexadecimal with a 0x prefix.
```python
>>> x=3 #base 10
3
>>> x=0b11 # base 2
3
>>> x=0o3 # base 8
3
>>> x=0x3 # base 16
3
# The above all represent numeric 3 with base 10
```
###  int
```python
>>> int(3.5) # Convert float to integer
3
>>> int(-3.5)
3
>>> int("123") # Convert String to Integer
123
>>> int("11",2) # Convert binary string to decimal
3
```
###  float
```python
>>> 3.141          
3.141              
>>> 3e8            
300000000.0        
>>> 1.6e-35        
1.6e-35            
>>> float(7) #convert integer to float       
7.0                
>>> float("1.23") # convert string to float
1.23               
>>> float("nan") # not a number  
nan                
>>> float("inf") # positive infinity  
inf                
>>> float("-inf")  # Negative infinity
-inf         
>>> 3+4.5 # integer + float is a float
7.5             
```
### None Type
Python has a special null value called None with a capital N. None is frequently used to represent the absence of a value. The Python REPL never prints None results, so typing None into the REPL has no effect. None can be bound to a variable name just like any other object, and we can test whether an object is None by using Python's is operator.
```python
>>> None #it never prints result
>>>
>>> a=None         
>>> type(a)        
<type 'NoneType'>  
>>> a is None      
True               
```
## bool Type
The bool type represents logical states and plays an important role in several of Python's control flow structures.
There are two bool values
- True
- False

```python
>>> True    #bool value   
True           
>>> False      
False          
>>> bool(0)  # convert integer to bool, except 0 all are true  
False          
>>> bool(143)  
True           
>>> bool(-143)
True    
>>> bool(0.0) # Convert from float bool, applies same rules are integer  
False          
>>> bool(1.0)  
True           
>>> bool(-1.0)
True     
#converting from collections
>>> bool([])  # Empty collections are false
False         
>>> bool([1,4,3]) # converting list to bool
True
>>> bool("") # converting empty string to bool
False
>>> bool("hello")
True
>>> bool("False") # False is not any empty string
True
>>>
```
### [index](index.html)
