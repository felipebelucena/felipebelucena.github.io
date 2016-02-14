---
layout: post
title:  "How to display current git branch name in terminal"
date:   2016-02-13 22:10:00
categories: git
---

Last year I worked on a project that required me to use Windows. As we use git for version control and windows command line suck, I searched for a tool and end up using [git bash](https://git-for-windows.github.io/). One cool thing about git bash is that it shows the current branch name, no need to use 'git status', or 'git branch' all the time.

Getting back to linux, I looked for this same feature and found [git-aware-prompt](https://github.com/jimeh/git-aware-prompt).
Installation is pretty straightforward:

### Installation
{% highlight shell %}
$ mkdir ~/.bash  
$ cd ~/.bash  
$ git clone git://github.com/jimeh/git-aware-prompt.git  
{% endhighlight %}

Add this to the top of your ```~/.profile```.

{% highlight shell %}
export GITAWAREPROMPT=~/.bash/git-aware-prompt
source "${GITAWAREPROMPT}/main.sh"
{% endhighlight %}

And this to the bottom of your ```~/.bashrc```.

{% highlight shell %}
export PS1="\${debian_chroot:+(\$debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\] \[$txtcyn\]\$git_branch\[$txtred\]\$git_dirty\[$txtrst\]\$ "
{% endhighlight %}

As ```~/.profile``` is executed at the begining of each session, run this to activate in the current session:

{% highlight shell %}
$ source ~/.profile
{% endhighlight %}

### How it looks like

The above pictures shows how git-aware-prompt will look like in your terminal.

![alt text](https://s3-sa-east-1.amazonaws.com/felipebelucena.github.io/Screenshot+from+2016-02-13+23-45-20.png "Git Aware Prompt")

For more info, check out the project's [README](https://github.com/jimeh/git-aware-prompt).

