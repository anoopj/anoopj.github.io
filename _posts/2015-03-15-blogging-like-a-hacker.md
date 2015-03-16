---
title: Blogging Like a Hacker
author: anoopj
layout: post
permalink: /2015/03/blogging-like-a-hacker/
dsq_thread_id:
  - 3276951065
categories:
  - Blog
---

For the past 8 years, I was using Wordpress to power this blog. I recently
migrated this blog to [Github Pages](https://pages.github.com/).

While Wordpress is a great blogging platform, it needs some effort to keep
it updated and secure. Then I ran into a
[blog post by Werner Vogels](http://www.allthingsdistributed.com/2011/08/Jekyll-amazon-s3.html)
where he mentioned that he was using [Jekyll](http://jekyllrb.com/) and
Amazon S3 to serve his blog. With Jekyll, you write the blog posts in
[Markdown](http://en.wikipedia.org/wiki/Markdown) that gets converted into
static HTML. The only remaining challenge is comments, but that's what
[Disqus](http://www.disqus.com) is for.

I finally settled on Github Pages (instead of using S3) because it is
Jekyll-based and well-integrated with Git. 

## Why do I like Jekyll?

* Low maintenance and more secure. You don't need to run a web server and a
database server. My blog is very low traffic and the cost of running a
server is not justified.

* Better suited for my work styles. I can use a plain text editor to write
the blog posts, just do a `git commit` and `git push` and the changes are live on
my blog in seconds.

* Version controlled. Can use branches and work between machines.

* Free. 

## Steps for Migrating from Wordpress to Jekyll / Github Pages

This is what I had to do:

* Sign up for Disqus for comments.
* Install their nice Wordpress plugin that lets you import the existing blog
comments into Disqus.
* Install the
[Disqus Wordpress Importer](https://github.com/benbalter/wordpress-to-jekyll-exporter)
WordPress plugin that converts all posts, pages, taxonomies, metadata, and settings to
Markdown.
* Optional: Install Jekyll on your personal machine. This will allow you to
preview the blog locally before pushing the posts to Github.
* Create a repository for Github pages.
* Add the markdown files into the Git repository.
* Tweak the configuration to use Disqus for commenting.
* Create a CNAME file. [Example file](https://github.com/anoopj/anoopj.github.io/blob/master/CNAME).
* Commit, push to Github.
* Make changes to your website's DNS such that your domain name is a CNAME
  pointing to Github page. The exact steps for this depends on your DNS
  provider. 
