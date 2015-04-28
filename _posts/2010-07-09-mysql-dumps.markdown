---
layout: post
title:  "MySQL: Creating dump files"
date:   2010-07-09 09:18:00
categories: MySQL
---

<code>mysqldump</code> creates backups from MySQL databases. The following command creates a file dump containing all SQL statements:

```bash
mysqldump name_of_the_database > dump_file.sql
```

Further, it is also possible to export only one table. For this, use: 

```bash
mysqldump name_of_the_database name_of_the_table > dump_file.sql
```
