---
layout: page
title: Collaborate and Resolve Conflicts Seamlessly with GitHub
description: Collaborating, Merging, Branching, and Code Review
---
Previously   
[Section 1: Intro and Git](index.html)   

[Section 3: Setting up Git and GitHub, Useful Links](SetupGitandGitHubActivity.html)  

## Section 2: Collaborate and Resolve Conflicts Seamlessly on GitHub
One of Git's best features is its ability to create text files that compare two versions of a file. These are called **diffs**. Git creates a **diff** when we compare a current version to one from six months ago. It also create a diff when we compare a version of my current code with Lindsay's code.

GitHub stores a **remote** copy of each repository so that we can create diffs with other people!

### Sharing our new repository with a collaborator
First, we'll go to GitHub.com, create a new repository, and add our collaborator as a contributor. Then, we'll connect this remote GitHub repo to our local repository by following GitHub's instructions.
```{bash, echo = TRUE, eval=FALSE}
git remote add origin https://github.com/coraallensavietta/example-repo.git
git branch -M main # rename main branch
git push -u origin main # push all of my commits to remote
```
Now, Lindsay and I can collaborate and compare our work using git diffs!   

### Resolving Conflicts
First, let's say Lindsay goes in and makes changes to our readme.md file. 

In the meantime, I've also made changes to the readme.md file on my local computer. 
```{bash, echo = TRUE, eval=FALSE}
code readme.md # I make changes locally
git add
git commit -m"added info about location of the data dictionary"
git push
``` 
*CONFLICT!*    
Don't worry! This looks scary, but GitHub is great at handling conflicts. That's why we love it!
GitHub will walk us through resolving this conflict.
```{bash, echo = TRUE, eval=FALSE}
git pull # pull Lindsay's changes from the remote
git status 
code readme.md # open the file with conflicts and resolve the conflict
git add readme.md # add the resolved version of the files
git commit # commit this newly resolved file
git push # push the resolved version to remote
```
Now, the my local repo and the remote repo on GitHub both have the resolved version of readme.md, which includes both my changes and Lindsay's changes. Lindsay can *pull* it to her local machine and she will have it too!

### Branches and Code Review
Often we want to test out a new feature before we add it to the main code base. To do this, we create a copy of the main repository, a **branch**, where we can play around with this new code.
```{bash, echo = TRUE, eval=FALSE}
git branch multivar-model # create a new branch to try a multivariate version of the model
git checkout multivar-model # move to this branch
code readme.md # try out this new model!
git add readme.md
git commit -m"trying a multivariate version of the model"
git diff main # compare this branch to the main branch
git push # on no! need to set the remote, just as we did for the main branch
git push --set-upstream origin multivar-model # push changes to the remote repository
```

On the multivar-model branch, I just added a new version of the data analysis model to our repo. Before it's integrated into our main branch, I'd like Lindsay to look it over.

To do this, I'll use [GitHub's pull request process](https://github.com/coraallensavietta/example-repo/pulls) and ask Lindsay to review the code.

### GitHub: Summary    

- Each collaborator has a **local** version git repo on their machine. GitHub stores the **remote** version of each repo. This lets us compare our local files with those stored on GitHub.

- To get your changes, collaborators will **pull** your changes from the remote GitHub repo

- To add their changes, they will **push** to the remote.

- **conflict resolution**: If you've made changes to the same code, you can smoothly handle them with a **merge**, so that you can write code together without overwriting each others work or missing changes.

- GitHub's **branching** and **code review** makes code review quick and easy for better, less buggy code!

previously   

[Section 1: Intro and Git](index.html)   

[Section 3: Setting up Git and GitHub, Useful Links](SetupGitandGitHubActivity.html)  
