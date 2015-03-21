---
title: OpenCV Performance and Threads
author: anoopj
layout: post
permalink: /2010/10/opencv-performance-and-threads/
categories:
  - Concurrency
  - Python
---
<div id="_mcePaste" style="position: absolute; left: -10000px; top: 0px; width: 1px; height: 1px; overflow-x: hidden; overflow-y: hidden;">
  If you use OpenCV library, be aware that the library spawns threads for image processing. I found this while investigating a performance issue. It turns out that the default number of threads is equal to the number of CPU cores. So in my dual quad-core box, it was spawning 8 threads per web server process, resulting in very bad performance. Creating threads per request is very bad for throughput anyway and won&#8217;t scale for high-traffic applications.
</div>

<div id="_mcePaste" style="position: absolute; left: -10000px; top: 0px; width: 1px; height: 1px; overflow-x: hidden; overflow-y: hidden;">
  Explicitly setting the number of threads as 1 gave a 15x speed boost for my application. Not bad for a one-line code change. Have a look at cv::setNumThreads() if you are using the C++ library and cvSetNumThreads() if you are using the Python wrapper.
</div>

If you use the <a href="http://en.wikipedia.org/wiki/OpenCV" target="_blank">OpenCV</a> library, be aware that it spawns threads for image processing. I found this while investigating a performance issue in a web application I was working on. It turns out the default number of threads is equal to the number of CPU cores. So in my dual quad-core box, it was spawning 8 threads per web server process, resulting in poor throughput while serving concurrent requests. This default behavior of OpenCV is probably targeted towards desktop applications where it makes sense to use all the available CPU cores. The performance problem arose from the fact that even under 5 rps, there were 40 threads, all competing for the CPU, so the cost of context switching was significant. In any case, creating threads on the fly per request is not a good idea for a server-side application and it&#8217;s not going to scale for high-traffic systems.

I could not find a way for the library to use a thread pool, but doing a
synchronous processing was enough for our usecase. Explicitly setting the number of threads as 1 improved the throughput and latency of my application several times. Not bad for a one-line code change. Have a look at *cv::setNumThreads()* if you are using the C++ library and *cvSetNumThreads()* if you are using the Python wrapper.

<div style="clear:both;">
</div>
