# NLTK Exercises

This repository contains Jupyter notebooks with the exercises from the _Natural Language Processing with Python_ book. You can make your own copy of the notebooks, run them, and complete the exercises to practice skills from the book and test your understanding.

## Getting Your Own Copy

Make sure you have Git on your computer, and create a GitHub account. While logged into your GitHub account, press the *Fork* button in the upper right of this repository to make a copy for your own account. You'll complete the exercises in your own copy.

Once you've forked the repository and are looking at the copy in your account (the page heading should say *[your user name]/nltk_exercises*), find the URL for your repository by clicking on the green *Clone or Download* button. Using whatever interface you prefer, clone your repository to your local computer. (For example, if you use git through the command line, go to the directory where you'd like the specific directory for these exercises to be created, and type `git clone https://github.com/[your user name]/nltk_exercises.git]`--this is the link you got from the Clone button.)

### Updating Your Copy

To keep your own copy of the exercises up to date (for example, as new features are added), you will need to retrieve changes from this repository and integrate them into your own repository. While this process can grow complicated, at its simplest it is just a matter of telling git about the original and asking it to fetch the changes. You'll have some choices to make, depending on how you work.

Before you attempt to retrieve any updates, you must commit your own changes. In Terminal, go to your local working directory for your fork (that is, the directory you cloned from your fork on GitHub). Use `git add` to specify the files you've updated. If you simply want to add any changes since your last commit, enter

    git add -A

Now your updates are *staged*; to see a list of changes git knows about, you can type `git status`. But you still have to *commit* your files in order to record the changes in history. To do so, use the `git commit` command like so:

    git commit -m "[Enter a brief description of the changes you've made. Example: 'Completed exercises for ch. 1.']"
    
Now that you've commited your changes, you're ready to go about getting any updates.

No matter what, you need to begin by letting git know about the original repository. In the directory that contains your local working copy, execute the following command:

    git remote add upstream https://github.com/paulbroyles/nltk_exercises.git

Your local repository is now aware of the existence of the original repository. (Note that if you're working on your fork on more than one computer, you'll need to run that command on each.)

Next, you need to get updates from the original repository onto your local computer. Do that with the following command:

    git fetch upstream

Now, our computer is aware of any changes that have been made to the original repository. But if you look at your files, you'll see that nothing has changed. That's because you have to integrate the changes into your fork. And it's here that you'll have to make a choice, based on your particular needs. Choose **one** of the following approaches based on your needs.

**If you work on only one computer**, it may make sense to *rebase*. This alters the history of your repository so that it is as though it always contained the updates to the original branch. This results in a history that is clean and easy to follow. In order to rebase, after fetching from upstream, run the following command:

    git rebase upstream/master

Git will integrate all the changes made to the original repository into your local copy; when it's done, you'll have the updated files, and your history will incorporate both changes you have made and changes to the original repository. However, if you attempt to push your fork back to GitHub, you'll probably find that it's rejected. That's because you have rewritten history; the commits on your local computer and those you've pushed to GitHub in the past are no longer the same, as far as git is concerned. You can essentially overwrite your whole history on GitHub by running `git push -f`. But now, if you have any copies elsewhere (or if anyone else has cloned or forked your repository), those copies will be out of step with what's on GitHub. So if you're working on more than one computer, things become complicated. (In general, it's considered bad form to rewrite the history of commits you have already pushed elsewhere.) So...

**If you work on more than one computer, or work with others**, it may instead make sense to *merge*. This will leave you with a much muddier, more complicated history, but it doesn't rewrite the history, meaning that you remain able easily to push to GitHub and update other copies accordingly. To make this happen, instead, execute the following command:

    git merge upstream/master
    
This will merge the changes into your git history, and you can then push accordingly.

## Installing and Using Jupyter

Download and install Jupyter, following the directions at http://jupyter.org/install.html. Once you have successfully installed Jupyter, open the Terminal and navigate to the directory where you cloned your fork of the repository and enter the *nltk_exercises* directory. Once you're inside that directory, type `jupyter notebook` to start Jupyter. A browser window should open automatically; if not, follow the instructions on the screen.

Once Jupyter launches, you'll be presented with a list of available notebooks, ending in the extension .ipynb. Select the notebook for the chapter you're on to launch it.

Inside the notebook, you'll find each of the exercises from the end of the chapter, followed by a grey box, with *In [ ]* appearing to the left. To complete an exercise, click on the box and type the code that solves the problem you've been posed. Once you've written enough code that you think you've solved the problem--or you just want to test what your code does--click the button on the toolbar that looks like a Play button. That will run the code in the cell (box) you've currently selected; any output from the code will appear directly below the box where you entered the code. If you make changes to the code, simply click the same button again to re-run it.

If an exercise requires an answer in text, rather than in code (for instance, if it's asking you to explain something), go to the selection menu that currently says Code and select Markdown instead. Here you can enter text in Markdown syntax; you can simply enter plain text, or visit https://daringfireball.net/projects/markdown/syntax for documentation of Markdown. (The questions in each notebook have been entered in Markdown.)

