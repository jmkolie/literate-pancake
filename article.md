---
title: |Iterators and Generators in Python
  "Introduction to Python modules."
In python programming or any other programming language, looping over the sequence (or traversing) is the most common aspect. While loops and for loops are two loops in python that can handle most of the repeated tasks executed by programs. Iterating over sequences is so widespread that Python offers extra capabilities to make it easier and more efficient. One of the tools for traversing is Iterators and Generators in Python. This chapter kicks off our investigation of these tools. Now, let’s get started with Iterators and Generators in python. 
Iterators in Python
What is Python Iterator?
An iterator is a collection object that holds multiple values and provides a mechanism to traverse through them. Examples of inbuilt iterators in Python are lists, dictionaries, tuples, etc.
It works according to the iterator protocol. The protocol requires to implement two methods. They are __iter__ and __next__.
 
Python iter()
The iter() function in Python returns an iterator for the supplied object. The iter() generates a thing that can be iterated one element at a time. These items are handy when combined with loops such as for loops and while loops. 
Syntax:
iter( object , sentinel )
iter() function takes two parameters:
•	Object: An object whose iterator needs to be created (lists, sets, tuples, etc.).
•	Sentinel (optional): Special value that represents the end of the sequence.
Python next()
The next() function returns the next item from the iterator. The next() function holds the value one at a time. 
Syntax:
next( iterator , default )
The next() method accepts two parameters:
•	Iterator : next( ) function retrieves the next item from the iterator.
default(optional): this value is returned if the iterator is exhausted (not tired, but no next item to retrieve).
 The __iter__() function returns an iterable object, whereas the __next__() gives a reference of the following items in the collection

How does Iterator work in Python?
 
Most of the time, you have to use an import statement for calling functions of a module in Python. However, iterators don’t need one as you can use them implicitly.
When you create an object, you can make it iterable by calling the __iter__() method over it. After that, you can iterate its values with the help of __next__(). When there is nothing left to traverse, then you get the StopIteration exception. It indicates that you’ve reached the end of the iterable object.
The for loop automatically creates an iterator while traversing through an object’s element.
The following flowchart attempts to simplify the concept for you.
Iterator Syntax
To use iterators, you can use the methods as defined above __iter__ and __next__ methods.
You can create an iterable object as per the below instruction:
iterable_object = iter(my_object_to_iterate_through)
Once, you get a hold of the iterator, then use the following statement to cycle through it.
iterable_object = iter(my_object_to_iterate_through)
next(iterable_object)
Iterator Examples 1
Cubes = (1, 8, 27, 64, 125, 216)
cube = iter(Cubes)
print(next(cube))
print(next(cube))
Example 2

X = [25, 78, 'Coding', 'is', '<3']
# Get an iterator using iter() 
a = iter(X)

# Printing the a iterator
print(a)

# next() for fetching the 1st element in the list that is 25
print(next(a))

# Fetch the 2nd element in the list that is 78
print(next(a))

# Fetching the consecutive elements
print(next(a))
print(next(a))
print(next(a))

As you can see, when we are trying to print the iterator a, it shows its type and the memory address it is located on. One by one, next() fetches the element from the list.
Generators in Python

What is Python Generators?
A generator in Python is a function with unique abilities. We can either suspend or resume it at run-time. It returns an iterator object which we can step through and access a single value in each iteration.
Alternatively, we can say that the generator provides a way of creating iterators. It solves the following common problem.
In Python, it is cumbersome to build an iterator. First, we require to write a class and implement the __iter__() and __next__() methods. Secondly, we need to manage the internal states and throw StopIteration exception when there is no element to return.

Python has a generator that allows you to create your iterator function. A generator is somewhat of a function that returns an iterator object with a succession of values rather than a single item. A yield statement, rather than a return statement, is used in a generator function. 
The difference is that, although a return statement terminates a function completely, a yield statement pauses the function while storing all of its states and then continues from there on subsequent calls.

How to Create a Generator in Python?

Python generator gives an alternative and simple approach to return iterators. The procedure to create the generator is as simple as writing a regular function.
There are two straightforward ways to create generators in Python.
Generator Function
We write a generator in the same style as we write a user-defined function.
The difference is that we use the yield statement instead of the return. It notifies Python interpreter that the function is a generator and returns an iterator.
# Generator Function Syntax
# 
def gen_func(args):
    ...
    while [cond]:
        ...
        yield [value]
The return statement is the last call in a function, whereas the yield temporarily suspends the function, preserves the states, and resumes execution later.
Below is a simple example of a Python generator function to determine the next value of a Fibonacci sequence.
Demonstrate Python Generator Function

def fibonacci(xterms):
    # first two terms
    x1 = 0
    x2 = 1
    count = 0

    if xterms <= 0:
       print("Please provide a +ve integer")
    elif xterms == 1:
       print("Fibonacci seq upto",xterms,":")
       print(x1)
    else:
       while count < xterms:
           xth = x1 + x2
           x1 = x2
           x2 = xth
           count += 1
           yield xth

ib = fibonacci(5)

