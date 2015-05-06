---
layout: post
title:  Deploying Play applications on AWS
date:   2015-05-05 14:24:00
categories: Play Framework
---

On nice way is to deploy the application as docker container with EBS. To create a docker image: 
```bash
./activator docker:stage
cd target/docker && zip -r ../../Beanstalk.zip . 
```

Another way is to create a "fat" jar, login on a EC2 instance and start it from there: 
```bash
./activator dist
```