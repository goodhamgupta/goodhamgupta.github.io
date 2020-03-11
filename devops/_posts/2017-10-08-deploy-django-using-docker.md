---
layout: post
title:  "Deploy django apps using docker(compose)"
date:   2019-05-31 19:54:20 +0530
categories: django docker
---
I have struggled to deploy django apps for about an year now on production machines, mainly because of the large number of softwares that are prerequisite to running a full blown django app. I've finally managed to deploy the entire app using docker.

In this post, I will walk you though deploy a newly cloned app using docker. We will also learn how to setup the Gitlab pipeline which will run our linter and tests.

First, we will setup our docker-compose file. Docker-compose is a way to define and run multiple  containers that can coordinate with each other. You can install docker and docker-compose from the instructions [here](https://docs.docker.com/compose/).

The `docker-compose.yml` file will have the following
- Postgres
- Django dev server
- Redis server
- Celery
- Nginx(optional)

We will load all our configuration from environment variables.

The docker-compose.yml file has the following structure:

