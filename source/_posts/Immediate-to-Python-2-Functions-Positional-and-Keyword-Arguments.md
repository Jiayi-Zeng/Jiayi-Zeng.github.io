---
title: "Functions Positional & Keyword Arguments"

date: 2023-02-26

tags: [Python]

categories: "Immediate to Python"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/3050754.png
---

# **1 Positional Arguments**

These are argument that are assigned based on their position in the function definition.  A example below will make this clear.

```python
def print_greeting(username, date):
    """Print a simple greeting"""
    greeting = 'Greetings, {}. The date is {}'.format(username, date)
    print(greeting)
```

```python
# test the function
print_greeting('Ronda', '2019-01-01')
```

Why did the function treat 'Ronda' as the username argument and '2019-01-01' as the date argument? The answer is simple: it is because 'Ronda' was the first argument passed to the function and, in the function definition, username is the first argument in the function signature.

The arguments are assigned by *position*.

# **2 Keyword Arguments**

Keyword arguments are arguments that are passed to a function by the argument name.  For example, when calling the `print_greeting` function we can pass the arguments as shown in the cell below.

```python
my_name = "Will"
today = "2019-07-01"
print_greeting(date=today, username=my_name)

print_greeting(username="Padma", date="2019-03-01")
```

**Sometimes you can't use keyword to specify arguments, and sometimes you can only use keywords to specify certain arguments.**

Many built in Python function are implemented in C and use a position-only API for processing argument. That means that there are some function with arguments that can not be specified by keyword. 

```python
help(sorted)
```

![image-20230301180010676](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230301180010676.png)

Notice the `/` in the function signature above?  This indicates that all the argument to the left of it can ONLY be specified by position. That is you can not pass the 'iterable' argument by keyword. (You may notice the `*` in the signature as well, we will discuss that in a moment)

```python
my_list = [2, 3, 1]

# We incorrectly try to pass the iterable argument by keyword. This will produce an error

# We correctly pass the iterable argument by position
sorted_list = sorted(my_list)
print(sorted_list)
```

Now, what about the `*` in the function signature? This means that you can ONLY specify the arguments to the right of it by keyword.  For example, in the sorted function, the arguments `key` and `reverse` can only be specified by keywords. See an example below:

```python
my_list = ['a_3', 'b_2', 'c_1']

sorted_list = sorted(my_list, key=lambda x: x.split('_')[-1])

print(sorted_list)
```

# **3 Introducing \*args**

Now, take your mind back to positional arguments.  What if you want a function to accept unlimited positional arguments? This is what the `*args` argument can do. By using the `*args` argument in our function definition, all positional arguments will be collected in a **tuple** named `args`. Let's define a function below using the `*args` argument to see how this works

```python
def args_example(*args):
    '''Print the contents of args.'''
    print(args)
    
args_example('Miguel', 'Mary', 'Paul')
# Output: ('Miguel', 'Mary', 'Paul')
```

## 3.1 Combining \*args with other positional arguments.

You can have positional arguments *before* `*args`. `*args` will collect all the extra position arguments passed to the function.

```python
def print_all_the_greetings_2(greeting, *args):
  '''Print "{greeting}, {name} for the greeting and all the names passed as arguments
	'''
	for name in args:
		print("{}, {}".format(greeting, name))
        
print_all_the_greetings_2('Good Morning', 'Winston', 'Aarav', 'Julie')
```

# **4 Introducing \*\*kwargs**

Much like `*args` captures extra positional arguments, `**kwargs` captures extra keyword arguments in a dictionary called `kwargs`.

```python
def kwargs_example(**kwargs):
    """Print kwargs"""
    print(kwargs)
    
kwargs_example(name="Paloma", occupation='teacher')
```

# **5 Mixing Positional and Keyword Arguments.**

When using both positional and keyword arguments you must specify the positional arguments **first**.

```PYTHON
print_greeting(username="Padma", date="2019-03-01")

print_greeting("Padma", date="2019-03-01")
```

