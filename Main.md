# main
Define a main function and call it when user running module as script
# calc.py module
```python
def add(x, y):
    return x + y
def sub(x, y):
    return x - y
def mul(x, y):
    return x * y
def div(x, y):
    return x / y

def main():
    print("add(1,2): ", add(1, 2))

if __name__ == "__main__":
    main()
```
# Execute module as script
```bash
$ python calc.py
add(1,2):  3
```
# In REPL
```python
>>> from calc import *
>>> main()
add(1,2):  3
```
### [index](index.html)
