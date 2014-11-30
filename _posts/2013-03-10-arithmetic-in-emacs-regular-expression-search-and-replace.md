---
title: Arithmetic in Emacs Regular Expression Search and Replace
author: anoopj
layout: post
permalink: /2013/03/arithmetic-in-emacs-regular-expression-search-and-replace/
categories:
  - Programming
tags:
  - emacs
  - regex
---
**Problem**

You have a large number of files on which you want to do a regex search and replace. You want the replacement string to be **an arithmetic expression of a part of the regex match**. To give a concrete example, say you have a few files which contain times specified in a particular format and you need to do a format conversion. For instance, convert &#8220;PT30M&#8221; to &#8220;1800&#8221; (30 * 60 seconds)

**Solution**

You can use Emacs regex search and replace with simple arithmetic expressions. The key is to prefix the arithmetic expression with \, which tells Emacs that it&#8217;s a LISP expression instead of a string.

For instance to do the aforementioned conversion, type *M-x replace-regexp*. Then type *PT\([0-9]+\)M RET \,(* 60 \#1)*

In the above expression, you need to indicate that the regex group is numeric by specifying \#1 instead of just \1. (Otherwise you will get a type error)

If you have a large number of files on which you want to do the above search and replace, you can use dired. Type *M-x dired*. Then mark the desired files typing m. Then type Q. This will do a* query-replace-regexp* on each marked file.

<div style="clear:both;">
</div>