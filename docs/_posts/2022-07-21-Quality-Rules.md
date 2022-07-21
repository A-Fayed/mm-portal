---
layout: post
title: "Quality Rules"
date: 2022-07-21 11:23:21 +0100
categories: [Ideas]
image: post-image.png
description: It is very import for a Python developer to know which data structure to use and when. In this section we are going to give a quick introduction to the most popular data structures in Python and hashable vs unhashable objects as well as the numpy and pandas libraries.
---

## Data Structure Guidelines

It is very import for a Python developer to know which data structure to use and when. In this section we are going to give a quick introduction to the most popular data structures in Python and hashable vs unhashable objects as well as the numpy and pandas libraries.

Do note that because Python is not a strong typed language, data structures can contain multiple different types of objects in them.

### Mutable vs Immutable and Hashable vs Unhashable

In Python, data structures and objects can either be mutable or immutable and they can be hashable or unhashable.

This is very important since mutable and immutable refer to the ability to modify a given object or not. This property then impacts if an object is hashable or not.

Hashing is the generation of an integer identifier for an object which will never change during the objects lifetime. Typically, immutable objects are hashable while mutable objects are not.

### List

A list in Python is a mutable unhashable ordered collection of objects.

Usage Example:

```python
list_sample_1 = [] # empty list

list_sample_1.append(1) # adds 1 to the end of the list

list_sample_1.append('a') # adds 'a' to the end of the list

print(list_sample_1) # [1, 'a']

list_sample_1[0] = 2

print(list_sample_1) # [2, 'a']
```

Lists are good when you want to store a collection of items that can have duplicates and that you would want to order.

```python
list_sample_1 = [4,5,3,2,5,1,3]

print(sorted(list_sample_1)) # [1, 2, 3, 3, 4, 5, 5]
```

### Tuple

A tuple in Python is an immutable hashable ordered collection of objects. Although, mutable objects within a tuple can be modified.

Usage Example:

Usage Example:

```python
tuple_sample_1 = () # empty tuple, can't be changed

tuple_sample_2 = (1,2,3) # integer tuple

tuple_sample_3 = ([1,2,3],'[4,5,6]', 2) # mixed types tuple

tuple_sample_4 = (3,4,5,2,3)

print(sorted(tuple_sample_4)) # (2, 3, 3, 4, 5)

tuple_sample_3[0] = 1 # TypeError: 'tuple' object does not support item assignment
```

You would use a tuple only if working with a collection you don't want to alter whether in terms of size or content, it doesn't have an `append` function like `List` does, and does not support changing values inside of it.

### Set

A set in Python is a mutable unhashable non-ordered collection of unique objects that don't have an index.

Usage Example:

```python
set_sample_1 = set() # empty set - pay attention because if you write this: set_sample_1 = {} it considers it as a dictionary

set_sample_1.add(1) # {1}

set_sample_1.add(1) # {1}

set_sample_1.add('a') # {1, 'a'}

set_sample_1.pop() # this will remove the last element in the set

set_sample_1[0] = 2 # TypeError: 'set' object is not subscriptable - you cannot access an element in a set as you would access an element in a list

set_sample_1.remove(1) # {'a'} - removes the element provided as a parameter
```

A handy way of using a set is to get all unique members of a list.

```python
list_sample_1 = [1,2,3,4,4,5,6,3,2,1]

unique_set = set(list_sample_1) # {1, 2, 3, 4, 5, 6} - you can then turn this back to a list if you so wish to: list(unique_set)
```

As you can see in the prior examples, you would use a set when you want to have a collection of unique objects. It is pseudo-mutable because you can remove / add objects to it but you cannot change the values of the objects that are in it.

### Dictionary

A dictionary in Python is a mutable unhashable ordered (if Python version is 3.7 or higher) collection of hashable unique keys and their unique values.

Usage Example:

