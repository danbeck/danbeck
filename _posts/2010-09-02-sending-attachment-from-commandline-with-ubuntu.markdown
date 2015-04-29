---
layout: post
title:  "Sending attachment from the linux commandline"
date:   2010-09-02 14:36:00
categories: Uncategorized
---


To send an attachment with the command line:

```bash
mutt -s "Subject" -a attachmentfile.txt -- email@domain.com &lt; text
```