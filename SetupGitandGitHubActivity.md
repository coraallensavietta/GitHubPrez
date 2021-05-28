---
layout: page
title: Set up Git and GitHub, Clone a Repo, and Make a Commit
description: interactive activity to set up Git and GitGub, useful links
---

Previously  
 
[Section 1: Intro and Git](index.html)   

[Section 2: GitHub, Merging, and Branching](GitHub_Merges_Branches_CodeReview.html)  

## Section 3: Set up Git and GitHub, Clone a Repo, and Make a Commit

Today we will clone the Berry Consultants [Shared Simulation Code Library](https://github.com/BerryConsultants/Shared-Trial-Simulation-Library), so that we can start contributing to it!

**Step 1**: If you don't already have one, [create a GitHub account](https://docs.github.com/en/github/getting-started-with-github/signing-up-for-github/signing-up-for-a-new-github-account) and verify your email address.  

**Step 2**: If you haven't done so, email or Slack your user ID to Henrik, Kert, or Pravin so they can add you to the Berry GitHub team.  

**Step 3**: Step up Git on your local computer.   
a) Verify that you have Git version >= 2.0 on your computer   
```shell
git --version
```
If not, download git [here](https://git-scm.com/downloads).    

b) Set your Git username by typing in your terminal:   
```shell
git config --global user.name "yournamehere"
git config --global user.name # confirm that it worked correctly
```
c) Set your commit email address    
Find your GitHub noreply email by following [these instructions](https://docs.github.com/en/github/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address#setting-your-commit-email-address-on-github).  

Once you have your GitHub noreply email, type into your terminal:   
```shell
git config --global user.email "yournoreplyemail@email.com"
git config --global user.email # confirm that it worked correctly
```

**Step 4**: Cache your GitHub credentials in Git.   

a) Test that credential helper is installed   
```shell
git credential-osxkeychain # test that credential helper is already installed
> Usage: git credential-osxkeychain <get|store|erase> # good, its installed!
```
If the osxkeychain helper isn't installed, then type `brew install git` into your terminal.  

b) After you've confirmed that the credential helper is installed, type into your terminal   
```shell
git config --global credential.helper osxkeychain # tells git to use osxkeychain credential helper
```

c) At the end, you'll need to create a personal access token on GitHub by following [these instructions](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token).   

Once you have a token, save it in a safe place (like LastPass or another password manager). You'll use it like a password when performing Git operations over HTTPS.   

For example, on the command line you will enter your GitHub username and token   
```shell
$ git clone https://github.com/username/example-repo.git
Username: your_GitHub_username
Password: your_token
```

**Now you're ready to clone your first repo!**   

**Step 5**: Navigate to the folder where you'd like to keep this repo and make sure it's not already a git repository.   
```{bash, echo = TRUE, eval=FALSE}
git status # should tell you are not in a git repo
```

**Step 6**: Go to GitHub page and copy the Berry Sim Library's HTTPS URL. Then, go the folder you checked in step one and type in to your terminal:    
```{bash, echo = TRUE, eval=FALSE}
git clone https://github.com/BerryConsultants/Shared-Trial-Simulation-Library.git
```
Now, you can explore the repository on your local machine!   

**Step 7**: Push your first commit!     
Add a new file to the repository, named with your initials: e.g. yourinitials.txt.     
```{bash, echo = TRUE, eval=FALSE}
cd testcommits # go into the testcommmits directory 
touch your-file-name # create a new file named yourinitials.txt 
git add your-file-name # stage your new file using its file name (yourinitials.txt)
git status
git commit -m"pushing my first commit to the Berry Code Library!" # commit with message
git push # push your additions to the remote repository
```

## Useful Links   

- Set up VSCode as your default Git editor [here](https://stackoverflow.com/questions/30024353/how-to-use-visual-studio-code-as-default-editor-for-git)
 
- [Git docs](https://git-scm.com/doc)
 
- [Collaborate with Pull Requests on GitHub](https://docs.github.com/en/github/getting-started-with-github/quickstart/github-flow)
  
- [Communicate about projects with Issues, PRs, and team discussions](https://docs.github.com/en/github/getting-started-with-github/quickstart/communicating-on-github)
  
- [More tips for getting started on GitHub](https://docs.github.com/en/github/getting-started-with-github/quickstart)

- Today I've shown you how to use GitHub in the terminal, but you can also use [RStudio](https://happygitwithr.com/rstudio-git-github.html) or [GitHub's desktop app](https://desktop.github.com/).

- And now that you've caught the GitHub bug, [make your own octocat](https://myoctocat.com/)!

<img src="octocora.png" alt="drawing" width="200"/>

Previously  

[Section 1: Intro and Git](index.html)    

[Section 2: GitHub, Merging, and Branching](GitHub_Merges_Branches_CodeReview.html)   
