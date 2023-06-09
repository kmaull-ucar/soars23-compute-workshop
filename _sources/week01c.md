Jupyter Fundamentals
------  

```{card}  
:class-card: objectives 
:class-header: text-center font-weight-bold
:class-body: bg-light font-italic 

**OBJECTIVES**
^^^
* how to build good notebooks
* Jupyter: how and why?
* strategic notebook development 

```
<!-- :class-header: text-white-50 text-center font-weight-bold bg-soars-card
:class-body: bg-light font-italic 



-->
## The Quick Tour

The notebooks below will give you a quick tour of the key features of the language:

| Notebook | Concepts |  Link  |
|:--:|:---|:--:|
| 1 | Interactive Jupyter; the value of interactive components in your notebooks | [nb/w01_interactive_jupyter.ipynb](nb/w01c_interactive_jupyter.ipynb) |
| 2 | Jupyter | -- |

### Plugins and Extensions

Jupyter plugins and extensions make your life easier in the environment.  There are many extensions out there, some are mature, while others are very much beta software.

Some very useful plugins are listed here:


* [jupyterlab/jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git): a powerful extension that allows you to use git without leaving the main interface
* [jupyterlab/jupyeterlab-github](https://github.com/jupyterlab/jupyterlab-github): an extension that provides easy access to Github repos and searching
* [jupyterlab/jupyter-ai](https://jupyter-ai.readthedocs.io/en/latest/): a newer extension for ChatGPT, AI21, Anthropic, HuggingFace and SageMaker AI models


Other extensions of note:

* [jupyterlab/jupyter-renderers](https://github.com/jupyterlab/jupyter-renderers): a useful tool for rendered coon 


## Strategies for Python-based Jupyter notebooks

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
    
* **Give attribution to borrowed code, data and ideas.**

    * if you find useful code, _no matter the source_ -- whether Github, stackoverflow, Reddit, a random website etc. -- give thanks. It doesn't need to be complex -- a simple comment in your code like:
    ```python
        # thank YOU miquel for the amazing f-string hints @ https://miguendes.me/73-examples-to-help-you-master-pythons-f-strings
        print(f"Hello {myvar:05})
    ```
    * we are all here to help each other, and giving
    a nod to those who put together something
    that got you over the hump isn't too much to ask. Furthermore, one day something _you_ did might be useful to someone else and they might return the attribution favor!

* **Use version control.**

    * there are wonderful benefits to keeping track of the changes in your code ... _use them_
    * there is a [git plugin for JupyterLab](https://github.com/jupyterlab/jupyterlab-git)  that is an essential tool for keeping track of your work.  You can use it to store your work in Github or wherever else you want your code to be.  Remember you are free to use any number of other platforms such as Gitlab, Codeberg, Bitbucket and others (including hosting your own git server, which is easier to do than you might think)