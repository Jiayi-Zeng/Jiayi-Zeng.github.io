---
title: "Understanding Namespace & Scope"

date: 2023-03-05

tags: [Python]

categories: "Immediate to Python"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/03050801.png

---

# **1 Namespaces**

## 1.1 The Global Namespace

t is a collection of names that map to objects (variables, functions, etc...) that have been created in our code. Anytime we run a python script (or a jupyter notebook), a global namespace is created. We can print the names that are in the global namespace with the `dir()` function.

```python
# use the dir() function to return the list of names in the namespace and use print() to print that list.
print(dir())
```
**output:**

```
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '__vsc_ipynb_file__', '_dh', '_i', '_i1', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'quit']
```

**Adding our own names to the global namespace**

We can add our own names very easily, all we need to do is create a new object.  Everything in python is an object, so if we create a variable or a function or a instance of a class, it will be added to the global namespace. 

```python
my_var = "Will"
print(dir())
```
**output:**

```
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '_dh', '_i', '_i1', '_i2', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'my_var', 'quit']
```

**Names in a namespace are unique - you can not have duplicates**

If we assign the variable name `my_var` another value, we will not be able to use `my_var` to access the previous value. In other words, you can not have two variables named `my_var` in the same namespace. You can not have two objects with the same name in the same namespace. 

**Let's now create a function and see that added to the global namespace**

```python
def reverse_string(string):
    '''Return the reverse of a string
    '''
    reverse_string = string[::-1]
    return reverse_string

print(dir())
```

**output:** 

```
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '_dh', '_i', '_i1', '_i2', '_i3', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'my_var', 'quit', 'reverse_string']
```

```python
my_string = 'Hello'
my_string_reversed = reverse_string(my_string)
print(my_string_reversed)
print(dir())
```

**output:**

```
olleH
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '_dh', '_i', '_i1', '_i2', '_i3', '_i4', '_i5', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'my_string', 'my_string_reversed', 'my_var', 'quit', 'reverse_string']
```

**Let's import a package and see that added to our namespace**

```python
import pandas
print(dir())
```

**output:**

```
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '_dh', '_i', '_i1', '_i2', '_i3', '_i4', '_i5', '_i6', '_i7', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'my_string', 'my_string_reversed', 'my_var', 'pandas', 'quit', 'reverse_string']
```

**Each package/module also has its own global namespace.**

This is important to understand. Each python module (a module is simply a .py file that contains functions, classes, and variables) has their own global namespace.

## 1.2 The Local Namespaces

A local namespace and a global namespace can exist at the same time.

The code works because any variable created inside the function is not created in the global namespace, but it is created in what's called a ***\*local namespace\****. This namespace is local to the function (each function has its own local namespace).

```python
my_text = "I am outside the function and in the notebook's GLOBAL namespace!"

def my_func():
    my_text = "I am inside the function and in the function's LOCAL namespace!"
    print(my_text)
    return

# Now run the function
my_func()
# Print my_text
print(my_text)
```

**Output:**

```
I am inside the function and in the function's LOCAL namespace!
I am outside the function and in the notebook's GLOBAL namespace!
```

**Let's now add `dir()` to the body of the function so that we can print the names in the function's local namespace**

```python
my_text = 'I am outside the function in the notebooks GLOBAL namespace!'
print("These are the names in the global namespace:")
print(dir(), '\n')

def my_func_b():
    my_text = "I am inside the function in the function's LOCAL namespace!"
    print("These are the names in the function's local namespace:")
    print(dir(), '\n')
    print(my_text)
    return

# Now run the function
my_func_b()
# Print my_text
print(my_text)
```

```
These are the names in the global namespace:
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '_dh', '_i', '_i1', '_i2', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'my_func', 'my_text', 'quit'] 

These are the names in the function's local namespace:
['my_text'] 

I am inside the function in the function's LOCAL namespace!
I am outside the function in the notebooks GLOBAL namespace!
```

**There can be multiple local namespaces**

Each function has its own local namespace.

```python
my_text = 'I am outside the function in the notebooks GLOBAL namespace!'
print("These are the names in the global namespace:")
print(dir(), '\n')

def my_func_1(my_text_1):
    print("These are the names in the 1st function's local namespace:")
    print(dir(), '\n')
    print(my_text_1, '\n')
    return

def my_func_2(my_text_2):
    print("These are the names in the 2nd function's local namespace:")
    print(dir(), '\n')
    print(my_text_2, '\n')
    return

# Now run the function
my_func_1("Hello!")

my_func_2("Goodbye!")
# Print my_text
print(my_text)
```

```
These are the names in the global namespace:
['In', 'Out', '_', '__', '___', '__builtin__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', '_dh', '_i', '_i1', '_i2', '_i3', '_i4', '_ih', '_ii', '_iii', '_oh', 'exit', 'get_ipython', 'my_func', 'my_func_1', 'my_func_2', 'my_func_b', 'my_text', 'quit'] 

These are the names in the 1st function's local namespace:
['my_text_1'] 

Hello! 

These are the names in the 2nd function's local namespace:
['my_text_2'] 

Goodbye! 

I am outside the function in the notebooks GLOBAL namespace!
```

