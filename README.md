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
class color:
    red = 'ff0000'
    green = '00ff00'
    blue = '0000ff'
```
The way to access these variables is as follows:
```python
myColor = color.red
```
These variables are called class variables, or static variables, because they are static and you do not need to create an instance of the class (aka an object) to get hold of the variables, they belong to the class.

There are also such things called class (or static) methods/functions. Say you have a set of functions which are related, then similarly you can group them in the same class:
```python
class arithmetic:
    @staticmethod
    def add(a,b):
        return a+b
    @staticmethod
    def subtract(a,b):
        return a-b
```
