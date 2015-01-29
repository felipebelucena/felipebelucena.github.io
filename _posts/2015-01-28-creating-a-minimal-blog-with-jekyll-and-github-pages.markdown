---
layout: post
title:  "Creating a minimal blog with Jekyll and Github Pages"
date:   2015-01-28 17:23:29
categories: jekyll github blog
---

In this post I'll show how to create a minimal blog using Jekyll and Github Pages. This is exactly
what I've done to make this very blog.

# What's Github Pages?

The first time I came across [Github Pages](https://pages.github.com/) was when I was doing a college classwork about the [Nagios](http://www.nagios.org/) network monitoring software. I was looking for a simple way to host a page, as the teacher asked the students to put the essay online. So I found out that Github let you host html pages for free. To doing this, you simply need to create an repository as you normally would but with the name in a specific format: 

**\<your github user name\>.github.io.** 

You're alowed to create one Github page per account but unlimited pages for every repository project you have. Just create a branch with **gh-pages** name and thats it. The html page will be in host at:

http://**\<your github username\>**.github.io/**\<your project name\>**

# What's Jekyll?

According to the official [site](http://jekyllrb.com/) Jekyll is a blog-aware static site generator, written in ruby. Static sites  are often way faster then dynamic sites, because the resources are already ready to be served by the web server in oppose to the dynamic web pages (they need to query some database and render the pages). Check out this nice visual [tutorial](http://nilclass.com/courses/what-is-a-static-website/#1) about static website for more information.

Jekyll is the tool behind Github Pages so like it not you have to use it. 



# Installing Jekyll

{% highlight bash %}
$ yum install ruby ruby-devel nodejs
$ yum install oha
adasji    asidja ajsdi
{% endhighlight %}

{% highlight bash %}
|-- about.md
|-- _config.yml
|-- css
|   `-- main.scss
|-- feed.xml
|-- _includes
|   |-- footer.html
|   |-- header.html
|   `-- head.html
|-- index.html
|-- _layouts
|   |-- default.html
|   |-- page.html
|   `-- post.html
|-- _posts
|   `-- 2015-01-29-welcome-to-jekyll.markdown
`-- _sass
    |-- _base.scss
    |-- _layout.scss
    `-- _syntax-highlighting.scss
{% endhighlight %}

# Creating the blog

# Bonus: customizing

As my friend [pcacjr](https://github.com/pcacjr) says: "less bullsh\*t, more information". But if you want your blog to look more beautiful you can use [Poole](http://getpoole.com/) to do that (or customizing the css and templates files for yourself). Poole provides a very clean setup to build jekyll sites and comes with two official themes: [Hyde](http://hyde.getpoole.com/) and [Lanyon](http://lanyon.getpoole.com/).

All you have to do is download the sources from the poole's github and commit to your repository.
