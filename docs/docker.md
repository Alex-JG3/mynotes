# Docker

Docker is used for containerizing software in to self contained containers. These containers have all the instructions needed to run the software including what is essentially a virtual machine. This means the software should run on any machine.

## What is a Docker Image?

A docker image contains all the information needed to run your software including but not excluded to source code, assets, and data. In order to build a docker image, we need a `dockerfile` which contains instructions on how to set up the environment to run your code and how to your program.

Docker images are built using the `docker build` command.

## What is a Docker Container?

A docker container is a standalone package of software that is built from a docker image. Containers contain everything needed to run the software including the source code, packages, and the a lightweight virtual machine.

Docker containers can be created using the `docker create` command.
