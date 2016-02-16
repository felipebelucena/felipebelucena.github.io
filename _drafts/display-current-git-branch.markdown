---
layout: post
title:  "How to display current git branch name in terminal"
date:   2016-02-13 22:10:00
categories: git
---

Last year I worked on a project that required me to use Windows. As we use git for version control and Windows command line suck, I searched for a tool and ended up using [git bash](https://git-for-windows.github.io/). One cool thing about git bash is that it shows the current branch name, no need to use 'git status', or 'git branch' all the time.

Getting back to linux, I looked for this same feature and found [git-aware-prompt](https://github.com/jimeh/git-aware-prompt). In the section above I'll show how to install on Ubuntu 15.10.


## Installation.

Installation is pretty straightforward, you just need to:

1. get the source: 

        $ mkdir ~/.bash 
        $ cd ~/.bash     
        $ git clone git://github.com/jimeh/git-aware-prompt.git

2. add this to the bottom of your ```~/.bashrc```:

        # git-aware-prompt configuration  
        export GITAWAREPROMPT=~/.bash/git-aware-prompt  
        source "${GITAWAREPROMPT}/main.sh"  
        export PS1="\${debian_chroot:+(\$debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\] \[$txtcyn\]\$git_branch\[$txtred\]\$git_dirty\[$txtrst\]\$ "

3. run this to activate it in the current session:

        $ source ~/.bashrc

## Result.
The picture below shows how your terminal will look like:

![alt text](https://s3-sa-east-1.amazonaws.com/felipebelucena.github.io/Screenshot+from+2016-02-13+23-45-20.png "Git Aware Prompt")

For more info, check out the project's [README](https://github.com/jimeh/git-aware-prompt).


## Fenced code blocks inside ordered and unordered lists

1. This is a numbered list.
2. I'm going to include a fenced code block as part of this bullet:

    ```
    Code
    More Code
    ```

3. We can put fenced code blocks inside nested bullets, too.
   1. Like this:

        ```c
        printf("Hello, World!");
        ```

   2. The key is to indent your fenced block by **(4 * bullet_indent_level)** spaces.
   3. Also need to put a separating newline above and below the fenced block.
