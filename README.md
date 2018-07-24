# Simple OOP Tutorial
This is a simple tutorial on object-oriented programming, in Python. There are many tutorials out there which explain OOP. Many are great, but many are also confusing. This is my take on how to best explain the basics. You may have attempted to read up on OOP before, but not quite understood it, or why you need it. I hope this tutorial can clarify things.

## Table of Contents
* [Static variables](#static-variables)


## Static variables
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
These variables are called class variables, or static variables, because they are static and you do not need to create an instance of the class (aka an object) to get hold of the variables, they belong to the class. The way to access these variables is as follows:
```python
print('Red in hexadecimal is ' + color.red)
```

## Static methods
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
You would call the methods as illustrated in the following example:
```python
print('3 plus 4 is:')
print(arithmetic.add(3,4))
```


## Objects
Great. So we we know about classes, and static variables and static methods. So what does it mean to create an instance of a class, or object, and why do we need this? Again, one reason is related to scaling. Classes and objects helps to organize your code, especially for lots and lots of code. But an even more fundamental reason also has to do with variable scope.

Say you have a car, and a variable associated with it: 'mySpeed'. Say you want a function to increase your speed by a specified amount. Perhaps you have tried something like this before:
```python
mySpeed = 40

def increaseSpeed(x):
    mySpeed = mySpeed + x
```
But this does NOT work. The only way to "hack" this to make it work is to reference 'mySpeed' as a global variable, inside the function.
```python
mySpeed = 40

def increaseSpeed(x):
    global mySpeed
    mySpeed = mySpeed + x
```
The problem is, this is BAD programming practice. It is not a smooth way to work with code, and it is not efficient for doing anything. Rather, the way to approach this problem is to use OOP.
```python
class car:

    def __init__(self):
        self.speed = 0

    def increaseSpeed(self,x):
    	self.speed = self.speed + x

myCar = car()
print 'Speed of my car =', myCar.speed
myCar.increaseSpeed(12)
print 'Speed of my car =', myCar.speed
```
If you create a class that you plan to make instances of (create objects), you must include what is called the constructor, which is the '__init__' function. The 'self' keyword is a generic variable which refers to the object, in the class. The constructor must at least take 'self' as an argument. The attributes (properties) of the object are defined in the constructor. If we make an instance of our 'car' class, that object has one attribute: speed. We access that attribute by calling 'self.speed'. Also note that we pass 'self' in our 'increaseSpeed' function, so that we can access the attributes of the object in the function.

## Another example
Let us look at another class example.
```python
class car:

    def __init__(self,brand,color):
        self.brand = brand
	self.color = color
	self.speed = 0

    def increaseSpeed(self,x):
        self.speed = self.speed + x

    def decreaseSpeed(self,x):
        self.speed = self.speed - x

myCar = car('BMW','blue')
myCar.increaseSpeed(50)
```
