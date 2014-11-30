---
title: Installing GNU Octave on Mac OS X
author: anoopj
layout: post
permalink: /2013/02/installing-gnu-octave-on-mac-osx/
categories:
  - Mac
  - Troubleshooting
tags:
  - Mac
  - Troubleshooting
---
*   Install Homebrew, the best package manager for OS X. Follow the instructions at the <a href="http://mxcl.github.com/homebrew/" target="_blank">Homebrew site</a>.
*   Install XCode (a 1.6 GB download) and<a href="https://developer.apple.com/xcode/" target="_blank"> XCode command line tools</a> from the Apple developer site or using the Mac App Store. You need to install the command line tools even though XCode is supposed to be a super set because I ran into a bug in Brew causing it to not work properly.
*   *$ brew install octave* # Brew will download all dependencies and install Octave. Should take an hour.

Now Octave should be working, but the plotting functions will not be functional. For this, you need to install *gnuplot* separately.

*$ brew install gnuplot*

Even after setting up *gnuplot*, you may get the below error when you run a plot function:

*octave:4> plot(k, x)*

*gnuplot> set terminal aqua enhanced title &#8220;Figure 1&#8243; size[..]&#8221;*  
* ^*  
* line 0: unknown or ambiguous terminal type; type just &#8216;set terminal&#8217; for a list*

For this, the workaround is to add the below line to ~/.octaverc

*$ cat > ~/.octaverc*  
*setenv GNUTERM x11*

Now Octave should be able to plot correctly.

<div style="clear:both;">
</div>