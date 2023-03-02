---
title: "Python Scripts and Functions"

date: 2023-02-19

tags: [Python]

categories: "Immediate to Python"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/20230225%20(2).png

toc: true
---

# **Sysargv**

```python
'''
This is a simple script.
'''
import sys

print(__doc__)	# output: docstring

print(sys.argv)	# output: System argument vector
```

# **Argparse**

## Example 1

```python
'''
This is a simple script.
'''
import argparse

parser = argparse.ArgumentParser(description=__doc__)
parser.add_argument('echo', help="the string you want to write to the file")
args = parser.parse_args()
print(args.echo)
```

**Output:**

![image-20230226181135214](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230226181135214.png)

## Example 2

```python
import argparse

parser = argparse.ArgumentParser(description=__doc__)
parser.add_argument('x', help="the value for x", type=int)
parser.add_argument('y', help="the value for y", type=int)
parser.add_argument('-f', '--formula', help="the formula you'd like to run",
                    choices=["power", "subtract"], default="power")

args = parser.parse_args()

if args.formula == "power":
    print(args.x ** args.y)
elif args.formula == "subtract":
    print(args.x - args.y)

```

**Output:**

![image-20230226183445409](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230226183445409.png)

# **Function Docstring**

## One-line Docstring

This is a simple function with a simple one-line docstring. Notice how the docstring is written as a command, "Return the value..." not a description "This function returns the value..."

```py
def add_2(num):
    """Return the value of num + 2."""
    return_num = num + 2
    return num
```

### Printing Docstrings

We can print doc strings by printing the **__doc__** attribute of the function.  This is a built-in attribute and all objects have it (even if the value is None).

Many editors and IDEs have special functionality / commands to print docstrings. For example, if you write the '?' key after a function name, in Jupyter Notebook, and then evaluate the cell, it will open a window with the docstrings.  See the example below.

```py
# Below is an example of printing the docstring directly
print(add_2.__doc__)
```

![image-20230226185514333](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230226185514333.png)

```py
help(add_2)
```

![image-20230226185537947](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230226185537947.png)

```python
# Below is an example of using Jupyter Notebooks '?' command
add_2?
```

## Multi-line Docstrings

A multi-line docstring provide more information but it still starts with single line description, followed by a blank line, and then a more detailed description. The more detailed description includes a description of the arguments, the return value(s), exceptions that the function raises, and any side effects.  It may also included references to similar functions and other helpful information.

```py
def circle(radius):
    """Return the circumference and area of a circle, given the radius.
    
    Parameters
    ----------
    radius : float, int
        the radius of the circle.
        
    Returns
    -------
    circumference : float
        the circumference of the circle.
    
    area : float
        the area of the circle.
    
    """
    circumference = 2*math.pi*radius
    area = math.pi*(radius**2)
    return circumference, area
```

### Printing Docstrings

```python
# method 1
print(circle.__doc__)

# method 2
circle?
```

![image-20230226191611138](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230226191611138.png)