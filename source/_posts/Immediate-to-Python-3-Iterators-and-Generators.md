---
title: "Iterators and Generators"

date: 2023-02-27

tags: [Python]

categories: "Immediate to Python"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/20230225%20(1).png

---

# **Iterators**

## Another look at `range()`

The `range()` function returns an iterator that will iterate through the values that we specify when we call `range()`.

The iterator only calculates and yields one value at a time.  It does not calculate or store those numbers in memory up front, it calculates them only when they are needed, one at a time.

```python
my_range = range(11, 23)
for x in my_range:
    print(x)
```

## File Object Are Also Iterators

You may have remembered from the prerequisite course how we opened files and iterated through the lines one at a time. The main takeaway is that each line is read in (iterated through) one at a time.  The entire file is not read up-front, each line is read into this notebook one at a time, as needed.

```python
filepath = os.path.join(os.getcwd(), 'AAA_Fuel_Prices.csv')
count = 0
with open(filepath, 'r') as my_file:
    for line in my_file:
        line = line.strip()
        print(line)
        count += 1
        if count > 10:
            break
```

## Iterators Can Also Be Made From Lists (as well as other data types)

Iterators can also be made out of lists. This is what happens when we use a list in a for loop.

```python
my_list = [1, 2, 3, 4, 5]
for x in my_list:
    print(x)
```

```python
my_list_iterator = iter(my_list)

print(type(my_list_iterator))
print(my_list_iterator.__next__())
print(my_list_iterator.__next__())
print(my_list_iterator.__next__())
```

# **Generators**

You may wonder how can we write functions, like `range()`, that return iterators that we can iterate through. We can!  In order to do so, we must use the keyword `yield` instead of `return`.

## Our Own Version Of Range

Let's write our own version of the `range()` function.  We need to write a function the will yield numbers between a beginning and ending number. Note that when the function reaches the yield keyword, it will return that value (in this case, the value of `i`) and it will cease execution until it is asked for the next value. 

```python
def my_range(beg, end):
    "Generate numbers from start to stop"
    i = beg
    while i < end:
        yield i
        i += 1
```

```python
# Let's call the function to return a generator that we can iterate through. 
range_of_nums = my_range(0, 10)

# Now, let's call the __next__() method to get each value is the it is 
# "yielded" by the generator

# This executes the code in the generator until it hits the yield statement.  It then stops until __next__() is called again.
print(range_of_nums.__next__())
print(range_of_nums.__next__())
print(range_of_nums.__next__())
```
**output:**

```
0
1
2
```

We do not usually use the `__next__()` method directly. We are usually looping over the iterator, or passing the iterator to another iterative process (in these case,`__next__()` is still used "under the hood", but we are not using it directly as programmers). Below, we simple use `range_of_nums` in a loop, we also use the `my_range()` function directly in a for loop, just like you would use `range()`.

```python
for num in my_range(30, 33):
    print(num)
```

## **A Fibonacci Series Generator.**

A Fibonacci Series is a series of numbers in which the next number is the sum of the two preceding numbers.  If we start with 0 and 1, then the series is 0, 1, 1, 2, 3, 5, 8, 13, etc.  This is a fun series that is often used in computer science lessons. Let's code a function that will return a generator that iterates through the Fibonacci Series (starting with 0 and 1).

```python
def fibonacci_series(N):
    """Generate the Fibonacci series starting at 0 and 1"""
    # We start by seeding 0 and 1 as the first two numbers
    i_prev = 0
    i = 1
    yield i_prev  # we yield 0 first
    # now in the following loop, we yield "i" and then calculate i_next by
    # summing the two previous
    for _ in range(N-1):
        yield i 
        i, i_prev = i + i_prev, i
```

```python
f_s = fibonacci_series(10)
for x in f_s:
    print(x)
```

**Iterators Can Only Be Iterated Over Once**

Once we create an iterator, it can only be iterated over once.  For example, in the above cell we looped over the entirety of `f_s`.  Below, we try to loop over it again, but nothing prints. This is because we have already looped over the iterator to its end.  If we need to iterate again, we will have to create a new iterator.

## File Word Counts

Another example, which will become more meaningful if you take the course Python Data Structures, Data Mining and Big Data, is producing a word counts from a file, line by line.

Let's write a function that will generate word counts, from a file, line by line.

```python
def file_word_count(filepath):
    """Generate word counts from ta file, line by line"""
    # First, open the file
    with open(filepath, 'r') as my_file:
        # Loop through the lines
        for line in my_file:
            line = line.strip()  # strip whitespace from the line
            words = line.split()  # split the line into words
            # create a dictionary that we will store the word counts in
            word_count_dict = {}
            # loop through the words in the line and tally them in the
            # dictionary
            for word in words:
                if word in word_count_dict:
                    word_count_dict[word] += 1
                else:
                    word_count_dict[word] = 1
            # now loop through the dictionary and yield up the word counts 
            for word in word_count_dict:
                yield word, word_count_dict[word]
```

```python
aesopa10_path = os.path.join(os.getcwd(), 'aesopa10.txt')
counter = 0
for word, count in file_word_count(aesopa10_path):
    print(word, count)
    counter += 1
    if counter > 2000:
        break
```

# **Enumerate and Zip**

## Enumerate

Enumerate takes in an iterable object (like a list, tuple, or some other iterator) and outputs tuples that are enumerated. The first element in the tuple is the number and the second is the value from the original iterable object.

```python
my_list = ['a', 'b', 'c']

for item in enumerate(my_list):
    print(item)
```

```
(0, 'a')
(1, 'b')
(2, 'c')
```

## Zip

Zip will take multiple iterable objects as inputs and output tuples that contain items from each iterable, in order. That is the first tuple will contain the first item from each iterable, the second tuple will contain the second items, etc...

```python
tuple_1 = (2012, 2012, 2012)
tuple_2 = ('01', '02', '03')

new_list = []
for val1, val2 in zip(tuple_1, tuple_2):
    print(val1, val2)
    new_list.append(str(val1) + '_' + val2)
print(new_list)
```

```
2012 01
2012 02
2012 03
['2012_01', '2012_02', '2012_03']
```

```py
for x in zip(tuple_1, tuple_2):
    print(x)
```

```
(2012, '01')
(2012, '02')
(2012, '03')
```

