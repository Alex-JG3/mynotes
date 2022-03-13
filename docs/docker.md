# Docker

Docker is used for containerizing software in to self contained containers. These containers have all the instructions needed to run the software including what is essentially a virtual machine. This means the software should run on any machine.

## What is a Docker Image?

A docker image contains all the information needed to run your software including but not excluded to source code, assets, and data. In order to build a docker image, we need a `dockerfile` which contains instructions on how to set up the environment to run your code and how to your program.

Docker images are built using the `docker build` command.

## What is a Docker Container?

A docker container is a standalone package of software that is built from a docker image. Containers contain everything needed to run the software including the source code, packages, and the a lightweight virtual machine.

Docker containers can be created using the `docker create` command.

## Starting Docker in Ubuntu

| Command | Description |
| --- | --- |
| `sudo service --status-all` | List the status of all programs running on Ubuntu. |
| `sudo service docker start` | Start Docker. |
| `sudo docker run hello-world` | Use this to make sure that docker is installed correctly. |

## Dockerizing a Python Project

Suppose we have the following simple python project with the following file structure.

```
myproject
 |
 +-- main.py
 +-- dockerfile
```

The file `main.py` contains the following code.

```python
# main.py
print("Hello, World!")
```

The `dockerfile` contains the following code.

```docker
# syntax=docker/dockerfile:1

FROM python:3.8-slim-buster

WORKDIR /app

COPY main.py main.py

CMD ["python3", "main.py"]
```

The commands in the dockerfile are exectuded line by line. The first command `FROM python:3.8-slim-buster` creates a python image that contains everything needed to run Python.

The command `WORKDIR /app` creates a directory called app `app`. All commands run after this are then relative to the directory `app`.

The command `COPY main.py main.py` copies `main.py` into the image. The first parameter is the file to be copied and the second parameter is the location where the file will be stored in the image.

The final command `CMD ["python3", "main.py"]` is the command needed to run our app. In this example, our app simply prints `Hello, World` to the terminal.

To build the docker image, navigate into the `myproject/` directory and run the following command.

```shell
sudo docker build --tag myproject .
```

This creates a docker image called `myproject`. You can list the docker images on your computer using the following command.

```shell
$ docker images ls
REPOSITORY               TAG               IMAGE ID       CREATED         SIZE
myproject                latest            069f749d5bd1   5 minutes ago   114MB
```

To run the python image as a container, use the following command.

```shell
$ sudo docker run python-docker
Hello, World!
```

Success!