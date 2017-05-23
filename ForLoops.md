# for-loop
Visit each item in an iterable series
For-loops in Python correspond to what are called for-each loops in many other programming languages
## Syntax
```python
for item in iterable:
    ...body...
```
## Iterate through list
```python
>>> fruits=["Apple","Mango","Banana"]
>>> for fruit in fruits:
...     print(fruit)
...
Apple
Mango
Banana
```
## Iterate through dictionary
```python
>>> students={"tom":70,"ram":60,"dora":30} # Student marks     
>>> for name in students:                       
...     print(name,students[name])              
...                                             
ram 60                                          
tom 70                                          
dora 30                                         
```
### [index](index.html)
