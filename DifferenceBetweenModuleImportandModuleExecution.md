# Distinguishing Between Module Import and Module Execution
When the Python interpreter reads a source file, it executes all of the code found in it.

Before executing the code, it will define a few special variables. For example, if the python interpreter is running that module (the source file) as the main program, it sets the special \_\_name\_\_ variable to have a value "\_\_main\_\_". If this file is being imported from another module, \_\_name\_\_ will be set to the module's name.

## Special variable \_\_name\_\_
**\_\_name\_\_** and gives us the means for our module to detect whether it has been run as a script or imported into another module

## calc.py
```python

def add(x, y):
    return x + y

if __name__ == "__main__":
    print("Calc is being run directly, Lets show a demo to use it: add(1,2)", add(1, 2))
else:
    print("Calc is imported into another module")

```
## Run directly calc.py

```bash
mario@myclient:~$ python3 calc.py
Calc is being run directly,Lets show a demo to use it: add(1,2) is
3
```
##  Import calc.py in REPL
```python
>>> import calc
Calc is imported into another module
>>>
```
## Module code is executed only once
observe though calc is imported twice its code is executed only once.
```python
>>> import calc
Calc is imported into another module
>>> import calc
>>>
```
### [index](index.html)
