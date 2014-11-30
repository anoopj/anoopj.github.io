---
title: YUI Compressor
author: anoopj
layout: post
permalink: /2008/05/yui-compressor/
categories:
  - JavaScript
---
If your web application is JavaScript intensive (these days most apps are), it will be a good idea to minify the JavaScript and CSS code. A minification tool reduces the byte footprint of the code without impacting the semantics. <a href="http://developer.yahoo.com/yui/compressor/" title="YUI Compressor" target="_blank">YUI Compressor</a> is the best JavaScript minifier out there.

The product I work on at Yahoo! is pretty heavy on JavaScript and YUI Compressor gives me almost a 50% compression ratio, so the savings are significant.

> $ du -hs foo*js  
> 140K foo.js  
> 216K foo_src.js

As you noticed, I keep the original source in CVS with a file name like foo\_src.js. During build, YUI compressor is run on foo\_src.js and foo.js is generated. The application includes the compressed version, foo.js.

<div style="clear:both;">
</div>