# Bytes
Bytes are very similar to strings except that rather than being sequences of Unicode codepoints, they are sequences of well, **bytes**. As such, they are used for raw binary data and fixed with single byte character encodings such as ASCII.
```python
>>> x=b'some bytes'
>>> x
b'some bytes'
>>> x.split()
[b'some', b'bytes']
```
# Note
It's crucial to understand since files and network resources such as HTTP responses are transmitted as byte streams whereas we prefer to work with the convenience of Unicode strings
### [index](index.html)
