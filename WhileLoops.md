# While loops
Python has two types of loops, for loops and while loops.While loops in Python are introduced by the while keyword, which is followed by a Boolean expression. As with a condition for if statements, the expression is implicitly converted to a Boolean value as if it had been passed to the bool constructor. The while statement is terminated by a colon because it introduces a new block.
```python
while expr:
    print("loop while expr is True")
# expr is implicitly converted to a Boolean value as if it had been passed to the bool constructor
```
Example that loops from 5 to 1
```python
>>> i=5               
>>> while i!=0:       
...     print(i)      
...     i=i-1         
...                   
5                     
4                     
3                     
2                     
1        
```
Shorter form:

To use the short form of this case might be described as unphythonic because referring back to The Zen of Python explicit is better than implicit, and we place a higher value on the readability of the first form over the concision of the second form
```python
>>> i=5           
>>> while i:      
...     print(i)  
...     i=i-1     
...               
5                 
4                 
3                 
2                 
1                 
```
## Breaking out
The break keyword terminates the innermost loop, transferring execution to the first statement after the loop
```python
while True:
    if expr:
        break
print("Time to take break :)")
```
Python doesn't have do while loop

Break the loop when i is 2
```python
>>> while i>=0:   
...     print(i)  
...     if(i==2):
...         break
...     i=i-1     
...               
5                 
4                 
3                 
2
```               
### [index](index.html)
