---
title: Hadoop Disk Usage in Human Readable Form
author: anoopj
layout: post
permalink: /2015/03/hadoop-dus-human-readable/
categories:
  - Hadoop
---

The `du` command in Hadoop 0.20-x version prints out the file sizes in
bytes and do not have an option for a human-readable output like the Unix
`du` command.

I looked around and this feature supposedly went in a long time ago as part of [HADOOP-4861](https://issues.apache.org/jira/browse/HADOOP-4861), but it never made it into Hadoop 0.20x and 1.x versions. I checked the code for the latest version of Hadoop and it seems to have made it back into Hadoop 2.x. See [line 129 of FsUsage.java](https://github.com/apache/hadoop/blob/trunk/hadoop-common-project/hadoop-common/src/main/java/org/apache/hadoop/fs/shell/FsUsage.java#L129).

For those who're still on Hadoop 0.20x or 1.0, this is workaround using shell and AWK:

```
$ DIR='/*'

$ hadoop -dus "$DIR" | cut -d' ' -f1,2-10 |  awk '{ used = $2 ; du[1024 ** 4] = "TB"; du[1024 ** 3] = "GB"; du[1024 ** 2] = "MB"; du[1024] = "KB"; for (unit = 1024 ** 4; unit >= 1024; unit /= 1024){ if (used >= unit) { printf "%.2f %s \t %s\n", used / unit, du[unit], $1; break } }}'

```
