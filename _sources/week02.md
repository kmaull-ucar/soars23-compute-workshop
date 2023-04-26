Week 2
======

````{dropdown} OBJECTIVES
:container: + shadow
:title: bg-secondary text-white text-center font-weight-bold
:body: bg-light font-italic
:animate: fade-in
:open:

* Python Quick Tour: constructs, loops, dictionaries and other data structures, core Python libraries
* Anaconda and Python
* Object-oriented programming in Python
* developing strategies for larger, more complex notebooks

````

## A Quick Tour of Python 
Python is a large and complex language.  While you may have had access to the language through geoscience and/or data science contexts, it is a _general purpose_ programming language that one can develop nearly any kind of program: from user interface applications to servers and low-level APIs (to the extent that a hardware-aware language like C/C++ may be invoked).

Python will take some time to learn fully, but there are some key language features that you must become familiar with to increase your competence.

The notebooks below will give you a quick tour of the key features of the language:

| Notebook | Concepts | Link |
|:--:|:---|:--:|
|1 | Basic Python introduction | [nb/w02_python_tour_01_basics.ipynb](nb/w02_python_tour_01_basics.ipynb)

## Anaconda and Python

[Anaconda](https://anaconda.com) is a platform for Python that pre-packages a large number of useful Python libraries, tools and environment configurations that are useful for data science-related work.  The platform enables a large number of tools that help manage and install a wide array of Python packages (in and out of the data science scope).  It is an open source platform -- and thus the community versions are free to install and use, but Anaconda also has commercial enterprise tools that enable large data analyses at a cost.

You will want to install Anaconda on your machine using the recommended installation procedures.  Make sure that you keep your installation up-to-date by installing the recommended updates, since this will make sure you are running the latest packages and that they are optimally compatible with one another.

Tutorials to consider to accelerate learning how to use Anaconda are listed below:

* [Getting started with Anaconda Distribution
](https://docs.anaconda.com/free/anaconda/getting-started/index.html) (anaconda.com)
* [How To Install the Anaconda Python Distribution on Ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-22-04) (digitalocean.com)
* [How I Setup for Python Development in Windows with WSL2 and Why You Should Consider Too](https://medium.com/geekculture/how-i-setup-for-python-development-in-windows-with-wsl2-and-why-you-should-consider-too-24187c9ed3a0) (medium.com)

You may also hear the term "conda" when referring to "Anaconda", but "conda" is the package manager and command line tool for managing the Python libraries and packages in Anaconda, the distribution.

## Object-oriented programming in Python

While an intermediate topic, it goes without saying that as your code gets more complex, you will be inclined to used deeper features of the programming language.

One such feature is what are called "objects".  This is not meant to be a complete introduction to objects or object-oriented programming in Python, but rather a gentle introduction to the _conceptual_ framing of objects and how you might use them in your own programs.

One easy way to think about objects is to rest your mind a little and look at your programs as more abstract components and the interplay of those components.  For example, when you think of the ideas around a "list", you can abstractly think about what it represents, what properties it has, and perhaps how the abstraction of a list differs from that, say of a set.  A set has the unique property that items in the set are not repeated, while in a list, not only can items be repeated, the ordering of those items is usually important -- and set  ordering is not usually important.  

So _abstractly_ a list can be thought of as 

* an ordered grouping of things, that 
* things can be added to or removed from.

So what might you want to _know_ about a list?  You might like to know:

* how many things are in the list?
* what kinds of  things (e.g. numbers, strings, other lists) are in the list?

Also what might you want to _do_ to a list?  You might want to:

* add and removed items from the list
* remove all items from the list
* take two lists and merge them
* and so on

You can see the things you might want to _do_ with the list and in some cases may exceed our interest in complicating the concept of list, thus we might want to think about the _essential_ things we want to do with a list, then let the end user of a list do other things.  This is where our thoughtfulness in building abstractions come in:  if we make things too abstract, they may not be useful and end users may have difficulty understanding the _reason_ for such abstractions; if we don't make things abstract enough, we end up not reaping the benefits of abstraction.  There is a careful balance that must be struck when developing abstractions, and there is often more art than science when building them.

Abstractions in Python can be captured a number of ways, but one critical tool is the "object".  An object in Python is a tool that at some point you may consider integrating into your code.

Initially, there are three things you will need to know about an object:

1. objects have properties, that capture the _state_ of the object;
2. objects have functions (also known as interfaces, APIs, etc.) which encode the _behavior_ of an object which are essential to perform actions on that object (and/or it interaction with other objects);
3. objects have a lifespan -- that is they are _created_ and ultimately _destroyed_.

The concepts **state** and **behavior** are essential to object-oriented programming.

Objects are realized in what are called "classes", and classes are realized in what are called "instances".  We will "instantiate" a "class", where the "class" is the programmatic manifestation of the "object".  It sounds complex, but once you see it in action, it will be clearer.

So let's get beyond the word games and play.

### Demo: a Temperature object

Let's say we want to abstract away the concept of "temperature".

What exactly is "temperature"?  

* it a measure of hotness or coldness
* it is expressed with some known units on some known scale (can be arbitrary, but usually is informative, if it is)

From this we can deduce "temperature", is, if not linear, increase or decreasing at some expected interval.  Let's say for now our "temperature object" is always linear so that when we use it, we can know what to expect: when the "temperature" goes up, it gets warmer, when it goes down, it gets cooler.

Let's see how we might model this as an "object" in Python.  

First, the syntax for a class in Python is relatively simple:

```python
class SomeClass:
    pass # the implementation of that class.
```

Each class will need to have an `__init(self, ...)__` method.  This is call the "constructor" or "initializer".  It is necessary to create and instance of the class.  Our implementation looks like:

```python
class SomeClass:
    def __init__(self): # the implementation of constructor
        pass
```

We would want to store the temperature, and there are many ways to do this, but we will continue our introduction to objects in the notebook here:

* [concrete implementation of `temperature` class](./nb/w02_temp_demo.ipynb)

Object-oriented programming is powerful and you may not initially find it useful or intuitive.  But as you write more code, it will become a standard tool with how you approach your code.  Give it a try, and at the very least, remember it is just another tool to help you be effective.

## Developing strategies for Python-based Jupyter notebooks

You may already know that Jupyter notebooks can be developed in a number of languages, Python being perhaps the most dominant and popular among them.  You will also soon be overwhelmed with either a large number of notebooks, or notebooks of high complexity, or both. 

We will try to distill some strategies and best practices for your notebooks.  Here are some top considerations:

* **Be narrative.**

    Jupyter notebooks offer you the unique
    opportunity to mix in the _conversation_
    with yourself and your audience on the
    important things you're doing.  Don't miss 
    out on this opportunity to tell the story
    and be narrative.  Minimally, your 
    _future self will thank you_, but probably
    so will your advisor, labbies, co-workers
    and maybe even a distant cousin in Kenya,
    India or Greece. 

* **Keep notebooks cohesive and focused; break them up when they get too complex.**

    * large notebooks may be more useful if they are broken up, so consider doing that and linking them.  [See this linked notebook  example](./nb/w02_linked_example_nb1.ipynb) to get
    and idea about how this is done.  

    * another advantage of doing this is if you
    use [git](https://git-scm.org) to version control your notebooks,
    you can keep better track of what is going
    on as you move through your code (and it supports collaboration)

* **Give attribution to borrowed code, data and ideas.**

    * if you find useful code, _no matter the source_ -- whether Github, stackoverflow, Reddit, a random websitem etc. -- give thanks. It doesn't need to be complex -- a simple comment in your code like:
    ```python
        # thank YOU miquel for the amazing f-string hints @ https://miguendes.me/73-examples-to-help-you-master-pythons-f-strings
        print(f"Hello {myvar:05})
    ```
    * we are all here to help each other, and giving
    a nod to those who put together something
    that got you over the hump isn't too much to ask. Futhermore, one day something _you_ did might be useful to someone else and they might return the attribution favor!

* **Structure your files and folders appropriately.**

    * for starters, if you have data, create a `data/` folder so you can always know where all your data is
    * if you have a complex notebook set, consider creating folders for the _themes_ or 
    notebook _functions_, so for example:
    ```
        preprocessing/  <-- preprocessing notebooks
        analysis/       <-- analysis notebooks
        data/           <-- project in/outputs
        summary.ipynb   <-- summary of project
    ``` 