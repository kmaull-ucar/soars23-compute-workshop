Algorithms and Computational Thinking
------  

```{card}  
:class-card: objectives 
:class-header: text-center font-weight-bold
:class-body: bg-light font-italic 

**OBJECTIVES**
^^^

* what is computational thinking
* problem solving and thinking through algorithms
* how to reduce complexity for understanding
* Algorithms: A quick tour

```

We are now in the epoch of human development where the transition from physical machines augmenting (and in some cases replacing) the work of _human bodies_ is giving way to  _digital machines_ augmenting the work of _the human mind_.  As was the case during the rise of mechanized machines automating human labor as the industrial revolution charged forward, with our digital machines and technologized transformations of work, a fertile ground is being cultivated for computers to be planted into nearly every creative endeavor of human activity, and sometimes providing the only tools with which human creativity can flourish at scale.

Indeed, in nearly every scientific discipline today  _computation_ has crept in.  Most numerically-grounded and big data intensive sciences cannot produce any relevant outcomes without computer software, and now nearly _any discipline_ that generates large amounts of data will fail to escape computation as a necessary path to progress.  Indeed, computation is now considered the [third "pillar" of science](https://physicsworld.com/a/the-third-pillar-of-science/) (the first two being theory and experiment) and we have relied on computers for a great many things in these disciplinary contexts in science -- but reasoning about how computing can bear on solutions to  domain-level disciplinary problems is why _computational thinking_ is so necessary today. Here, it is the _thinking_ part that is at parity with the _computation_ part.  


```{image} ./img/abstract-geometric-wavy-folds-background.jpg
:alt: abstract image
:class: bg-primary mb-1
:width: 640px
:align: center
```

## What is "computational thinking"?

Generically, computational thinking involves the _processes_ necessary to construct solutions to complex problems to be carried out by machines and humans {cite:ps}`wing_computational_2006`, and at its core requires analyzing patterns and developing appropriate abstractions (models) to problems.  It also requires an awareness of computational strategies, experience with data analysis and skill projecting computational techniques onto domain-specific problems.  Today, few domains can progress without the new generation of experts having intimate knowledge and skill in "computational thinking".

## Key Ingredients

The key ingredients to computational thinking are: data, abstraction/modeling and computation.  We will explore each of these separately, but nearly all of your work begins with some specific dats (simple or complex), which within the context of your domain, requires some modeling or abstraction of the problem space.  From that abstraction, computational solutions can be crafted and ultimately may yield more data, analyses or additional insights to improve modeling or abstraction.

### Data

We will begin our travels into the realm of computational thinking by first situating ourselves in the world of data.  Without data, there is no computation. Computational thinking is the tool we will use to get what we need from our data and with it, answering relevant questions of interest (or ask new ones).  Some of the approaches we will learn will require knowledge of a programming language, and perhaps knowledge of data formats and ways to transform that data.  Other approaches will require higher level abstractions to unlock a solution or to make a small step towards one.  The interplay of both the _low-level specialized tools_ (a programming language), and the _high level abstractions_ (e.g. algorithmic pseudocode) will bring us to a more productive relationship with our computational work.

```{admonition} What is "psuedocode"?
:class: tip
Psuedocode refers to the high level "sketch" of your code, written in a way that 
is more of a shorthand description of what your code is supposed to do.  While there's
not a "formal" shorthand, per set, and in the beginning it is best your psuedocode
is at least understandable by you, as you progress and mature, your psuedocode might look
very close to the final code, especially if you stay in Python.

Here is example psuedocode for a random password generator:

    variable P is a string of length 2 or more that hold the password

    set P = an empty string
    set size = an integer between 2 and 30 for an arbitrary password
    set alpha = the set of upper and lowercase letters

    for i = 0 to size
        set N[i] = a random character from alpha 

```


In Python, we will be well served to think about all "things" in the Python world as **data objects** -- that is objects that contain some data, whether structured or not.  In the next few paragraphs we will explain what structured and unstructured data are and various techniques to deal with each in Python.

Data typically come in two forms: _unstructured_ and _structured_.  We'll break each of them down to develop a more rigorous approach to computational thinking.

**UNSTRUCTURED DATA**

_Unstructured data_ is all around us, indeed, this type of data is what reminds us not only how far we have to go to move human knowledge into machines, but perhaps how interesting, strange and beautiful human creativity actually is.  Unstructured data are all those forms of data that either have not yet been, or resist altogether, being converted to a machine-ready, machine-interpretable form.  Think about such data as that which looks the same in a book as it does in a text file.  Shakespeare's _Hamlet_, for example -- at least at the textual level that it contains, is considered "unstructured data".  We would say, however, that there is a structured form of the plan which would include it's various parts, plots, characters, etc. once we have read and _interpreted_ it, and rightfully added _metadata_ about it.  Much of the human world belongs to unstructured data, until information scientists put structure to it often through _metadata_.  In fact, much of the "structured" data of "unstructured" data, is captured as metadata -- or data _about_ the thing, as opposed to the thing itself.  It will take some getting used to, but if in its raw form, data does not seem amenable to direct computational inspection or manipulation, the it is a good candidate "unstructured" data.

To cement this idea, consider the bits of a digital image as unstructured until it is displayed on a computer and viewed and interpreted by a human as a cat.  There is no structure to the image that a machine can _understand_ outside of its metadata which would include things like the time the image was captured, the resolution of the image, color depth, etc.  Of course, if  we try to analyze those bits, perhaps with some algorithm to detect patterns in that unstructured sequence of bits, we might arrive at a different conclusion about whether the image was of a cat, dog or car.

**STRUCTURED DATA**

```{figure} ./img/2808109_18384.jpg
---
width: 250
align: right
---
```
The opposite of unstructured data is structured data, and it is typical to work with structured data in the numerically-driven sciences.  One of the primary clues you are dealing with structure data is that it is not merely an easily human-readable text file (though in the case of CSV, it will often be ).  It might be a CSV, JSON, XML, NetCDF or any number of various formats that will encode the structured data a particular way so that you can manipulate it more easily.  Some of these formats may require special tools to inspect their data, others will have built in readers in Python (e.g. CSV) and others yet, may require database tools to read them.  Whatever the case, study the data format you have before working with it -- you will find it important to understand this well in advance of any analysis you might need to do.

Here is a list of common structure data formats:

 | Format | Description |  | Python Library |
 |-------:|:------------|:--------|:--------------:|
 | CSV    | "Comma Separated Values" represent columns, while each line represents a row of data; common in a variety of contexts | [example](https://github.com/leokassio/weather-underground-data/blob/master/data/bangkok-2015.csv) | [csv](https://docs.python.org/3/library/csv.html?highlight=csv), [pandas](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html) |
 | XML    | "eXtensible Markup Language" flexibly represent complex data in a very structured way that usually require special parsers; data files can be validated against a known structure | []() | [xml](https://docs.python.org/3/library/xml.html), [pandas](https://pandas.pydata.org/docs/dev/reference/api/pandas.read_xml.html) | 
 | JSON   | "JavaScript Object Notation" represents data much like XML in a structured, but less strict form | [example](https://github.com/leokassio/weather-underground-data/blob/master/data/bangkok-2015.csv) | [json](https://docs.python.org/3/library/json.html), [pandas](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_json.html), [geojson](https://geojson.org) | 
 | netCDF4   | [Network Common Data Format](https://www.unidata.ucar.edu/software/netcdf/) v4 developed and maintained here at UCAR by [Unidata]( https://www.unidata.ucar.edu/) represent complex multi-dimensional data in a variety of sciences; common in Geosciences and usually require special libraries to parse | [example](https://github.com/Unidata/MetPy/blob/main/staticdata/NAM_test.nc) | [xarray](https://docs.xarray.dev/en/stable/user-guide/io.html#netcdf) |
 

### Computation
Computational thinking, therefore, begins with the problem of taking unstructured or structured data and _doing_ something with it.  Perhaps we want to detect patterns in a sequence of bits -- a _computational_ approach will need to be developed parse those bits and then look for patterns.  It might be that we have data about hourly air temperatures and need to understand the median or mean of those temperatures.  A _computational_ approach will be necessary (albeit one we have likely already been exposed to) to get at those answers.  When we look at computational thinking, we don't always have to think about _novel_ approaches, some are the same old tried and true one's that we've known for some time (mean), while others will require a high degree of ingenuity and cleverness.


### Algorithms
Algorithms are at the heart of computation and if data are the gasoline, algorithms are the engine, but let us be clear: algorithms _do not require a computer_, but with the data of today, nothing of value is possible _without a computer_.

Thus, algorithms are the fundamental building blocks of computation -- without them, the functioning of most of what we could call "the modern data analysis", would cease to exist.  Algorithms are all around us, and here are a few basic definitions of algorithms to consider:

* _"methods for solving problems which are suited for computer implementation"_
(Sedgewick)
* _"an exact prescription, defining a computational process, leading from various initial data to the desired result"_(Markov)
* _"a set of rules which tell us, from moment to moment, precisely how to behave"_ (Minsky)

**Data provide the raw material to algorithms** so that the underlying value of that data can be realized.  Algorithms are the recipes that bring the raw material of data into the myriad of dishes we do analysis and interpretation over, and form the basis of the _procedural_ work of computational thinking.  We will not only need to understand how to decompose data into its constituent parts so we might know what questions we can ask, we develop algorithms to help answer those questions.  

For many of us, however, an algorithm is realized as a program, and later, we will evolve our thinking more fully, but the abstract heart of an algorithm is _the application of some process or processes within a loop over some data_.

### Complexity

One of most important (and overlooked) things we can do to step to computational thinking on the right foot, is to recognize that _complexity is not our friend_, and we must work hard to _manage or reduce_ it as much as possible.  Not only algorithmic complexity, but the problem complexity and even organizational complexity.  There is a different complexity in the world of algorithms that we won't broach here, but know that is a different (and also important) complexity that requires a different frame to discuss in the context of the [analysis of algorithms](https://www.geeksforgeeks.org/complete-guide-on-complexity-analysis/).  This tutorial here is not that. 

##  Algorithms: A Quick Tour

If algorithms make the data world go round, here are 4 major concepts that form the **basic foundation**:

* counting
* summing
* searching
* sorting

The good news is that most modern programming languages implement the basic versions of these concepts for free, so you can build on them.  You will quickly find that most algorithms build on these simple constructs into more complex constructs.  You will also recognize that some of these are variants of one another.  For example, if you are trying to find the min/max value in a sequence, the problem could be solved with searching or sorting algorithms.

But let's go through these concepts in notebooks so we can see how we go from the _idea_ to _the code_ (however simple).

| Notebook | Concepts |  Link  |
|:--:|:---|:--:|
| 1 | Counting algorithms | [nb/w02_algos_counting.ipynb](nb/w02_algos_counting.ipynb) |
| 2 | Summing algorithms | [nb/w02_algos_summing.ipynb](nb/w02_algos_summing.ipynb) |
<!-- | 3 | Min/Max algorithms | [nb/w02_algos_minmax.ipynb](nb/w02_algos_minmax.ipynb) | -->
| 3 | Sorting/Searching algorithms | [nb/w02_algos_searchsort.ipynb](nb/w02_algos_sorting.ipynb) |

##  Data Structures: A Quick Tour

Algorithms are easy to understand when there are simple things to run them on (numbers, strings), but the world 
is much more complex (not really, but really), so we need to _create_ data structures to hold more complex
versions of simple things like numbers and strings.  Don't worry, if you've used a list, you've already 
had your initial run in with a data structure (albeit a simple one).  You may have run into more complex
versions of lists as well -- say a _queue_ ... the typical grocery store line.  The first people in the line
are the first out of the store, when there is one register.  When there are multiple registers, this 
may not hold true.  You can think more on what the optimal number of registers a store needs to have that would
guarantee a line wait time of no more than 2 minutes, if the average register time is 90 seconds.

This type of problem is where algorithms meet data structures and where computation thinking begins to
get interesting (and complicated).

Stepping back a bit, let's do a quick tour of data structures in Jupyter notebooks:

| Notebook | Concepts |  Link  |
|:--:|:---|:--:|
| 1 | List (and list-like) data structures | [nb/w02_ds_lists.ipynb](nb/w02_ds_lists.ipynb) |
| 2 | key-value pair data structures | [nb/w02_ds_keyvals.ipynb](nb/w02_ds_keyvals.ipynb) |
| 3 | Variations of these themes | [nb/w02_ds_variations.ipynb](nb/w02_algos_minmax.ipynb) |
