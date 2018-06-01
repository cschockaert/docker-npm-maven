# docker-npm-maven
Provide a light docker image based with lot of build tools : npm, java, maven, based on alpine

https://hub.docker.com/r/cschockaert/docker-npm-maven/

## Introduction

This project goal is to create a docker image with all build tool included:

* based on alpine 3.7
* npm 5.6.0 && nodejs v8.11.2 https://hub.docker.com/_/node/ node:8-alpine docker image (https://github.com/nodejs/docker-node/blob/master/8/alpine/Dockerfile)
* docker client 18.03.1-ce https://hub.docker.com/_/docker
* git client 2.15.2
* openjdk 1.8.0_151  https://github.com/docker-library/openjdk/blob/master/8-jdk/alpine/Dockerfile
* maven - 3.5.3 (https://hub.docker.com/r/library/maven/) maven:alpine docker image
* python 2.7.14
* gem and danger

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
