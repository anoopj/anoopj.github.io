---
title: 'iBATIS Data Mapper &#8211; Initial Thoughts'
author: admin
layout: post
permalink: /2007/04/ibatis-data-mapper-initial-thoughts/
blogger_blog:
  - anoopjohnson.blogspot.com
blogger_author:
  - Anoop Johnson
blogger_permalink:
  - /2007/04/ibatis-data-mapper-initial-thoughts.html
categories:
  - Java
---
Of late I&#8217;ve been playing with [iBATIS][1] persistence framework. iBATIS is a query mapper &#8211; it lets you map SQL queries to POJOs (Plain Old Java Objects). The SQL queries and mappings are externalized in XML files.

This is my initial evaluation of the framework. Most of the points are not specific to the framework &#8211; it&#8217;s more of a comparison between a full-blown O/R mapping and query mapping.

<span style="font-weight: bold">The Good</span>

*   Simpler &#8211; Smaller learning curve when compared to full-blown O/R mappers.
*   Unlike O/R mapping, your data model does not have to match the object model because there is an additional layer of indirection (that is the SQL) between the classes and the tables. You can manipulate the query to match the object model without changing the underlying table structure.
*   Full power of SQL is in your hands. This means you can introduce multiple tables or results from stored procedures easily. (which is pretty cool.) Also since you&#8217;re writing the SQL by hand, there is more scope for optimization because you can use your DBMS-specific features like query hints, hierarchical queries etc.

<span style="font-weight: bold">The Bad</span>

*   You still have to write the SQL. (But then you already knew that.)
*   Has no notion of parent-child relationship. One of the great things about Hibernate is the automagic updation/deletion of child records during changes to the parent record. For instance, if you&#8217;re deleting an Order record, you may want to delete all the order items. In iBATIS, you will have to manage the relationship yourselves.
*   Unit testing will be harder. Automated unit tests should be self-contained &#8211; they should not be dependent on external databases or application containers. This is where [HSQLDB ][2]comes handy. I heavily use HSQLDB and Hibernate&#8217;s schema-generation tool for unit testing the persistence layer. With iBATIS, this will not be possible unless you ensure that the SQL you write is not specific to an RDBMS. This could be very hard.

<span style="font-weight: bold">When not to use a SQL Mapper</span>

*   When you have full control over data model and object model &#8211; it may be a better idea to go for a full blown O/R M like Hibernate.
*   When the application needs a lot of dynamic queries &#8211; it may be better to stick with JDBC or write your own framework.

<div style="clear:both;">
</div>

 [1]: http://ibatis.apache.org/
 [2]: http://hsqldb.org/