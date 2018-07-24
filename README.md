# Simple OOP Tutorial
This is a simple tutorial on object-oriented programming, in Python.

Let us start with an example. Say you need some variables with names of colors that contain strings of their hexadecimal representation. One way to go about this is to define the variables as follows:
```python
red = 'ff0000'
green = '00ff00'
blue = '0000ff'
```
This is fine, but the method does not scale. Say you are working with hundreds of variables, then you could for instance run into variable name conflicts. It is logical to group these variables in the same class.
```python
class colors:
    red = 'ff0000'
    green = '00ff00'
    blue = '0000ff'
```
