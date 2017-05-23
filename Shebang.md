# Shebang
It's common on Unix-like systems to have the first line of a script include a special comment called a shebang. This begins with the usual hash as for any other comment followed by an exclamation mark. The shebang allows the program loader to identify which interpreter should be used to run the program. Shebangs have an additional purpose of conveniently documenting at the top of a file whether the Python code they're in is Python 2 or Python 3. The exact details of your shebang command depend on the location of Python on your system. Typical Python 3 shebangs use the Unix env program to locate Python 3 on your path environment variable, which importantly is compatible with Python virtual environments. A standard Python 3 shebang passes Python 3 to the user bin/env program. Don't worry if you're on Windows. Python includes machinery to make this work on Windows too. On Mac or Linux, we must mark our script as executable using the chmod command before the shebang will have any effect. Having done that, we can now run our script directly.
# Example Hello.py
```python
#!/usr/bin/env python3
import sys
print("Welcome Mr ",sys.argv[1])
```
```bash
$ Hello.py Mario
Welcome Mr  Mario
```
### [index](index.html)
