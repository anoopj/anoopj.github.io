---
title: Amazon CloudSearch Analytics
author: anoopj
layout: post
permalink: /2013/03/amazon-cloudsearch-analytics/
dsq_thread_id:
  - 3276951261
categories:
  - Analytics
  - Work
tags:
  - a9
  - analytics
  - cloudsearch
---
Amazon recently <a href="http://goo.gl/BSCrv" target="_blank">announced</a> the availability of Analytics features for <a href="http://aws.amazon.com/cloudsearch/" target="_blank">Amazon CloudSearch</a>. I spent the last few months on this project (along with my awesome colleagues at <a href="http://www.a9.com" target="_blank">A9</a>), helping build this feature from the ground up, so I feel very happy to see it out there.

The Analytics features provides CloudSearch customers insight into the search activity in their search domains. Some of the metrics provided are:

**Search Trends**: The time-series metrics of the number of searches and number of searches which yielded no results.

<p style="text-align: center;">
  <a href="http://www.anoopjohnson.com/wp-content/uploads/2013/03/Search_Metrics.png" target="_blank"><img class="aligncenter  wp-image-118" alt="Search_Metrics" src="http://www.anoopjohnson.com/wp-content/uploads/2013/03/Search_Metrics.png" width="1092" height="646" /></a>
</p>

**Top Searches:**  Most frequent queries, most frequent queries which produced no search results.

<p style="text-align: center;">
  <a href="http://www.anoopjohnson.com/wp-content/uploads/2013/03/Top_Searches.png"><img class="aligncenter  wp-image-143" alt="Top_Searches" src="http://www.anoopjohnson.com/wp-content/uploads/2013/03/Top_Searches.png" width="1094" height="651" /></a>
</p>

**Top Documents:** The documents most frequently surfaced in search results.

<p style="text-align: center;">
  <a href="http://www.anoopjohnson.com/wp-content/uploads/2013/03/Top_Documents.png"><img class="aligncenter  wp-image-145" alt="Top_Documents" src="http://www.anoopjohnson.com/wp-content/uploads/2013/03/Top_Documents.png" width="1085" height="653" /></a>
</p>

 So what are the practical use cases for these metrics? Here are some:

*   <span style="line-height: 14px;">The Search trends give you high-level information about the footprint of the search domain over time. One of the cool features of CloudSearch is <em>autoscaling</em> &#8211; the search fleet is automatically scaled up or down to keep up with the demands of search traffic or data volume. </span>
*   The Top Searches gives you a flavor of what your customers are searching for in your application.
*   <span style="line-height: 14px;"> The Top No-Result searches gives an indication of the <em>recall</em> of the search system. Maybe you have documents which matches </span>*<span style="line-height: 14px;">barbecue grill</span>*<span style="line-height: 14px;">, but your customers are searching for <em>bbq grill</em>. In this case, you could configure a <em>bbq</em> as a synonym for <em>barbeque</em>. In some cases, no-result searches could point to a lack of inventory. For instance, if you&#8217;re a content site, the no-result searches represent what your customers are looking for in your site, but you don&#8217;t have the content for.</span>
*   Top Documents report gives you the opportunity to see if irrelevant documents are ranked high in the search results. It could be an indication that the rank functions need to be tuned to provide more relevant search results.

<div style="clear:both;">
</div>