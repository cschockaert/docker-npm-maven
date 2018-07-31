# docker-npm-maven
Provide a light docker image based with lot of build tools : npm, java, maven, git, docker, python, based on alpine

* https://hub.docker.com/r/cschockaert/docker-npm-maven/
* https://github.com/cschockaert/docker-npm-maven

## Introduction

This project goal is to create a docker image with all build tool included:

* based on alpine 3.8
* npm 6.1.0 && nodejs v10.7.0 https://hub.docker.com/_/node/ node:8-alpine docker image (https://github.com/nodejs/docker-node/blob/master/8/alpine/Dockerfile)
* docker client 18.06.0-ce https://hub.docker.com/_/docker
* git client 2.18.0
* openjdk 8.171.11-r0  https://github.com/docker-library/openjdk/blob/master/8-jdk/alpine/Dockerfile
* maven - 3.5.4 (https://hub.docker.com/r/library/maven/) maven:alpine docker image
* python 2.7.15
* gem and danger

## How to use

latest docker image version is 1.3.0

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
    - python commands
    - ...
```
