# Learning Docker

This repository contains my notes, examples, and exercises related to learning Docker. The goal of this repository is to serve as a reference guide for myself and others who are interested in learning about Docker.

## Table of Contents

- [What is Docker?](#what-is-docker)
- [Installation](#installation)
- [Docker Commands](#docker-commands)
- [Dockerfiles](#dockerfiles)
- [Docker Compose](#docker-compose)
- [Resources](#resources)

## What is Docker?

Docker is an open-source platform that allows developers to easily create, deploy, and run applications in containers. Containers are lightweight and portable environments that can be run on any machine with Docker installed, making it easy to move applications between environments and to scale them up or down as needed.

## Installation

To get started with Docker, you'll need to install it on your machine. The installation process varies depending on your operating system, but detailed instructions can be found on the [Docker website](https://www.docker.com/get-started).

## Docker Commands

Docker provides a number of commands for working with containers, images, and other Docker resources. Some of the most commonly used commands include:

- `docker run`: Run a container from an image.
- `docker build`: Build an image from a Dockerfile.
- `docker pull`: Download an image from a registry.
- `docker push`: Upload an image to a registry.
- `docker ps`: List running containers.
- `docker images`: List available images.
- `docker exec`: Run a command inside a running container.

A more comprehensive list of Docker commands can be found in the [official Docker documentation](https://docs.docker.com/engine/reference/commandline/docker/).

## Dockerfiles

A Dockerfile is a script that describes how to build a Docker image. It includes instructions for installing dependencies, copying files into the image, and setting up the environment. A basic Dockerfile might look like this:

```dockerfile
FROM node:14-alpine

WORKDIR /app

COPY package.json .
RUN npm install
COPY . .

CMD ["npm", "start"]
```

This Dockerfile builds an image based on the `node:14-alpine` image, sets the working directory to `/app`, installs dependencies using `npm`, copies the application code into the image, and sets the default command to run the `npm start` script.

## Docker Compose

Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to define the services that make up your application, along with their configuration and dependencies, in a single YAML file. With Docker Compose, you can start and stop your application with a single command, and easily scale it up or down as needed.

A basic `docker-compose.yml` file might look like this:

```yaml
version: "3"
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
```

This file defines two services, `web` and `redis`. The `web` service is built from the current directory (which contains a Dockerfile), and exposes port 5000. The `redis` service is created from the `redis:alpine` image.

## Resources

Here are some helpful resources for learning Docker:

- [Docker documentation](https://docs.docker.com/): The official Docker documentation is a great place to start learning about Docker. It includes tutorials, reference guides, and API documentation.
- [Docker Hub](https://hub.docker.com/): Docker Hub is a repository of images that can be used to create containers. It includes a wide variety of images for popular software stacks, as well as user-submitted images.
- [Dockerfile reference](https://docs.docker.com/engine/reference/builder/): The Dockerfile reference is a detailed guide to creating Docker images using Dockerfiles. It includes information on all the available commands and instructions.
- [Docker Compose documentation](https://docs.docker.com/compose/): The Docker Compose documentation provides a comprehensive guide to using Docker Compose to define and run multi-container applications.
- [Docker Compose file reference](https://docs.docker.com/compose/compose-file/): The Docker Compose file reference provides detailed information on all the available options for defining services in a Docker Compose file.
- [Docker for Beginners: Full Course](https://youtu.be/fqMOX6JJhGo): This YouTube video by FreeCodeCamp provides a comprehensive introduction to Docker, covering everything from installation to creating containers, Dockerfiles, and Docker Compose.
- [Play with Docker](https://labs.play-with-docker.com/): Play with Docker is an online sandbox for experimenting with Docker. It provides a web-based interface for creating and managing containers, as well as a built-in terminal for running commands inside the containers.

These resources should provide a solid foundation for learning Docker. Happy containerizing!