print(next(fib))
print(next(fib))
print(next(fib))
print(next(fib))
print(next(fib))
print(next(fib))
In the above example, the generator function has a while loop to calculate the next value of a Fibonacci series. We’ve placed a yield statement inside the ‘while.’
After creating the generator function, we’ve called it and passed five as the input argument. It will only return the iterator object.
The generator function will not execute execution until we call the next() method over the returned object, i.e., ‘fib.’ We are doing six such steps to iterate over the ‘fib’ object.
The first five next() calls have succeeded and returned the corresponding element of the Fibonacci series. However, the last one raised the StopIteration exception as the iterator had no items left.

Generator Expression
Python allows writing generator expressions to create anonymous generator functions.
This procedure is similar to a lambda function creating an anonymous function.
The syntax of a generator expression is the same as of list comprehension in Python. However, the former uses the round parentheses instead of square brackets.
Another difference between a list comprehension and a generator expression is that the LC gives back the full list, whereas the generator expression returns one value at a time.
# Demonstrate Python Generator Expression

# Define the list
alist = [4, 16, 64, 256]

# Find square root using the list comprehension
out = [a**(1/2) for a in alist]
print(out)

# Use generator expression to calculate the square root
out = (a**(1/2) for a in alist)
print(out)
print(next(out))
print(next(out))
print(next(out))
print(next(out))
print(next(out))
While executing the above example, firstly, the list comprehension returns the list containing the square roots of all elements. So we get the conclusive result here.
Next, the generator expression produces an iterator object which gives one result at a time. The size of the list is four. So we have four successive next() method calls which print the square root of respective list elements.
Since we called the next() method one more time, it caused the StopIteration exception. Please check from the below output.
[2.00, 4.0, 8.00, 16.0]
 at 0x000000000359E308>
2.0
4.0
8.0
16.0
Traceback (most recent call last):
  File "C:/Python/Python35/python_generator.py", line 17, in 
    print(next(out))
StopIteration

Explanation: yield in Python can be used as the return statement in a function precisely the way we have used in the above program. The function returns a generator that can be iterated upon instead of returning the output when done so.
Python iterates over the code until it reaches a yield line within the function. The function then transmits the produced value and pauses in that state without leaving. When the function is called again, its last paused state is remembered, and execution is begun from there. This will continue until the generator is exhausted.
 
Why use generators when the return statement is already present?
The most well-known feature of generators is their excellent memory efficiency. A standard function that returns a sequence will first construct the whole sequence in memory before returning the result. If the number of elements in the sequence is enormous, this is overkill. The generator implementation of such sequences, on the other hand, is memory-friendly and preferable since it only generates one item at a time.

When to use a Generator?
There are many use cases where generators can be useful. We have mentioned some of them here:
	Generators can help to process large amounts of data. They can let us do the calculation when we want, also known as the lazy evaluation. The stream processing uses this approach.
	We can also stack the generators one by one and use them as pipes as we do with the Unix pipes.
	The generators can also let us establish concurrency.
	We can utilize Generators for reading a vast amount of large files. It will help in keeping the code cleaner and leaner by splitting the entire process into smaller entities.
	Generators are super useful for web scraping and help increasing crawl efficiency. They can allow us to fetch the single page, do some operation, and move on to the next. This approach is far more efficient and straightforward than retrieving all pages at once and then use another loop to process them.

Comparison of Iterators and Generators in python
Iterators:
Iterators are the objects that use the next() method to get the next value of the sequence.
Classes are used to Implement the iterators.
Every iterator is not a generator.
Complex implementation of iterator protocols .i.e., iter() and next().
Iterators in python are less memory efficient.
No local variables are used in Iterators.

Generators:
A generator is a function that produces or yields a sequence of values using a yield statement.
Functions are used to implement the generator.
Every generator is an iterator.
Generators in Python are simpler to code than do the custom iterator using the yield statement.
Generators in Python are more memory efficient.
All the local variables are stored before the yield statement.

Conclusion:
To summarise the session, we explored Iterators and Generators in python.
A generator uses the ‘yield’ keyword in Python. A Python iterator, on the other hand, does not. Every time 'yield' pauses the loop in Python, the Python generator stores the states of the local variables. An iterator does not need local variables. All it requires is an iterable object to iterate on.

date: May, 2022
lang: en-EN
urlcolor: blue
geometry: "left=2.5cm,right=2.5cm,top=3cm,bottom=3cm"
documentclass: article
fontfamily: Alegreya
header-includes: |
    \usepackage{fancyhdr}
    \pagestyle{fancy}
    \fancyhf{}
    \rhead{Dakar Institute of Technology}
    \lhead{Patrick Nsukami}
    \rfoot{Page \thepage}
    \hypersetup{pdftex,
            pdfauthor={Patrick Nsukami},
            pdftitle={Introduction to Python programming},
            pdfsubject={Introduction to Python programming},
            pdfkeywords={Python, Programming},
            pdfproducer={Emacs, Pandoc, Latex, Markdown},
            pdfcreator={Emacs, Pandoc, Latex, Markdown}}
    
---

# Foo:

foo bar baz

```python
# module foo.py

a = 42

def bar(x):
    print(x)

def foo():
    return 42
```
