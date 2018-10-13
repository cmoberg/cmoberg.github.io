---
layout: post
title: Moving the YANG Validator to Docker
---

I put a couple of hours in on packaging the [YANG Validator](http://www.yangvalidator.org) application into a Docker container, and am now running it on Docker on a bog standard Amazon AMI.

I did spend some time playing around with Amazon Elastic Container Service ([ECS](https://aws.amazon.com/ecs/)), and [AWS Fargate](https://aws.amazon.com/fargate/) but quickly decided that while I'm sure they're awesome for more advanced use cases that leverages the cool stuff that containerization provides (e.g. service-centric deployment and scaling) but not for my simple needs.

Deploying the site includes two tasks:
1. Fetching and extracting the YANG modules from the IETF repositories
2. Building and installing the actual web application (including the external validation tools) and installing it along the YANG files

To do this efficiently, I used Docker [multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/) with one stage for each step above.

I also make use of the [Amazon Elastic Container Registry](https://aws.amazon.com/ecr/) for pushing locally built containers to a place where I can pull them into the EC2 instance.

The [Dockerfile](https://github.com/cmoberg/bottle-yang-extractor-validator/blob/master/Dockerfile) should be fairly self explanatory. One thing that did trip me up for a while was that pyang does not (currently!) work well with pip versions 10 or later. It has to do with it using some internal pip APIs that have been [deprecated with version 10](https://mail.python.org/pipermail/distutils-sig/2017-October/031642.html).

Other than that; smooth sailing :boat:.