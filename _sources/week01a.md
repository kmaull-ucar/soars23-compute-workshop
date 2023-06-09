Scientific Computing, Computational Workflows and Jupyter/Python
======  

```{card}  
:class-card: objectives 
:class-header: text-center font-weight-bold
:class-body: bg-light font-italic 


**OBJECTIVES**
^^^

* scientific computing today
* (re)Introduction to Jupyter
* computational narratives
* understanding basic git and Github
* understanding the role of Linux in scientific computing 
```

## Scientific Computing Today

With the rise of advanced, ubiquitous and inexpensive computing, nearly every scientific  discipline today has (with a mix of excitement and/or hesitation) embraced computing  -- and in fact, _some_ computing skill is a practical _requirement_ to do almost any domain-specific work, no matter your discipline (even including the humanities).

It is daunting to gain skill in the tools and technologies that are driving scientific advancement, and the process takes time and requires continuous learning, since the dominant tools today may not be the same two, five or ten years into the future.

There are several axes that support the scientific computing skill today: 

* foundational **computational thinking** and **algorithmic problem solving**, 
* **software support tools**, systems interaction, **programming skill** and **open source software**,
* **data analysis** and statistical inference skill.

**Computational thinking** {cite:ps}`wing_computational_2006` is the modern approach to learning how to write code for computers, but it extends well beyond merely programming machines and into _strategic_ problem solving with _automation_ and _data_.  This is what makes the conversation so apt for scientific thinking, because at the heart of all science is data, and most modern scientific data are overwhelmingly large and thus _require automation_. To be successful today, you must understand the foundations of how algorithms facilitate scientific problem solving with large amounts of data, accelerating advancements at a pace we have yet to understand.

We address computational thinking on its own [here](./week02a.md).

**Software support tools** are required to interact with the myriad computer systems, files and platforms for computing.  These tools may include:

* software revision control systems (i.e. git), 
* software development and execution platforms (e.g. Jupyter), 
* virtualization platforms (e.g. Docker), 
* programming languages (e.g. Python, Javascript) and markup languages (e.g. Markdown, HTML)
* operating systems optimized for performance scientific computing (e.g. Linux)

