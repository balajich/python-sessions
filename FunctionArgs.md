# Function Arguments
The formal function arguments specified when a function is defined with the def keyword are a comma separated list of the argument names. These arguments can be made optional by providing default values.  There two types of arguments
- Positional (Mandatory)
 - These need to be specified in order
 - These should be first arguments
- Keyword (default argument) (non Mandatory)
 - These can be specified in any order

## Example
```python
def add(x, y=0, z=0):
    # x is called positional argument
    # y, z are called keyword argument
    print("x=", 10, "y=", y, "z=", z)
    return x + y + z
# add()  # This will result error because of missing positional argument: 'x'
add(10, 20)  # x is 10, y is 20
add(10)  # x is 10
add(10, z=10)  # x is 10 and z is 10
# add(y=20)# This will result error  missing 1 required positional argument: 'x'
```
```bash
x= 10 y= 20 z= 0
x= 10 y= 0 z= 0
x= 10 y= 0 z= 10
```
## Default Arguments are evaluated only once
The default argument expressions are evaluated only once when the def statement is executed
## Example
```python
import time
#The default argument expressions are evaluated only once when the def statement is executed
def show_time(arg=time.ctime()):
    print(arg)

show_time()# prints current time
time.sleep(5)# sleep for 5 sec
show_time()# prints current time
```
```bash
Fri May 19 18:47:59 2017
Fri May 19 18:47:59 2017
```
**Note**: The above show_time function prints the time at which function definition is executed. That's the reason though we call show_time() twice it prints same value. Ignoring sleep time
## Be cautious when using mutable  list as default argument
### Potential Bug
```python
def add_spider(heros=[]):
    heros.append("spider")
    return heros

print(add_spider())
print(add_spider(['mario', 'dora']))
# This is a potential bug. instead of adding spider once in list we see it twice
print(add_spider())   
```
```bash
['spider']
['mario', 'dora', 'spider']
['spider', 'spider']
```
### Potential Fix
Always use immutable objects such as integers or strings for default values. Following this advice, we can solve this particular case by using the immutable None object as a sentinel
```python
def add_spider(heros=None):
    if(heros is None):
        heros = []
    heros.append("spider")
    return heros

print(add_spider())
print(add_spider(['mario', 'dora']))
print(add_spider())   
```
```bash
['spider']
['mario', 'dora', 'spider']
['spider']
```
### [index](index.html)
