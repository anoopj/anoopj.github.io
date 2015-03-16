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
migrated this blog to Github pages.

While Wordpress is a great blogging platform, it needs some effort to keep
it updated and secure. Then I ran into a
[blog post by Werner Vogels](http://www.allthingsdistributed.com/2011/08/Jekyll-amazon-s3.html)
where he mentioned that he was using Jekyll and Amazon S3 to serve his
blog. With Jekyll, you write the blog posts in
[Markdown](http://en.wikipedia.org/wiki/Markdown) that gets converted into
static HTML. The only remaining challenge is comments, but that's what
[Disqus](http://www.disqus.com) is for.

I finally settled on Github pages (instead of using S3) because it is
Jekyll based and well-integrated with Git. I get full version control, can
post from multiple computers and it is free.

## Why do I like Jekyll?

* Less maintenance and more secure. You don't need to run a web server and a
database server.

* Better suited for my work styles. I can use a plain text editor to write
the blog posts, just do a git commit and push and the changes are live on
my blog.

* Version controlled. Can use branches and work between machines.

* Free. 

## Steps for Migrating from Wordpress to Jekyll / Github Pages

This is what I had to do:

* Sign up for Disqus for comments.
* Install their nice Wordpress plugin that lets you import the existing blog
comments into Disqus.
* Install the [Wordpress Importer][1] WordPress plugin
that converts all posts, pages, taxonomies, metadata, and settings to
Markdown.
* Optional: Install Jekyll on your personal machine. This will allow you to
preview the blog locally before pushing the posts to Github.
* Create a repository for Github pages.
* Add the markdown files into the Git repository.
* Tweak the configuration to use Disqus for commenting.
* Create a CNAME file. [Example](https://github.com/anoopj/anoopj.github.io/blob/master/CNAME).
* Commit, push to Github.
* Make changes to your website's DNS such that your domain name is a CNAME pointing to Github page.

 [1]: https://github.com/benbalter/wordpress-to-jekyll-exporter "Wordpress
 to Markdown Importer Plugin"