```python
dict_sample_1 = {} # empty dictionary

dict_sample_1[1] = 1 # {1: 1}

dict_sample_1[(1,2,'c')] = ['a',2,3] # {1: 1, (1, 2, 'c'): ['a', 2, 3]}

dict_sample_1[1] = 2 # {1:2, (1, 2, 'c'): ['a', 2, 3]}

dict_sample_1[[1,2,'c']] = 2 # TypeError: unhashable type: 'list'
```

Dictionaries are very useful in representing complex data, you can also use nested dictionaries if more complexity is needed i.e.:

```python
dict_sample_1 = {1: {1: {'username':'test', 'pwd': 'secret', 'active': True}}}
```

It is very similar to [JSON syntax][json] and can contain customized objects, tuples etc. which is not supported by JSON.

## Asynchronous Programming

Code tends to be written to run synchronously:

Get a document => Extract information from it => Transform it to a model input.

In some cases, when an action does not need the previous actions' to finish to execute, we can introduce [asynchronous][async] code.

As an example, think of a user interface where a user can upload documents to be processed and returned back to the user.

In syncronous programming, this user interface would follow a simple workflow:
Wait for user input => Process document => Return document.

But this would be ineffective since the user interface does not need to wait for the document to finish processing to continue to execute.

In asyncronous programming, the user interface process can run the document processing method as an async method allowing the user interface to continue to execute.

Wait for user input => async process document...
Waiting for further input | async document processing...
Waiting for further input => 2nd async process document | async document processing...
waiting for further input | async document processed! | async document 2 processing...
etc...

Asynchronicity in Python is a bit different than in other programming languages. It can be achieved through different ways, all of which presented in [this article][async-py] and some of them described below.

![Python Programming Models](./assets/images/async-py.png "Python Programming Models")

<!-- References -->

