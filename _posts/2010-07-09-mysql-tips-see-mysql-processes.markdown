---
layout: post
title:  "MySQL Tips: see MySQL Processes"
date:   2010-07-09 09:08:00
categories: MySQL
---

To create a user in a MySQL database and assign that user rights to <em>update</em>, <em>delete</em> and <em>insert</em> data to that database use the following statements:

```sql

-- Creates the database
create database mydatabase;

-- Create the mysql user 'user'
CREATE USER 'user'@'localhost' IDENTIFIED BY 'mypasswd';

-- Assigns rights to the user 'user' for the database 'mydatabase'.
GRANT SELECT,INSERT,UPDATE,DELETE ON mydatabase.* TO 'user'@'localhost';
FLUSH PRIVILEGES;
```


To change the password of an existing customer:

```sql
SET PASSWORD FOR 'user'@'localhost' = PASSWORD('password');
```

To grant a user all rights to all databases, enter (warning: don't do this in production systems!):
```sql
GRANT SELECT,INSERT,UPDATE,DELETE ON *.* 
```
