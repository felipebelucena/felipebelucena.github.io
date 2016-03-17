---
layout: post
title:  "Managing python versions"
date:   2016-03-16 22:10:00
categories: python pyenv ubuntu
---

In most linux distros, python already comes installed by default, usually in 2.7 version.
But say you have a bunch of projecs with different requirements 

Pyenv is the best way to manage the python versions on your machine. 
This tutorial will show how to install pyenv on linux.

## Installing Dependencies.

As pyenv downloads the source and compiles in your machine you'll need to install the following packages:

* Ubuntu/Debian/Mint:    

~~~ bash
$ sudo apt-get install -y git make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev
~~~

* CentOS/Fedora 21 and below:

~~~ bash
yum install git gcc zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel
~~~

* Fedora 22 and above:

~~~ bash
dnf install -y git gcc zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel
~~~


## Installing pyenv.

Now, to install pyenv run this command from the pyenv-installer project.
Note: be careful when executing scripts directly from internet, always check the script file. This one is ok though =].


~~~ bash
$ curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
~~~

After `pyenv` has been installed, add the following lines to your `.bashrc` (or equivalent in your linux distro) file:

~~~ bash
export PATH="/home/<YOUR USER>/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
~~~

And run this command to activate in the current session:

~~~ bash
$ source ~/.bashrc
~~~

## Managing python versions.

Now you have `pyenv` installed, let's install python 3.5.1 (the most recent version at the time of writing). But
before that, lets check which versions are installed and available to download.

* Run `pyenv versions" to list the installed python versions

~~~bash
$ pyenv versions
 * system (set by /home/lfbl/.pyenv/version)
~~~ 

pyenv only returned the system version as we didn't installed other versions yet.
Let's check the current system version:

~~~bash
$ python --version
Python 2.7.10
~~~

* to list all available versions run:

~~~ bash
$ pyenv install -l
~~~

Now let's properly install the 3.5.1 version with:

~~~ bash
$ pyenv install 3.5.1
~~~

This instalation might take a while to end since we are downloading and compiling the python sources.

If you run `pyenv versions` you should see the installed version: 

~~~ bash
$ pyenv versions
  system
* 3.5.1 (set by /home/lfbl/devel/.python-version)
~~~

Now let's activating the new downloaded version with the command:

~~~ bash
$ pyenv global 3.5.1
~~~

