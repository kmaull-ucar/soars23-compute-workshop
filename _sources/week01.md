Week 1
------  

````{dropdown}  OBJECTIVES
:container: + shadow
:title: bg-secondary text-white text-center font-weight-bold
:body: bg-light font-italic
:animate: fade-in
:open:

* (re)Introduction to Jupyter
* developing computational narratives
* understanding basic git and Github
* understanding the role of Linux in scientific computing 
````

## Jupyter

As you may know, Jupyter is a simple, interactive platform for writing Python code.  To be certain, the Jupyter environment supports multiple languages, including [R](https://www.r-project.org/), [Julia](https://julialang.org/) and Java to name a few.  In fact, the name (and spelling) for the work comes from (Ju)lia, (Pyt)hon and (R).

The appeal of the Jupyter environment is simple:

* it is interactive,
* it can be hosted locally or on the cloud,
* a notebook can be a combination of code and narrative (aka "computational narrative"{cite}`jupyter_project_2017`)
* it is a great platform for sharing.

Jupyter notebooks can be created in the [standard notebook environment](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html) or the newer, expanded feature [Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html) environment.  Which ever you choose, there are a few basics about the platform that you'll want to learn and this video may be valuable to introduce you to some of the features of Jupyter Lab.

<iframe  title="YouTube video player" width="640" height="480"  src="https://www.youtube.com/embed/A5YyoCKxEOU" frameborder="0" allowfullscreen></iframe>

## Structure of Notebooks and Narratives
Notebooks impart a great deal of flexibility to the creator, and with that flexibility comes some basic responsibilities.  Though not every notebook is meant to be shared, you should assume that the majority of your notebooks _will_ be shared or executed by at least one other person -- even if you take the approach that the one other person is your _future self five years from now that might have completely forgotten what you were working on at the time the notebook was created_.  

```{tip}
Start your notebook with a single markdown cell that describes the purpose of the notebook.
```

Any notebook you create has a purpose, and in the first cell of your notebook, make a habit of  least put a single markdown cell that describes that purpose.  This cell will at the very least describe (very briefly), why the notebook has been created and what problem it is intended solve or explore.  

Here is a simple example:

* [Example #1](./notebooks/example01.ipynb) #todo link externally

### Computational Narratives
The Jupyter environment is designed to support what are called _computational narratives_
we'll talk about what they are and then we're going to create one ourselves. there's really nothing special about it -- in fact we can initially approach it as a fancy way to indicate a "notebook" that pays special attention to a developing good flow through the core research, implementation (computation) and narrative explanation of that research.  In the end, narratives support the researcher, the audience and the research itself.

That is to say, and as mentioned previously, the narrative is for you but not _only for you_ -- it's also intended for the audience who will be interested in your work and possibly reproducing it.  Many times we create notebooks are that do not expose details  about what trying to accomplish in the notebook -- indeed, many times we develop a single notebook with a large amount of code to produce a graphic of visualization, and months later when we return to it, we are unsure exactly what the intent of the code was, or worse, when we try to modify the code that was there (say, to update the data or improve it) we end up unnecessarily repeating previous work.  With a narrative in place we can position our work to be more intentional and thus enhance its utility and value in the future.  

```{tip}
A good narrative maintains focus on the what, why and how of your work.  Keep focus on details to the extent that they help you and the audience understand key decisions and supporting computation.
```
A good narrative has one objective: to describe the process and workflow of your research so that you and others understand what was done, and ostensibly how to reproduce it, not only through the original notebook, but through any other means (copying, borrowing, etc.). The computational narrative truly emerges as a virtuous relationship between code, computation and the expository narrative and is more than just a description of what was done (though that is a great place to start in the absence of anything else), but rather a detailed account of the purpose of the notebook and the underlying work, the decisions that were made at various points in the notebook and _why_ they were made. doing this not only provides the context necessary for others to understand what was done, how and why, but it is also an important reminder to yourself of these things, since as time moves forward, notebooks accumulate and it is easy to forget all of these details.

### Narrative Structure & Flow
Often we are faced with developing a notebook with only minimal information about the end goal.  We want to write some code, produce some output (in the form of graphs, tables, etc) and then we might want to share that with others.  The notebook provides an opportunity to layer our work in a way that a commitment to one notebook is not necessary.  Indeed, our first notebooks are often scratch notebooks (but many times we don't actually see them that way and they end up as the final notebook).  We would like to avoid the problem of scratch notebooks turning into final notebooks and so planning your narrative structure (once you get going in a direction) is important.

A single notebook should be designed to guide the narrative through a problem, computational resolution (or attempt at resolution) and summary of outcome(s).  This will include:

1. **problem** exposition or purpose, 
2. **code** (with output) and 
3. **interpretation** and summary. 

A simple notebook will just have those three components and repeat them for each of the problems attempted in the notebook.  When a problem gets large, there may be additional structural considerations:

* How much of the notebook is code vs exposition vs theoretical?
* If the code is extensive, is that code better packaged outside the notebook in `.py` files or Python modules?
* Are the expository components of the notebook better stored in separate notebooks to allow focus on one component or another?

You may eventually come to the conclusion that a single large notebook is confusing and diminishes the value of your work.  You may find some parts of your narrative are algorithmically intensive and need addition exposition or more complete mathematical treatment.  Some of that explanation may be in the form of code cells, and it may be appropriate to develop multiple notebooks to manage the complexity of your work.  Recognizing this early can be an important step toward good narratives.

### Computational Flow
The computational flow of your notebook refers to the _code cells_ of your notebook.  This might also include the output of those cells, including graphics, plots and visualizations, as well as text output (e.g. the result of a calculation).  There are simple steps to keep your code as tidy as possible so that it is not only reusable, but that cells can be rerun easily with their appropriate contexts and imports.  

Consider:

1. **keep one time imports where they are used**: if a cell can be run in one execution, but involves imports that do not get used by other cells in the notebook, just include them in that cell. For example, a cell that uses the [`csv` module](https://docs.python.org/3/library/csv.html) and nowhere else in the notebook allows it to be executed standalone when it needs to:
    ```python
    import csv

    cell_data = []
    with open('file.csv', 'w', newline='') as f:
        freader = csv.reader(f, delimiter=',',
                                quotechar='"', quoting=csv.QUOTE_MINIMAL)
        for row in freader:
            if row['column'] == 'data':
                cell_data.append(row)
    ```
2. **use minimal error checking to halt a notebook when known preconditions are not satisfied**: if error checking needs to occur, don't let successive cells run, use [`SystemExit()`](https://docs.python.org/3/library/exceptions.html?highlight=systemexit#SystemExit) to halt further execution of the notebook -- this will avert long running cells that would otherwise waste time if any assumptions about input and environment conditions are not met. See [an example]().  You could alternatively consider [`assert`](), which will signal that some precondition is not satisfied and will halt execution of the notebook.
3. **indicate long running cells with a comment and/or narrative note**: long running cells that can take minutes or hours to execute should be indicated either with a comment at the first line of the cell or a markdown cell preceding it say that the cell is likely to take time.  If the cell is instrumented and the running time is known, the comment might also indicate such.
```python
# NOTE: THIS CELL USUALLY TAKES 20m TO RUN ON MOST HARDWARE
import time

for i in range(0,20):
    time.sleep(60)
```

so what's in a narrative you have images of visuals usually those the output cells you know if you ran a patters or you ran a plot or you read a book whatever out lot of times you'll have your formulas exploration of algorithms you have links to other notebooks other data other modules and those are the no books could be a collection of notebooks that you is up our part of your broader narrative

### Cross-notebook Linking, Table of Contents and Flow
One of the most profoundly useful and perhaps underused features of the notebook ecosystem, is notebook linking.  By this we mean developing notebooks that link to other notebooks that represent a larger collection.  For example, when a single notebook it large and complex, it may be necessary to consider breaking it up into other notebooks.  Unifying one more more notebooks is then a simple matter of linking them.

For example, a markdown cell in a notebook linking to another would look like this:
```markdown
So at once, we have shown the first part of the analysis.  

The second part can be found in [notebook #2](./notebook02.ipynb).
```
This snippet will signal to the reader (and you), that another notebook continues the narrative.

```{tip}
Links can be two-way, and it is a good idea to link _back_ to the notebook you linked _to_.  This allows the context and flow to stay intact.
```

Should you choose to develop a single linear notebook, a table of contents can be a good idea.  You can manually create your TOC or try one of several methods for automatically creating it.  Either way, your notebooks will increase their utility by doing this.


### Citation
Citation, acknowledgement and attribution are the cornerstone of collaboration and are at the heart of scientific communication.  A notebook may have citations to many things: academic papers, datasets, software, external resources, computing resources, licenses, etc.  It should be a reminder to you that attribution is an important thing to your own notebook as well. When you share your notebook with others, or submit is as a supplement to a published paper or presentation, it may be worth considering getting a permanent identifier such as a DOI (Digital Object Identifier) and providing appropriate attribution instructions in your own notebook, especially if they are in Github or some other public repository.

```{tip}
Consider the services at Zenodo ([https://zenodo.org](https://zenodo.org)) and Figshare ([https://figshare.org](https://figshare.org)) which can help you mint a permanent and persistent DOI (Digital Object Identifier).  Learn more about DOIs [here](https://www.doi.org/factsheets/DOIKeyFacts.html).
```



## Basic git and Github


Though notebooks do not require it, the use of git and Github are highly valuable tools in your scientific workflow.  But before using either, it should be clear what each of these tools are and what they bring to the table for your work.

### git

[git]() in its simplest form, is a tool that allows you to keep track of changes to files.  Build atop the heritage of software revision control systems, which function to make sure source code changes can be tracked, and in the collaborative case, merged or otherwise monitored by a team of people (developers, etc.).  git is its own tool and should not be confounded with _Github_, which can be seen as a collaborative front end to tools like git.  You can use git without Github, and while _technically_ you can use Github without git, intermediate and advanced use require it.

There are really three aspects of git that you should be familiar with:

* repository initialization
* source file editing
* source file committing

Repository initialization is a simple process of making a set of files _visible_ to git, so they can be tracked.  You must initialize repository before you can put any file under git's control.  After you have initialized a repository, you may add files, edit them and begin to let git know what changes you made to those files so that in the future, you can keep track of those changes -- especially if they are dramatic or represent big changes from one point in time to another.  Once your changes have been made, you must commit them to the repository and then the magic begins.  Git will be able to automatically show the differences in files, so that in the future, you have a trackable _history_ of those changes.

Git is mostly a command line tool, though there are several front end tools that make it less unfriendly:

* 
* 
* 

### Github

![](./github_com.png)

But one of the most friendly (and popular) front ends to git is [Github](https://github.com), but two other platforms [Gitlab](https://gitlab.org) and [Bitbucket](https://bitbucket.org) offer similar and equally good alternatives.  You are free to use whatever platforms make the most sense for you, your team and your project, though we will focus on Github here.  

Github is a website that provides front end access to git repositories, but more importantly, it provides an excellent platform for collaboration.  You can share code with other individuals, teams, researchers, etc.  You can privately or publicly share, and there are many additional functionalities to support your code and your team, many of which you may never find use for, or know even exist.

Though you might only use Github with an eye toward its basic and limited functionality, it is nonetheless a platform that you cannot ignore and a basic working knowledge of what it provides will go a long way in your research career.


<!--
so if you have a particular license on your notebooks or your code that needs to be appropriately documented arm acknowledgments for people who may have helped you or a rip other repositories your other code bases that bomb or valuable and new accomplishing what you cops law book and how you want your noble to be cited and known by the people if you make a public right so you may be don't make a public probably good advice o

we should so that you can get of remember know what's going on okay so here's what we're gonna do it and and we may run out of time but oh what we could probably at least get started and see how far would go i'll give you like maybe ten minutes to jump in and i'll actually do this we live as well so you know if you just want to follow long that's fine if you want to do your own thing that's right so oregon just gonna explore average temperature an immunity for city minneapolis minneapolis from january first to january figure for she does them jail for twenty two it i've already grabbed his data and so it is in it is that data file that is in the repository or that you just downloaded awfully while that long we're going to use when he's panders to get the mean media min and max temperature for the time period and going to build a quick little narrative cape so ah let let me let let me ask the question i'm a of how we want to proceed we've got like thirteen minutes i can do this narrative real fast and out just talk through it i'm or i can let you all do this right now and then say how far you get ten minutes type of thing and we can chat about that or or you can do it off line and play with it says now you have access to the hope he can actually do this ah i'm in i'm open to a or oh okay did none of those lights go through the next to slides and that we can call it the in our are there any particular vote on any one of those or and configuration that i didn't mention revamp preference i mean it's want me to yeah i could certainly do it and then once you get the slides you can go back through or you can do you want in any preference on analysts or are good l a said i and i could go i could just leave it i'm to go on okay so salami lot okay so i'm going to jump in and out or do it you rather quickly here but on let's go back to the what are we trying to accomplish our right so what i'm going to do is i'm going to create a new notebook and let's go ahead and let's go and do this we're going to do a window we're going to go to the jupiter lab to sure that are it so on creating a notebook in that know book real fast i'm going to remind myself what i'm gonna do so to to remind myself you can create a marked down so by hitting the escape am and have you covered a back to ac was changing from code that lead me up let me see where's this file libby  okay i'm you can convert from marked down so lives from marked down so by hitting escape him as marco and a good quarterback to a code so by hitting escape why or we can hit the drop down and choose what you what we're going to use a markdown down so and i'm gonna go back of my son lied and i'm going to copy what i'm what i'm trying to accomplish your as mark on i'm a copy those in there and then ah the see okay so on it it actually a it's a weird stuff here though want to do that and it so if you hit shift enter as everyone remembers it'll cover that marked down to something that sector readable so i'm i'll go and here and i'll add a heading our put a a heading it overview of greatest of it give it some meteor okay virago and i notice that you know we have a nice features that are now available to us okay so my overview as i'm gonna grab a csv forget which we've already done right so at this point out what i'm gonna do is just use demo three and then uses data file gay and then when i use the pandas library to get the mean median min max the temperature with that period so forcing i'll do that import pandas as pt most people are familiar with this if you have never use pandas are there are some arm i will put the in the chat i can go and put the pandas documentation of here i'm and is is amazing and has you know lots of features so your would just leave it at that right so on and now either the question is how do i grabbed his file so i'm gonna say by data frame equals know pandas how much are you two ways to be this actually have got read csv is a csv file a i'm i'm going to read it see as we've from the file system so we're gonna do this we're going to be demo three doors and that i'm getting tab to to get at all this a i'm getting cab so ah juvenile record as is trying to open a file and it'll just sort of start inspected the file system and make it easy for you to do so i'm groups or it that pt or it so so i made a mistake and of that's good he told me you know pandas as exist bpd does obviously so i did that so now have a data frame and of do the f it would just part that been for him to the screen and let me throw off some of these distractions here for a moment ah do we need term outvoted or okay so want to do that so now what is do it it it it pulled then that that csv file and in fact i will open another terminal just a just to show you ah what that csv looks like right this is the csv the pandas as now important and if we look on the file system can see ah it's a four point one megabyte file aren't okay now i'm what am i being asked to do i want to get the mean median min max of temperature are so i'm just from the audience it who has used it it just raise your hand who has used pandas before ayman a know and he said you you had a alyssa okay right okay cool now on how and why how do i just get the ah t average column or i i do that pandas i'm on a d d f what the f that t average call him or away or women amy 
-->
