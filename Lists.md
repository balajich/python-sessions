# Lists
Lists are mutable in so far as the elements within them can be replaced or removed, and new elements can be inserted or appended. Lists are delimited by square brackets, and the items within the list separated by commas.

Elements are zero based index
```python
>>> [1,2,3] # integer list
[1, 2, 3]
>>> ["apple","orange","banana"] # String list
['apple', 'orange', 'banana']
>>> x=["apple","orange","banana"]
>>> x[1]
'orange'
>>> x[1]=9 # lists are mutable
>>> x
['apple', 9, 'banana'] # lists are homogenous
```
# Methods on lists
```python
>>> x=[]            
>>> x.append(1)     
>>> x               
[1]                 
>>> x.append("two")
>>> x               
[1, 'two']          
>>>                 
```
# Constructor of lists
It can be used to create lists from other collections such as strings
```python
>>> list("Welcome to Python")
['W', 'e', 'l', 'c', 'o', 'm', 'e', ' ', 't', 'o', ' ', 'P', 'y', 't', 'h', 'o', 'n']
```
### [index](index.html)
