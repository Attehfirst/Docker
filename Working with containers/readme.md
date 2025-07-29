# WOrking with Docker Containers

## Introduction to Docker Containers

Docker containers are lightweight, portable, and executable units that encapsulate an application and its dependencies. In the previous step, we worked a little with docker contaier. We would dive deep into the basics of working with Docker containers, from launching and running containers to managing their lifecycle.

## Running Containers

To run a container, you use the **docker run** command followed by the name of the image you want to use. Let’s create a container from ubuntu image. This command launches a container based on the Ubuntu image

```
docker run ubuntu
```
<img width="1303" height="138" alt="image" src="https://github.com/user-attachments/assets/34a934cc-1182-49a3-80a5-a887ac2bb311" />

The image above shows that the container is created but not running. We can start the container by running

```
docker start f4f4a864083b 
```

<img width="1299" height="39" alt="image" src="https://github.com/user-attachments/assets/548d5dfc-0158-4d0c-a49a-8a3d38945bf4" />

## Running Containers in the Background

By default, containers run in the foreground, and the terminal is attached to the container’s standard input/output. To run a container in the background, use the -d option:

```
docker run -d ubuntu

```
This command starts a container in the background, allowing you to continue using the terminal.

## Container Lifecycle

Containers have a lifecycle that includes creating, starting, stopping, and restarting. Once a container is created, it can be started and stopped multiple times.


