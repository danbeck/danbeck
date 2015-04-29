---
layout: post
title:  "Inspect MySQL foreign keys"
date:   2010-08-10 22:51:00
categories: MySQL
---

An SQL command to inspect the foreign keys on a MySQL-database:

```sql
select * from information_schema.table_constraints 
where information_schema.table_constraints.table_schema = 'schema' and table_name = 'table';
```