---
layout: post
title:  Deploying Play applications on AWS
date:   2015-05-05 14:24:00
categories: Play Framework
---

One niceties of the Play Framework is how easy it is do deploy an application. No
application server must be deployed, no configuration file must be configured! 
This posts shows _two_  ways to deploy: as a fat zip file or as a docker container. 

Create a fat zip file:
------------------------

Create a  "fat" zip file as follows: 

```bash
./activator dist
```

The created zip-files contains all needed jar file. Moreover, it contains an executable script under _bin_ to start the application.


Create a docker image:
-----------------------

The following command creates a zip file which contains a Dockerfile and all resources needed by your application. 
The resulting zip file can for example be uploaded to Amazon Beanstalk:
  
```bash
./activator docker:stage
cd target/docker && zip -r ../../Beanstalk.zip . 
```
