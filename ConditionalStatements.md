# Conditional statements
Conditional statements allow us to branch execution based on the value of an expression.
```python
if expr:
  print("Exp is True")
```
expr is converted to bool  as if by the bool() Constructor
## if
```python
>>> if True:                        
...     print("It is true!")        
...                                 
It is true!                         
>>> if False:                       
...     print("It is not true")     
...                                 
>>> if bool("hello"):               
...     print("Hello .. Thank you")
...                                 
Hello .. Thank you
>>> if bool(""):                      
...     print("Empty is not true")    
...                                   
>>>
```

## if and else
```python
>>> i=10
>>> if(i==11):
...     print("It is  11")
... else:
...     print("It is 10")
...
It is 10
```
Nested if inside else
```python
>>> i=10
>>> if(i==11):                     
...     print("i is 11")           
... else:                          
...     if(i==9):                  
...         print("i is 9")        
...     else:                      
...         print("i may be 10")   
...
i may be 10                                
```
Whenever you find yourself with an else block containing a nested if statement , you should consider instead using Python's elif keyword, which is a combined else/if
## elif (else/if)
```python
>>> if(i==11):                 
...     print("i is 11")       
... elif(i==9):                
...     print("i is 9")        
... else:                      
...     print("i may be 10")   
...                            
i may be 10
```                    
### [index](index.html)
