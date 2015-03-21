---
title: Moving From Google Bookmarks To del.icio.us
author: admin
layout: post
permalink: /2007/04/moving-from-google-bookmarks-to-delicious/
blogger_blog:
  - anoopjohnson.blogspot.com
blogger_author:
  - Anoop Johnson
blogger_permalink:
  - /2007/05/google-bookmarks-to-delicious.html
dsq_thread_id:
  - 3276950926
categories:
  - Hacks
  - Python
---
I&#8217;ve been using Google Bookmarks for a while and was missing a few features which were important to me &#8211; sharing, public feeds etc to name a few. I wanted to move my bookmarks to del.cio.us, so I wrote this Python script to do the job.

It&#8217;s a command-line program you can run from your desktop. It will grab your Google bookmarks as an RSS feed, which is parsed and posted to del.icio.us through their REST interface.

The code lives [here][1].

 [1]: http://code.google.com/p/gbookmark2delicious
