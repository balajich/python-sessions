# Access to command line arguments
Access to command line arguments in Python is through an attribute of the sys module called argv, which is a list of strings
# Access program arguments
```python
import sys
print("Welcome Mr ",sys.argv[1])
```
```bash
$ python Hello.py Mario
Welcome Mr  Mario
```
**NOTE**  For sophisticated command line processing please refer **argparse** and **docopt** module
### [index](index.html)
