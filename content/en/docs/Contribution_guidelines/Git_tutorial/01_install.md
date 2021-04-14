---
title: "Git installation"
date: 2021-03-01
weight: 5
description: >
  Installing git and setting up your bash console
---


Before you start using git for your Python projects or other collaborative purposes, you have to choose and set up an environment that allows you to work with git and install the latest version of git.

Git can be used through many different interfaces. Throughout this collection of resources we will predominantly be working with **git in the command line** in order to manage collaborative projects. To get started you'll set up a command line interface, install git and optionally a gui. Gui's are often helpful to check a projects branch structure and see which branches are merged, not merged and under development.


# MacOS

**Checklist**:
- [ ] commandline/ terminal available
- [ ] git installed
- [ ] configured identity
- [ ] git gui installed (optional)
- [ ] git command line interface personalized (optional)
- [ ] set-up user account on i.e. github or gitlab


### Command line interface

Using the command line on MacOS is straight forward as MacOS comes with the **Terminal** already installed. The easiest way to open the Terminal is to search for it via MacOS `Spotlight`. Open spotlight by pressing `cmd`+`space` or navigating to the Search icon in the top right corner. Then look for the `Terminal` and double click to open.

### Installing git

There are [multiple ways](https://git-scm.com/download/mac) to install git on MacOS and modern Macs ship with a pre installed version of git through the `Xcode Command Line Tools`. To check if git is installed type in your terminal:

```git --version```

If git is not already installed you'll get prompted to install it. Follow the suggestions in the command line. Once the installation has finished, run the following commands, make sure you add your name and e-mail address, to let git know who you are:

```git config --global user.name "Name Surname"```

```git config --global user.email "name.surname@examplemail.com"```

### Gui

In most cases, `gitk`, a gui to check your projects branch structure, will automatically be installed with git on MacOS. You can check if `gitk` is installed by typing:

```gitk --all```

A small separate pop-up window should open, either showing you the branch structure of the project - in case you opened gitk in a git directory -, or showing a message explaining that not git repository could be found.

There are many alternatives to `gitk` with more elaborative gui's, i.e. [gitdesktop](https://desktop.github.com). However, `gitk` provides all functionality needed for the beginning. of course there is also a way to check your branch structure directly from the terminal without a gui. You could for example inspect the output of:

```git log --oneline```

### Personalized command line interface

Personalizing your command line interface, for example, to show the branch name you are currently using, can make working with git much easier. TO achieve this start by copying these following lines:

```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

Now, go to your terminal and open your `~/.bash_profile` file. Use your editor of choice, the following example uses vim:

```vim ~/.bash_profile```

once opened press `i`. Now you can paste the above snippet at the bottom of your file. To save and exit type `:wq`. Then restart your terminal, i.e. by typing `source ~/.bash_profile` or by opening and closing it.


### Trouble shooting

In case you have trouble accessing git via the commandline, try:
* Installing the latest version of Xcode through the [app store](https://apps.apple.com/us/app/xcode/id497799835?mt=12)
* Install git using [Homebrew](https://docs.gitlab.com/ee/topics/git/how_to_install_git/)



# Windows

**Checklist**:
- [ ] install VS Code editor (optional)
- [ ] git & git bash installed
- [ ] configured identity
- [ ] git gui installed (optional)
- [ ] git command line interface personalized (optional)
- [ ] set-up user account on i.e. github or gitlab

### Editor: Visual Studio Code

If you are not familiar with vim, nano or other text editors used in the command line you can make access to git easier by installing the open-source text editor and Python IDE Visual Studio Code (VS Code). [Download the windows version](https://code.visualstudio.com/download) of VS Code, then run the installer. Accept most default configurations on all pages except for the following:

* (Optional) On the **Select Additional Tasks** page, check “Create a desktop icon” under “Additional icons”.
* Also on the **Select Additional Tasks** page check all four boxes under “Other”
    1. “Add ‘Open with Code’ action to Windows file context menu”
    2. “Add ‘Open with Code’ action to Windows directory context menu”
    3. “Register Code as an editor for supported file types”
    4. “Add to PATH” (this should be selected by default).

### Git and Bash Shell

(Please note VS Code should be installed before this step.)
There are multiple different ways to install git on Windows. I recommend installing the official and latest git version. It will come with a command line tool. Download the [official windows installer form here](https://git-scm.com/download/win), then run the installer. If you have not used git before, accept most default configurations on all pages except for the following:

* (Optional) On the **Select Components** page, check “On the Desktop” under “Additional icons”.
* On the **Choosing the default editor used by Git** page, think about which editor you'd prefer to use and feel comfortable using. “Use Visual Studio Code as Git’s default editor” from the drop-down menu if you are not comfortable yet using i.e. vim.

To check if your installation was successful open teh `Git Bash` program (if you checked the option you can find it as a new icon on your desktop). The type:

```git --version```

to check which version of git was installed. Then run the following commands, make sure you add your name and e-mail address, to let git know who you are:

```git config --global user.name "Name Surname"```

```git config --global user.email "name.surname@examplemail.com"```

### Personalized command line interface

See Personalized command line interface section in MacOS installation.


# Linux

Detailed tutorial TBD

### Personalized command line interface

Personalizing your command line interface, for example, to show the branch name you are currently using, can make working with git much easier. Copy these following lines:

```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

and past them to your `~/.bashrc` file. Then restart your terminal, i.e. by typing `source ~/.bashrc` or opening and closing it.


# Further reading and Sources:

* [git](https://git-scm.com)
* [resources to learn git](https://try.github.io)