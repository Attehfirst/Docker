## Working with Docker Images

# What Are Docker Images?
Docker images are lightweight, portable, and self-contained blueprints for containers. Each image packages everything an application needs—code, runtime, libraries, and system dependencies—based on instructions defined in a Dockerfile.

# Pulling Images from Docker Hub
Docker Hub is a public image registry hosting thousands of ready-to-use Docker images. To download an image to your system, use the docker pull command:
```
docker pull ubuntu

```
To explore available images on Docker Hub, the docker command provides a search subcommand. For instance, to find the Ubuntu image, you can execute:

```
docker search ubuntu
```
This command allows you to discover and explore various images hosted on Docker Hub by providing relevant search results. In this case, the output will be similar to this:

<img width="719" height="477" alt="image" src="https://github.com/user-attachments/assets/c1c77575-408a-44a7-adde-75f51763446c" />



