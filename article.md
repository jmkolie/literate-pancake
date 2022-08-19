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