Today,the language in broad use across large swaths of scientific domains from biology, chemistry, physics, atmospheric science and many others is [Python](https://python.org).

`````{admonition} Open Source Software: What is it?
:class: info

[Open source software (OSS)](https://opensource.org/) is a software model that promotes transparency, proper attribution (licensing), sharing, distribution and community contribution.  Borrowing from some of the ideals of [Free and Open Source Softwware (FOSS)](), which is a distinctly different (but also similar) model to OSS, scientific research should strive to promote the same ideals: transparency, sharing and community.
`````

**Data analysis and statistical inference** cannot be avoided when talking about _interpretation_ of scientific data and analysis.  It is no longer possible to perform complex science without some mathematical skill and a basic understanding of statistics.  When combined with software and computational thinking, data analysis and statistical inference can produce powerful outcomes.

Excellent introductions to statistical inference can be found in the [Tools, Guides and Inspiration](./tools.md) resource section of this guide.


## Software Support Tools

### Jupyter

As you may know, Jupyter is a simple, interactive platform for writing Python code.  To be certain, the Jupyter environment supports multiple languages, including [R](https://www.r-project.org/), [Julia](https://julialang.org/) and Java to name a few.  In fact, the name (and spelling) for the work comes from (Ju)lia, (Pyt)hon and (R).

The appeal of the Jupyter environment is simple:

* it is interactive,
* it can be hosted locally or on the cloud,
* a notebook can be a combination of code and narrative (aka "computational narrative"{cite}`jupyter_project_2017`)
* it is a great platform for sharing.

Jupyter notebooks can be created in the [standard notebook environment](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/what_is_jupyter.html) or the newer, expanded feature [Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html) environment.  Which ever you choose, there are a few basics about the platform that you'll want to learn and this video may be valuable to introduce you to some of the features of Jupyter Lab.

<iframe  title="YouTube video player" width="640" height="480"  src="https://www.youtube.com/embed/A5YyoCKxEOU" frameborder="0" allowfullscreen></iframe>

#### Structure of Notebooks and Narratives
Notebooks impart a great deal of flexibility to the creator, and with that flexibility comes some basic responsibilities.  Though not every notebook is meant to be shared, you should assume that the majority of your notebooks _will_ be shared or executed by at least one other person -- even if you take the approach that the one other person is your _future self five years from now that might have completely forgotten what you were working on at the time the notebook was created_.  

```{tip}
Start your notebook with a single markdown cell that describes the purpose of the notebook.
```

Any notebook you create has a purpose, and in the first cell of your notebook, make a habit of  least put a single markdown cell that describes that purpose.  This cell will at the very least describe (very briefly), why the notebook has been created and what problem it is intended solve or explore.  

Here is a simple example:

* [Simple Example #1](./nb/w01_sample_notebook.ipynb)

#### Computational Narratives
The Jupyter environment is designed to support what are called _computational narratives_
we'll talk about what they are and then we're going to create one ourselves. there's really nothing special about it -- in fact we can initially approach it as a fancy way to indicate a "notebook" that pays special attention to a developing good flow through the core research, implementation (computation) and narrative explanation of that research.  In the end, narratives support the researcher, the audience and the research itself.

That is to say, and as mentioned previously, the narrative is for you but not _only for you_ -- it's also intended for the audience who will be interested in your work and possibly reproducing it.  Many times we create notebooks are that do not expose details  about what trying to accomplish in the notebook -- indeed, many times we develop a single notebook with a large amount of code to produce a graphic of visualization, and months later when we return to it, we are unsure exactly what the intent of the code was, or worse, when we try to modify the code that was there (say, to update the data or improve it) we end up unnecessarily repeating previous work.  With a narrative in place we can position our work to be more intentional and thus enhance its utility and value in the future.  

```{tip}
A good narrative maintains focus on the what, why and how of your work.  Keep focus on details to the extent that they help you and the audience understand key decisions and supporting computation.
```
A good narrative has one objective: to describe the process and workflow of your research so that you and others understand what was done, and ostensibly how to reproduce it, not only through the original notebook, but through any other means (copying, borrowing, etc.). The computational narrative truly emerges as a virtuous relationship between code, computation and the expository narrative and is more than just a description of what was done (though that is a great place to start in the absence of anything else), but rather a detailed account of the purpose of the notebook and the underlying work, the decisions that were made at various points in the notebook and _why_ they were made. doing this not only provides the context necessary for others to understand what was done, how and why, but it is also an important reminder to yourself of these things, since as time moves forward, notebooks accumulate and it is easy to forget all of these details.

#### Narrative Structure & Flow
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

#### Computational Flow
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

#### Cross-notebook Linking, Table of Contents and Flow
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

#### Citation
Citation, acknowledgement and attribution are the cornerstone of collaboration and are at the heart of scientific communication.  A notebook may have citations to many things: academic papers, datasets, software, external resources, computing resources, licenses, etc.  It should be a reminder to you that attribution is an important thing to your own notebook as well. When you share your notebook with others, or submit is as a supplement to a published paper or presentation, it may be worth considering getting a permanent identifier such as a DOI (Digital Object Identifier) and providing appropriate attribution instructions in your own notebook, especially if they are in Github or some other public repository.

```{tip}
Consider the services at Zenodo ([https://zenodo.org](https://zenodo.org)) and Figshare ([https://figshare.org](https://figshare.org)) which can help you mint a permanent and persistent DOI (Digital Object Identifier).  Learn more about DOIs [here](https://www.doi.org/factsheets/DOIKeyFacts.html).
```

### git and Github


Though notebooks do not require it, the use of git and Github are highly valuable tools in your scientific workflow.  But before using either, it should be clear what each of these tools are and what they bring to the table for your work.

#### git

[git]() in its simplest form, is a tool that allows you to keep track of changes to files.  Build atop the heritage of software revision control systems, which function to make sure source code changes can be tracked, and in the collaborative case, merged or otherwise monitored by a team of people (developers, etc.).  git is its own tool and should not be confounded with _Github_, which can be seen as a collaborative front end to tools like git.  You can use git without Github, and while _technically_ you can use Github without git, intermediate and advanced use require it.

There are really three aspects of git that you should be familiar with:

* repository initialization
* source file editing
* source file committing

Repository initialization is a simple process of making a set of files _visible_ to git, so they can be tracked.  You must initialize repository before you can put any file under git's control.  After you have initialized a repository, you may add files, edit them and begin to let git know what changes you made to those files so that in the future, you can keep track of those changes -- especially if they are dramatic or represent big changes from one point in time to another.  Once your changes have been made, you must commit them to the repository and then the magic begins.  Git will be able to automatically show the differences in files, so that in the future, you have a trackable _history_ of those changes.

Git is mostly a command line tool, though there are several front end tools that make it less unfriendly:

* [Github Desktop](https://desktop.github.com/) client for Mac, Windows and Linux
* [TortoiseGit](https://tortoisegit.org/download/) client for Windows
* [Gitup](https://gitup.co/) client for Mac

For a quick sheet approach to some basic git command line instructions, see

* [Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf) (PDF by Github)
* [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) (PDF by Github Education)
* [Git Cheat Sheet: 50 commands you should know](https://www.freecodecamp.org/news/git-cheat-sheet/) (by Fabio Pacific@FreeCodeCamp)

#### Github

```{image} https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png
:alt: Github
:class: bg-primary mb-1
:width: 200px
:align: left
:url: https://github.com
```

But one of the most friendly (and popular) front ends to git is [Github](https://github.com), but two other platforms [Gitlab](https://gitlab.org) and [Bitbucket](https://bitbucket.org) offer similar and equally good alternatives.  You are free to use whatever platforms make the most sense for you, your team and your project, though we will focus on Github here.  

Github is a website that provides front end access to git repositories, but more importantly, it provides an excellent platform for collaboration.  You can share code with other individuals, teams, researchers, etc.  You can privately or publicly share, and there are many additional functionalities to support your code and your team, many of which you may never find use for, or know even exist.

Though you might only use Github with an eye toward its basic and limited functionality, it is nonetheless a platform that you cannot ignore and a basic working knowledge of what it provides will go a long way in your research career.
