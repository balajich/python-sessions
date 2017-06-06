# Exception and Control Flow
Example that effects the control flow
## Example :control_flow_demo.py
```python
''' A module for demonstrating exceptions '''
def convert(s):
    ''' convert string to an integer '''
    x = int(s)
    return x

if __name__ == "__main__":
    print("Convert String to int", convert("10"))
    # This will cause exception
    print("Convert String to int", convert("Hello world"))
```
```bash
Convert String to int 10
Traceback (most recent call last):
    print("Convert String to int", convert("Hello world"))
      x = int(s)
ValueError: invalid literal for int() with base 10: 'Hello world'
```
- **ValueError** is  exception object
- **invalid literal for int()**  payload of the exception object

## Handling Exceptions
Both the try and except keywords introduce new blocks.
- The **try** block contains code that could raise an exception
- **except** block contains the code which performs error handling in the event that an exception is raised
**Note:** The statements in the try block after the point at which the exception was raised was not executed

### Example handle_exception_demo.py

```python
''' A module for demonstrating exceptions '''
def convert(s):
    ''' convert string to an integer '''
    try:
         x = int(s)
         print("Conversion is successful!")
    except ValueError:
        x = -1
        print("Conversion is failed!")
    return x

if __name__ == "__main__":
    print("Convert String to int", convert("10"))
    print("Convert String to int", convert("Hello world"))
```
```bash
Conversion is successful!
Convert String to int 10
Conversion is failed!
Convert String to int -1
```
### type_error.py
Handle the wrong types that was passed. User is passing list of integers instead of int

```python
''' A module for demonstrating exceptions '''
def convert(s):
    ''' convert string to an integer '''
    try:
         x = int(s)
         print("Conversion is successful!")
    except ValueError:
        x = -1
        print("Conversion is failed!")
    except TypeError:
        x = -1
        print("Conversion failed. Wrong Type!")
    return x

if __name__ == "__main__":
    print("Convert String to int", convert("10"))
    print("Convert String to int", convert([1, 2, 3, 4]))
```
```bash
Conversion is successful!
Convert String to int 10
Conversion failed. Wrong Type!
Convert String to int -1
```
### except_tuple.py
Now you except tuple in exception handler.

```python
''' A module for demonstrating exceptions '''
def convert(s):
    ''' convert string to an integer '''
    try:
         x = int(s)
         print("Conversion is successful!")
    except (ValueError, TypeError):
        x = -1
        print("Conversion is failed!")
    return x

if __name__ == "__main__":
    print("Convert String to int", convert([1, 2, 3, 4]))
```
```bash
Conversion is failed!
Convert String to int -1
```
## Exceptions for programmer errors
- IndentationError
- SyntaxError
- NameError

**You should not normally catch these**

## Handle empty except block
The solution arrives in the form of the **pass** keyword, which is a special statement which does precisely nothing. It's a NOOP, and its only purpose is to allow us to construct syntactically permissible blocks which are semantically empty.

```python
''' A module for demonstrating exceptions '''
def convert(s):
    ''' convert string to an integer '''
    x = -1
    try:
        x = int(s)
    except (ValueError, TypeError):
        pass
    return x

if __name__ == "__main__":
    print("Convert String to int", convert([1, 2, 3, 4]))
```
```bash
Convert String to int -1
```
## Exception object (exception_object.py)
We can get a named reference to the exception object by tacking an as clause onto the end of the except statement
```python
''' A module for demonstrating exceptions '''
import sys

def convert(s):
    ''' convert string to an integer '''
    x = -1
    try:
        x = int(s)
    except (ValueError, TypeError) as e:
        print("Conversion error:{}".format(str(e)), file=sys.stderr)
    return x

if __name__ == "__main__":
    print("Convert String to int", convert([1, 2, 3, 4]))
```
```bash
Convert String to int -1
Conversion error:int() argument must be a string, a bytes-like object or a number, not 'list'
```
## Re-Raising Exceptions (raise_demo.py)
If you are not willing to handle exception, you can use **raise** to throw it back to caller
```python
''' A module for demonstrating raise '''
import sys

def convert(s):
    ''' convert string to an integer '''
    try:
        return int(s)
    except (ValueError, TypeError) as e:
        print("Conversion error:{}".format(str(e)), file=sys.stderr)
        raise

if __name__ == "__main__":
    print("Convert String to int", convert("1,234"))

```
```bash
Conversion error:invalid literal for int() with base 10: '1,234'
Traceback (most recent call last):
  File "raise_demo.py", line 13, in <module>
    print("Convert String to int", convert("1,234"))
  File "raise_demo.py", line 7, in convert
    return int(s)
ValueError: invalid literal for int() with base 10: '1,234'
```
## Returning exception objects
You can throw an exception object from the code

### raise_demo_1.py

```python
''' A module for demonstrating raise '''
import sys

def div(x, y):
    ''' convert string to an integer '''
    if y == 0:
        raise ValueError("y cannot be zero {}".format(y))
    return x / y

if __name__ == "__main__":
    print("Division div(10,5) ", div(10, 5))
    print("Division div(10,0)", div(10, 0))

```
```bash
Division div(10,5)  2.0
Traceback (most recent call last):
    print("Division div(10,0)", div(10, 0))
    raise ValueError("y cannot be zero {}".format(y))
ValueError: y cannot be zero 0
```
### raise_demo_2.py
```python
''' A module for demonstrating raise '''
import sys

def convert(s):
    ''' convert string to an integer '''
    if not isinstance(s, int):
        raise TypeError("Argument {} must be number".format(s))
    return int(s)

if __name__ == "__main__":
    print("Convert String to int", convert("abc"))
```
```bash
Traceback (most recent call last):
  File "raise_demo_2.py", line 11, in <module>
    print("Convert String to int", convert("abc"))
  File "raise_demo_2.py", line 7, in convert
    raise TypeError("Argument {} must be number".format(s))
TypeError: Argument abc must be number
```

## Exisiting Exceptions
Often if you're deciding what exceptions your code should raise, you should look for similar cases in existing code. The more your code follows existing patterns, the easier it will be for people to integrate and understand.
- KeyError to indicate a request for a nonexistent key because this is how dictionary works
- IndexError is raised when an integer index is out of range
- ValueError is raised when the object is of the right type, but contains an inappropriate value


### [index](index.html)
