---
layout: page
title: Version Control with Git
description: intro, version control with Git
---

- [Section 1: Version Control](index.html)

  - define a clear history by taking "snapshots" as you work
  
  - track only certain files with .gitignore files

  - bonus: set Visual Studio Code as your Git editor

- [Section 2: GitHub, Merging, and Branching](GitHub_Merges_Branches_CodeReview.html)   

  - share code with collaborators
  
  - resolve conflicts
  
  - review code with pull requests

- [Section 3: Setting up Git and GitHub](SetupGitandGitHubActivity.html)

  - set up Git on your computer

  - clone a repo from GitHub and make your first commit!

  - additional useful links

<img src="octocora.png" alt="drawing" width="200"/>

## Section 1: Version Control with Git

- Git tracks your changes, allowing you to define a clear history

- Whenever you'd like to add to your history, take a snapshot, called a "commit", and add a message.

- To look at a previous version of a project and its commit message, check out the previous commit, then come back to the newest version.

- Git helps you take care of your future self, so you'll know exactly which version of your code created that design report!

Let's create a new project directory and see how Git can help us track our changes.   

*note: The `code` command I use below only works if you've set Visual Studio Code as your Git editor. To do so, follow **Bonus: Set Up Visual Studio Code** instructions at the bottom of this page. Otherwise, you can skip lines starting with `code`, replacing them by creating and editing your readme.md file in another text editor.*      
```shell        
mkdir example-repo # create a new folder
cd example-repo
git init # create a Git repository
git status
code readme.md # create and make changes to the readme in VSCode
git add readme.md # stages file
git commit -m"starting a readme for docs" # create a new commit with a log message
git log # to see our repos commit history. each commit has a unique ID, called a SHA
git show SHA # use SHA to see only its changes
code readme.md # make new changes to the readme
git diff # see only new differences
git add readme.md # add these changes
git reset # oops! didn't mean to add those
```    

Now, you have a Git repo!

### Control what you track with a Gitignore File   

We *want* to track:

- scripts: any kind of code in R, Rmd, Python, Julia, Fortran...

- text documentation: 

  - readme files
    
  - data dictionaries
  
  - data analysis pipelines (instructions for reproducing results)
  
We do *not* want to track:

  - large or sensitive data files. (Unauthorized users cannot access private repos, but its still not best practice to track data files.)

  - pdfs, images, figures: instead, document how they can be reproduced

  - MS Word/Powerpoint documents

To avoid accidentally adding these files, we can use a gitignore file.  

*note: To use the `code` command used below, follow the **Bonus: Set Up Visual Studio Code** at bottom of this page. Otherwise, you can skip lines starting with `code`, instead creating and editing your data.csv, words.docx, words2.docx files in another text editor.*  

```shell        
code data.csv # add a data file to the repository. We dont want to track this!
code words.docx # create a word document. We dont want to track this either
git status
code . # VSCode bolds all file names
code .gitignore # create a .gitignore file, add *.csv, *.docx, any other file extensions you dont want to track
git status
git add .gitignore
git commit -m"adding a gitignore file to ignore csv and docx files"
code words2.docx # create another word file
git status # git automatically ignores this new docx file
code . # ignored files are now lighter in VSCode
```      

### Version Control with Git: Summary 

- tracks your changes as you work, allowing you to **define a clear history**

- **.gitignore** files help us control what is tracked

- useful commands     
**git status**: summarizes changes that are staged/not staged for next commit    
**git add**: stages changes    
**git reset**: unstages changes    
**git diff**: shows differences in files since last commit   
**git commit -m"commit message"**: commits stages changes with a message   
**git log**: shows Git history, with each commit's SHA (id)    
**git show SHA**: shows commit's changes and log message    


### Bonus: Set Up Visual Studio Code  
To use the `code` command and set Visual Studio Code as your Git editor, follow these instructions (from the [VSCode docs](https://code.visualstudio.com/docs/editor/versioncontrol#_vs-code-as-git-editor)).    

**Step 1:** Download Visual Studio Code [here](https://code.visualstudio.com/download).    
**Step 2:** Add code command to path.        
  - **macOS**: From the View menu, select Command Palette. Within the Command Palette, type: Shell Command: Install 'Code' command in path      
  - **Windows**: Make sure you selected Add to PATH during the installation.    
  - **Linux**: Make sure you installed Code via our new .deb or .rpm packages.    
    
**Step 3:** In the terminal, type:    
```shell    
git config --global core.editor "code --wait"   
```    
You're all set!   

--------------------------    

[Section 2: GitHub, Merging, and Branching](GitHub_Merges_Branches_CodeReview.html)   

[Section 3: Setting up Git and GitHub, Useful Links](SetupGitandGitHubActivity.html)   