[python-2]: https://www.python.org/downloads/release/python-2718/
[python-3]: https://www.python.org/downloads/release/python-3100/
[nep-29]: https://numpy.org/neps/nep-0029-deprecation_policy.html
[json]: https://www.w3schools.com/whatis/whatis_json.asp
[comprehension]: https://www.geeksforgeeks.org/comprehensions-in-python/#:~:text=%20Python%20supports%20the%20following%204%20types%20of,3%20Set%20Comprehensions%204%20Generator%20Comprehensions%20More%20
[comprehension-readability]: https://towardsdatascience.com/how-to-convert-loops-to-list-comprehension-in-python-15efcc696759#:~:text=List%20comprehensions%20are%20relatively%20faster%20than%20for%20loops.,figure%20out%20how%20to%20structure%20a%20list%20comprehension.
[comprehension-speed]: https://switowski.com/blog/for-loop-vs-list-comprehension
[generator]: https://www.tutorialspoint.com/generators-in-python#:~:text=Generator%20in%20python%20are%20special%20routine%20that%20can,called%20and%20it%20generates%20a%20sequence%20of%20numbers.
[map]: https://www.w3schools.com/python/ref_func_map.asp
[numpy]: https://github.com/numpy/numpy
[numpy-w3schools]: https://www.w3schools.com/python/numpy/numpy_intro.asp
[locality-of-reference]: https://stackoverflow.com/questions/7638932/what-is-locality-of-reference
[c-vs-py]: https://www.huffpost.com/entry/computer-programming-languages-why-c-runs-so-much_b_59af8178e4b0c50640cd632e#:~:text=Computer%20Programming%20Languages%3A%20Why%20C%20Runs%20So%20Much,called%20JIT%2C%20or%20Just%20In%20Time%20compilation.%20
[pandas]: https://github.com/pandas-dev/pandas
[pd-series]: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html
[pd-df]: https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html
[pd-vs-np]: https://www.educba.com/pandas-vs-numpy/
[oop]: https://www.educative.io/blog/object-oriented-programming
[oop-python]: https://pythonguides.com/object-oriented-programming-python/#:~:text=Python%20is%20an%20object-oriented%20programming%20language%20and%20it,also%20it%20focuses%20on%20writing%20the%20reusable%20code.
[overriding-overloading]: https://www.educba.com/overloading-vs-overriding/
[oop-remark]: https://www.youtube.com/watch?v=o9pEzgHorH0
[kiss]: https://www.interaction-design.org/literature/topics/keep-it-simple-stupid
[requests-lib]: https://realpython.com/python-requests/#:~:text=%20Python%E2%80%99s%20Requests%20Library%20%28Guide%29%20%201%20Getting,values%20through%20query%20string%20parameters%20in...%20More%20
[lambda]: https://thedeveloperblog.com/python/python-lambda-functions#:~:text=%20Why%20use%20lambda%20function%3F%20%201%20Example,list.%20It%20gives%20a%20new%20list...%20More%20
[async]: https://www.outsystems.com/blog/posts/asynchronous-vs-synchronous-programming/
[async-py]: https://medium.com/velotio-perspectives/an-introduction-to-asynchronous-programming-in-python-af0189a88bbb
[thread]: https://en.wikipedia.org/wiki/Thread_(computing)
[process]: https://en.wikipedia.org/wiki/Process_(computing)
[gil]: https://en.wikipedia.org/wiki/Global_interpreter_lock
[subprocess]: https://geekflare.com/learn-python-subprocess/
[multiprocessing]: https://docs.python.org/2/library/multiprocessing.html#module-multiprocessing
[asyncio]: https://docs.python.org/3/library/asyncio.html
[event-loop]: https://docs.python.org/dev/library/asyncio-eventloop.html
[coroutine]: https://docs.python.org/3.5/library/asyncio-task.html#coroutines
[future]: https://docs.python.org/3.5/library/asyncio-task.html#future
[aiohttp]: https://docs.aiohttp.org/en/stable/
[async-usage-diff]: https://leimao.github.io/blog/Python-Concurrency-High-Level/
[cpu-bound]: https://en.wikipedia.org/wiki/CPU-bound
[io-bound]: https://en.wikipedia.org/wiki/I/O_bound
[cookiecutter]: https://drivendata.github.io/cookiecutter-data-science/
[py-struct-hitch]: https://docs.python-guide.org/writing/structure/
[py-struct-tutorial-repo]: https://github.com/yngvem/python-project-structure/
[pypi]: https://pypi.org/
[jupyter]: https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter
[pylance]: https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance
[autopep8]: https://marketplace.visualstudio.com/items?itemName=himanoa.Python-autopep8
[vs-code-lint]: https://code.visualstudio.com/docs/python/linting
[flake8]: https://flake8.pycqa.org/en/latest/
[pylint]: https://pylint.org/
[pyflakes]: https://pypi.org/project/pyflakes/
[pycodestyle]: https://pypi.org/project/pycodestyle/
[pip]: https://pypi.org/project/pip/
[pkg-index]: https://pypi.org/search/?c=Programming+Language+%3A%3A+Python+%3A%3A+3
[pkg-collection]: https://www.lfd.uci.edu/~gohlke/pythonlibs/
[py-wheel]: https://pythonwheels.com/
[venv]: https://docs.python.org/3/library/venv.html
[virtualenv]: https://virtualenv.pypa.io/en/latest/
[virtualenvwrapper]: https://pypi.org/project/virtualenvwrapper/
[vscode-debug]: https://code.visualstudio.com/docs/editor/debugging
[create-pip-pkg]: https://github.com/MichaelKim0407/tutorial-pip-package
[ae-wiki]: https://mmdigitalventures.visualstudio.com/Moata/_wiki/wikis/Module%20-%20Analytical%20Engine?wikiVersion=GBmain&pagePath=/Define%20(Describe%20and%20define)
[semaphores]: https://docs.python.org/3/library/asyncio-sync.html#asyncio.Semaphore
[semaphores-tutorial]: https://tutorialedge.net/python/concurrency/python-asyncio-semaphores-tutorial/
