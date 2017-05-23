# str (String)
Strings in Python have the data type str spelled S-T-R.Strings are sequences of Unicode codepoints, and for the most part you can think of codepoints as being like characters, although they aren't strictly equivalent. The sequence of characters in a Python string is **immutable** meaning that once you've constructed a string you can't modify its contents. Literal strings in Python are delimited by quotes. You can use single quotes or double quotes.

**Default source encoding for python is UTF-8**
```python
s='This is a string'
s="This is also a string"
```
## Adjacent literal strings
These concatenated by the Python compiler into a single string
```python
>>> "Hello"  "World!"
'HelloWorld!'
>>>
```
## Multiline strings
Multiline strings are delimited by three quote characters rather than one
```python
>>> """This is
... a multi line
... string"""
'This is \na multi line\nstring'
>>> m="This is \na multi line\nstring" # or embed new line character
>>> m
'This is \na multi line\nstring'

```
If you're working on Windows, you might be thinking that new lines should be represented by the carriage return at new line couplet \r\n. There's no need to do that with Python since Python 3 has a feature called universal newlines support, which translates from the simple \n to the native newline sequence for your platform on input and output. You can read more about universal newlines support in PEP278.
## Escape sequences \
```python
>>> "Hello \"world!\" "
'Hello "world!" '
>>> message="Hello \\ world "
>>> print(message)
Hello \ world
```
## Raw Strings
 particularly when dealing with strings such as Windows file system paths or regular expression patterns, which use backslashes extensively, the requirement to double up on backslashes can be ugly and error prone. Python comes to the rescue with its raw strings. Raw strings don't support any escapes sequences and are very much what you see is what you get.

 To create a raw string, prefix the opening quote with a lowercase **r**
 ```python
>>> path=r"c:\users\mario\docs"
>>> path
'c:\\users\\mario\\docs'
```
## Convert other types to string
 ```python
 >>> str(143) # integer to string
'143'
>>> str(1.5) # float to string
'1.5'
 ```
## Sequence types
We can access individual characters using square brackets with an integer zero-based index.
```python
>>> s="mario"
>>> s[0]
'm'
>>> print(s[2])
r
>>> type(s[2])
<class 'str'>
 ```
# Methods of String object

```python
>>> c="delhi"     
>>> c.capitalize() # strings are immutable
'Delhi'           
>>> c             
'delhi'
>>> x="hello world"
>>> x.split()
['hello', 'world']          
```
# UTF-8 characters
```python
>>> message="పైథాన్ కు స్వాగతం"
>>> message
'పైథాన్ కు స్వాగతం'
```
### [index](index.html)