## 5.1 Mixing Positional Arguments, \*args, Keyword Arguments and \*\*kwargs

```python
def test_arg_and_kwarg(arg1, arg2, *args, kwarg1, kwarg2, **kwargs):
    print(arg1)
    print(arg2)
    print(args)
    print(kwarg1)
    print(kwarg2)
    print(kwargs)
    return

test_arg_and_kwarg(1, 2, 'extra_1', 'extra_2', kwarg1='kwarg 1',
                   kwarg2='kwarg 2', extra_kwarg1='Bonus!',
                  extra_kwarg2="I'm extra!")
```

# **6 Default Arguments**

Sometimes you want to specify a default argument value to one of the arguments in your function. This means that if no value is passed to that specific argument, it will still have a default value and the function will run successfully.

This is very common. In fact, let's look at the documentation for the built in function `sorted` again.

See the 'key=None' and the 'reverse=False' in the function signature? This indicates that the default value for key is None, and the default value for reverse is False. This means that if we use the sorted function, these will be the values for these arguments if we do not specify other values.

```python
help(sorted)

# Output:
Help on built-in function sorted in module builtins:

sorted(iterable, /, *, key=None, reverse=False)
    Return a new list containing all items from the iterable in ascending order.
    
    A custom key function can be supplied to customize the sort order, and the
    reverse flag can be set to request the result in descending order.
```

## 6.1 You can use \* and \*\* to pass arguments to functions.

Just as we used the \* and \*\* to collection arguments that are passed to a function, you can also use the to pass arguments to a function from a tuple or dictionary.  Let's walk through two examples below.

```python
def my_function(x, y):
    result = x**2-y**(0.5)
    return result
    
# Here we use the function and pass the values directly
result1 = my_function(2.1, 0.6)

# Belww, we define a tuple with the values, and then pass those values to the
# function by indexing them from the tuple.
values = (2.1, 0.6)
result2 = my_function(values[0], values[1])

# Here, we just use the '*' to dump the arguments in the values tuple directly
# to the function
result3 = my_function(*values)

# Finally, print all three results so that we ensure all methods give the same
#result
print(result1, result2, result3)
```

```python
def my_greeting(date, greeting):
    print('{}: {}'.format(date, greeting))
    
# Here we use the function and pass the values directly
my_greeting('2018-11-07', "How are you today?")

# Below, we define a tuple with the values, and then pass those values to the
# function by indexing them from the tuple.
my_greeting(greeting='How are you today?', date='2018-11-07')

# Here, we just use the '*' to dump the arguments in the values tuple directly
# to the function
values = {'greeting': 'How are you today?', 'date': '2018-11-07'}
my_greeting(**values)
```

# **7 An example of a built-in function that actually uses `args` and `kwargs`!**

Now, let's look at a built-in functions that uses both `*args` and `**kwargs`.

The function is the `format` method of string objects.  Depending on which version of the prerequisite course you have taken, you may have already seen this, but we will do a quick review anyways.

## 7.1 The .format() method of a string object.

One of the preferred methods to format strings in Python is to use the format method of string objects. (The latest preferred method is something called 'f strings'). Observe the example below.  First, we define a string and we put `{}` in the string wherever we would like to fill in the string by a variable. We then call the `.format()` method on the string and pass to it the variables we would like to use to fill in the `{}` portions of the string.  The `{}` are filled in by the order we pass the variables to the `.format()` method.

```python 
my_string = 'Hi, my name is {}. I live in {} and I work at {}'.format('Will', 'California', 'UCI')
print(my_string)
```

The point here is that `.format()` can accept *any* number of arguments, it just depend how many `{}` we have to fill in in the string.  How does `.format()` do this? It uses the `*args` argument to capture all of the positional arguments passed, and then it fills in the `{}` in the order of the arguments.

## 7.2 The .format() method also uses kwargs!

Format also supports keywords, observe the example below:

```python
my_string = 'Hi, my name is {name}. I live in {home} and I work at {work}'. \
    format(name='Will', home='California', work='UCI')
print(my_string)
```