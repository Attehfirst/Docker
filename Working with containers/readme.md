# Working with Docker Containers

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

## Starting, Stopping, and Restarting Containers

```
#To start a stopped container:
docker start container_name

#To stop a running container:
docker stop container_name

#To restart a container:
docker restart container_name

#Removing Containers
docker rm container_name

#This deletes the container, but keep in mind that the associated image remains on your system.

```

## Task: Docker Container Operations

1. Start a Container and Run a Simple Command:

- Use an official Ubuntu image to start a container. If you don’t have the image, you can pull it from docker hub
- Run a simple command within the container, such as displaying the system information.
- Stop the Container and Verify Its Status:
  
<img width="1291" height="151" alt="image" src="https://github.com/user-attachments/assets/97715d7d-b9f6-412a-90f6-7d0d57d6121d" />

<img width="1292" height="37" alt="image" src="https://github.com/user-attachments/assets/ae1e5a9b-ba80-4a20-bb73-c9cbd77de2a7" />


2. Stop the running container
- Verify that the container is stopped
- Note the status column to confirm the container’s status.
- Restart the Container and Observe Changes:

  <img width="1290" height="118" alt="image" src="https://github.com/user-attachments/assets/a9bd5ddf-da9e-41e1-ae20-1bbf2babc279" />

<img width="1293" height="154" alt="image" src="https://github.com/user-attachments/assets/f14bf5f5-94a6-43a7-b3b7-66bd8940a775" />


3. Restart the stopped container
- Verify the container’s status again to ensure it’s running
- Observe any changes or differences in the container’s behavior after the restart.
- Remove the Container:

  <img width="1288" height="142" alt="image" src="https://github.com/user-attachments/assets/a9472a41-bea4-47f1-a5ae-997f58f488ff" />


4. Stop the running container (if it’s still running)
- Remove the container
- Verify that the container is removed
- Confirm that the container is no longer listed.





