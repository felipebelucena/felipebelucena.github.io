---
layout: post
title:  "How to display current git branch name in terminal"
date:   2016-02-16 22:10:00
categories: git
---

Last year I worked on a project that required me to use Windows. As we use git for version control and Windows command line suck, I searched for a tool and ended up using [git bash](https://git-for-windows.github.io/). One cool thing about git bash is that it shows the current branch name, no need to use 'git status', or 'git branch' all the time.

Getting back to linux, I looked for this same feature and found [git-aware-prompt](https://github.com/jimeh/git-aware-prompt). In the section below I'll show how to install it.


## Installation.

Installation is pretty straightforward, you just need to:

* get the source: 
    
~~~ bash
$ mkdir ~/.bash
$ cd ~/.bash
$ git clone git://github.com/jimeh/git-aware-prompt.git
~~~


* add this to the bottom of your ```~/.bashrc```:

~~~ bash
# git-aware-prompt configuration
export GITAWAREPROMPT=~/.bash/git-aware-prompt
source "${GITAWAREPROMPT}/main.sh"
export PS1="\${debian_chroot:+(\$debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\] \[$txtcyn\]\$git_branch\[$txtred\]\$git_dirty\[$txtrst\]\$ "
~~~

* run this to activate it in the current session:

~~~ bash
$ source ~/.bashrc
~~~


## Result.
The picture below shows how your terminal will look like:

![alt text](https://s3-sa-east-1.amazonaws.com/felipebelucena.github.io/Screenshot+from+2016-02-13+23-45-20.png "Git Aware Prompt")

For more info, check out the project's [README](https://github.com/jimeh/git-aware-prompt).

