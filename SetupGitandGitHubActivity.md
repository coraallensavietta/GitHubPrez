---
layout: page
title: Set up Git and GitHub, Clone a Repo, and Make a Commit
description: interactive activity to set up Git and GitGub, useful links
---
 
[Section 1: Intro and Git](index.html)   

[Section 2: GitHub, Merging, and Branching](GitHub_Merges_Branches_CodeReview.html)  

--------------------------    

## Section 3: Set up Git and GitHub, Clone a Repo, and Make a Commit

In the following steps, we will set up Git on our computers, cache our GitHub credentials, clone a repo, and make a first commit! We only need to do steps 1-4 once, so once you've completed them, you can skip them in the future and jump straight to step 5.

**Step 1**: If you don't already have one, [create a GitHub account](https://docs.github.com/en/github/getting-started-with-github/signing-up-for-github/signing-up-for-a-new-github-account) and verify your email address.  

**Step 2**: If you haven't done so, email or Slack your user ID to Henrik, Kert, or Pravin so they can add you to the Berry Consultants GitHub team.  

**Step 3**: Step up Git on your local computer.   
a) Verify that you have Git version >= 2.0 on your computer    
```shell    
git --version
```   
If Git is installed, you'll get a message like "git version 2.xx.x (Apple Git-128)". If not, download Git [here](https://git-scm.com/downloads).    

b) Set your Git username by typing in the terminal:   

```shell   
git config --global user.name "yourGitHubusername"
git config --global user.name # to confirm that it worked correctly
```

c) Set your commit email address    
Find your GitHub noreply email by following [these instructions](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address#setting-your-commit-email-address-on-github). Then, type into the terminal:   

```shell    
git config --global user.email "yournoreplyemail@email.com"
git config --global user.email # to confirm that it worked correctly
```

**Step 4**: Cache your GitHub credentials in Git.   
a) Test that the credential helper is installed by typing into the terminal:   
```shell    
git credential-osxkeychain
```   
If you get a message like "> Usage: git credential-osxkeychain <get|store|erase>", it's installed. If not, type `brew install git` into the terminal. If you don't have homebrew, download it here: https://brew.sh/, then type `brew install git` into the terminal.

b) Tell Git to use osxkeychain credential helper by typing:          
```shell    
git config --global credential.helper osxkeychain 
```   

c) Last, create a personal access token on GitHub by following [these instructions](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token). Save it in a safe place (like LastPass or another password manager). You'll use it like a password when performing Git operations over HTTPS.   

**Git and GitHub are now set up!** Since steps 1-4 only need to be done once on each computer, you won't need to repeat them. Now you're ready to clone your first repo!

**Step 5**: Clone a repo     
Navigate to the folder where you'd like to keep the Berry Simulation Library repo. Make sure it's not already a git repository by typing the following into the terminal:   
```shell      
git status # should tell you are not in a Git repo. if not, move out of the repo
git clone https://github.com/BerryConsultants/Shared-Trial-Simulation-Library.git # HTTPS address for this repo
```  
You now have a local version of this repo on your machine.    

**Step 6**: Push your first commit!     
Add a new file to the repository, named with your initials (e.g. yourinitials.txt) by typing the following into the terminal:    
```shell  
cd Shared-Trial-Simulation-Library/testcommits/ # move into testcommmits directory 
touch your-file-name # create a new file named yourinitials.txt 
git add your-file-name # stage your new file using its file name (yourinitials.txt)
git status # check the status of your new file
git commit -m"pushing my first commit to the Berry Code Library!" # commit with message
git push # push your additions to the remote repository
```   

**Congratulations!** You've set up Git, GitHub, cloned a library, and pushed your first commit to a GitHub repo. You're ready to explore all the great tools Git and GitHub have to offer! Check out [your personal dashboard](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/managing-user-account-settings/about-your-personal-dashboard), follow some of your [Berry colleagues](https://github.com/orgs/BerryConsultants/people), or [create a new repo](https://docs.github.com/en/github/getting-started-with-github/quickstart/create-a-repo).

### Setting up Git, GitHub, and Making your First Commmit: Summary   

- Steps 1-4 only need to be done once on each computer. Once you're completed them, you're all set!

- To clone a repo, use the command `git clone` followed by the repo's HTTPS address

- In general, add to or change a repo with the following four commands (in this order):   
    
    - `git pull` to get the latest changes from the remote version on GitHub
    
    - `git add filename` to stage your updates
    
    - `git commmit -m"message here"` to take a snapshot to add to the Git history
    
    - `git push` to push your updates to the remote GitHub repository    


## Useful Links    
 
- [Git docs](https://git-scm.com/doc)   
 
- Collaborate with [Pull Requests](https://docs.github.com/en/github/getting-started-with-github/quickstart/github-flow)
  
- Manage projects with [Issues, PRs, and team discussions](https://docs.github.com/en/github/getting-started-with-github/quickstart/communicating-on-github)
  
- [Getting started on GitHub](https://docs.github.com/en/github/getting-started-with-github/quickstart)

- This tutorial covers using GitHub through the terminal, but you can also use [RStudio](https://happygitwithr.com/rstudio-git-github.html) or [GitHub's desktop app](https://desktop.github.com/).

- And now that you've caught the GitHub bug, [make your own octocat](https://myoctocat.com/)!

<img src="octocora.png" alt="drawing" width="200"/>

--------------------------    

[Section 1: Intro and Git](index.html)    

[Section 2: GitHub, Merging, and Branching](GitHub_Merges_Branches_CodeReview.html)   
