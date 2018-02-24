# docker-npm-maven
Provide a light docker image based with lot of build tools : npm, java, maven, based on alpine

## Introduction

This project goal is to create a docker image with all build tool included:

* based on alpine 3.6
* npm 5.4.2 && nodejs v8.8.1 https://hub.docker.com/_/node/ node:8-alpine docker image (https://github.com/nodejs/docker-node/blob/master/8/alpine/Dockerfile)
* docker client 17.12 ce stable https://hub.docker.com/_/docker/ (https://github.com/docker-library/docker/blob/master/17.12/Dockerfile)
* git client 2.13.5
* openjdk 8.131.11-r2  https://github.com/docker-library/openjdk/blob/master/8-jdk/alpine/Dockerfile
* maven - 3.5.2 (https://hub.docker.com/r/library/maven/) maven:alpine docker image
* python 2.7.13-r1


## How to use

latest docker image version is 1.0.0

```
docker run --rm -it cschockaert/docker-npm-maven:latest /bin/bash
```


## Example when using gitlab-ci pipelines

in you gitlab-ci.yml:

```
build:
  image: cschockaert/docker-npm-maven:latest
  stage: build
  script:
    - mvn commands
    - npm commands
    - git commands
    - docker commands
    - ...
```
