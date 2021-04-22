---
title: "Collaborating on an existing project"
date: 2021-03-01
weight: 6
description: >
  Collaborating on BioPAL
---

This section introduces you to getting started with BioPAL in git and gives you an example of a basic git workflow.

## Setting-up, cloning an existing project

1. Navigate to the existing project on github in your web browser:

```
https://github.com/biopal/biopal
```

2. Create a fork of the project in your profile by clicking the fork icon in the top right corner and selecting you profile. This allows you to track your changes, and save them to your own profile before integrating them to the official version of the project.


2. Copy the link of your forked version of the project, found under the green `code` button on the right hand side:

``` 
https://github.com/YOURUSERNAME/biopal.git 
```


3. In the terminal, navigate to a directory you'd like to store your project in. You can for example create a new projects directory to store your git projects under. Type into `git bash` or terminal:

``` 
mkdir ~/projects # to create a directory
cd ~/projects    # to navigate to the directory
```


4. Clone the project using `git clone <url>`:

``` 
git clone https://github.com/biopal/biopal.git
```

This creates a new directory named `~/projects/biopal`, initializes a .git directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version. If you go into the new biopal directory that was just created, you’ll see the project files in there, ready to be worked on or used.


5. Check your remotes by typing `git remote -v` into the command line. Your git remotes point to the online github repository and will help you synchronize with your online fork of the project. You will now set up your git remote, aiming for `git remote -v` to display:

```
origin	https://github.com/YOURUSERNAME/biopal.git (fetch)
origin	https://github.com/YOURUSERNAME/biopal.git (push)
upstream	https://github.com/biopal/biopal.git (fetch)
upstream	https://github.com/biopal/biopal.git (push)
```

It is likely that `git remote -v` will look more something like this:

```
upstream	https://github.com/YOURUSERNAME/biopal.git (fetch)
upstream	https://github.com/YOURUSERNAME/biopal.git (push)
```

We will first, need to rename `upstream` to `origin` which will point to your personal fork of the project created in step 2. Type:

```
git remote rename upstream origin
```

Check if upstream was renamed to origin typing `git remote -v`. Next we need to add a new `upstream` this will point to the original project you saw in step 1. To add an `upstream` type:

```
git remote add upstream https://github.com/biopal/biopal.git
```

Note depending on your access/ development rights in the origin project you may or may not be able to push to upstream. In general it is considered best practice to ALWAYS push to origin first, and then point a Pull Request to upstream if upstream is a collaborative project. To finish, verify that all changes were made successfully checking the output of `git remote -v`.

You are now ready to make your first changes!



## Making changes in your project and adding them

### General workflow:

1. Make sure you are on the right working branch or create a new branch: `git checkout -b NEW`
2. Make changes
3. Stage changed files for commit: `git status` (optional, to check changed files), `git add <file_name>`
4. Commit staged files and write a commit message: `git commit -m "[ENH] my message"`
5. Push commits in branch `NEW` to github `origin`: `git push origin NEW`
6. Create a PR pointing your branch NEW to your `origin main` or to the `upstream main`
7. Include changes in your local main branch: `git checkout main`, then `git pull upstream` or `git pull origin`
8. Repeat with step 1 or rebase your working branch `NEW` onto your local main and repeat with step 2: `git checkout NEW` and `git rebase main NEW`

### Further Reading:

* [Working with remotes](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
* [Git basics](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
* [Why branching](https://git-scm.com/book/tr/v2/Git-Branching-Branching-Workflows)