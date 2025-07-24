## Introduction to Docker and Containers

 In 2013, Solomon Hykes introduced Docker, a lightweight containerization platform that revolutionized how applications are built, shipped, and deployed.

Docker packages applications and all their dependencies into isolated units called containers. This ensures consistent behavior across environments—from development to production—solving the classic "it works on my machine" problem.

By abstracting away host OS differences, Docker simplifies deployment, reduces configuration overhead, and supports CI/CD pipelines with clean, reproducible builds.

Whether you're just starting in DevOps or aiming to improve software delivery, Docker is a must-know tool in modern infrastructure.

## Advantage Of Containers
- Portability across different environments
- Resource efficiency compared to virtual machines
- Rapid apllication deployment and scaling.

## Importance of Docker
- Technology and Industry Impact
- Real-world impact

## Getting Started with Docker
### Installing Docker

Add Docker’s Official GPG Key (for Secure Package Verification)
Before installing Docker Engine, configure the Docker repository securely by adding its official GPG key:

```
# 1. Update your package list
sudo apt-get update

# 2. Install required certificates and tools
sudo apt-get install ca-certificates curl gnupg

# 3. Create a directory to store Docker’s key
sudo install -m 0755 -d /etc/apt/keyrings

# 4. Download Docker’s GPG key securely
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# 5. Set read permissions on all users for the key
sudo chmod a+r /etc/apt/keyrings/docker.gpg

```

## Add Docker Repository to APT Sources
This section adds the official Docker repository to your system so you can install Docker packages directly from Docker, not from Ubuntu’s default repositories.

# Command to Add Docker Repo:

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```
 This command:

Detects your architecture (e.g., amd64)

Detects your Ubuntu codename (e.g., fred, focal)

Adds Docker’s repository to /etc/apt/sources.list.d/docker.list

# Update Your Package Index:

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

```

This installs

- docker-ce: Docker Engine (Community Edition)

- docker-ce-cli: Docker command-line tool

- containerd.io: Container runtime

- buildx and compose plugins

# Verify Docker is Installed & Running:

```
sudo systemctl status docker

```

<img width="962" height="390" alt="docker1" src="https://github.com/user-attachments/assets/a4992c4f-0614-4317-8dc1-ace2f2746d44" />

## Running "Hello World" Container

# Using the "docker run" command
The "docker run" commmand is the entry point to excecute containers in docker. It allows you to create and start a container based on the specified docker image.

```
# Run the "Hello World" container
docker run hello-world

```
<img width="963" height="444" alt="docker2" src="https://github.com/user-attachments/assets/749003cc-6ded-4f36-ad3c-4a2f56f0d64c" />

When you execute this command, Docker performs the following steps:

   1.  Pulls Image (if not available locally): Docker checks if the hello-world image is available locally. If not, it automatically pulls it from the Docker Hub, a centralized repository for Docker images.

   2.  Creates a Container: Docker creates a container based on the hello-world image. This container is an instance of the image, with its own isolated filesystem and runtime environment.

    3. Starts the Container: The container is started, and it executes the predefined command in the hello-world image, which prints a friendly message.

# Understanding the Docker Image and Container Lifecycle

**Docker Image**: A Docker image is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools. Images are immutable, meaning they cannot be modified once created. Changes result in the creation of a new image.

   - **Container Lifecycle**: Containers are running instances of Docker images.

        - They have a lifecycle: create, start, stop, and delete.

        - Once a container is created from an image, it can be started, stopped, and restarted.
    
# Verifying Successful execution
You can check if the image is now in your local environment with Example output

```
docker images
```
<img width="962" height="48" alt="docker3" src="https://github.com/user-attachments/assets/d48117fc-732f-4fd3-ac1e-3b668c38195b" />




## Basic Docker commands
```
# Run a container based on the "nginx" image
docker run hello-world

# List running containers
docker ps

# List all containers (running and stopped)
docker ps -a

# Stop a running container (replace CONTAINER_ID with the actual container ID)
docker stop CONTAINER_ID

# Pull the latest version of the "ubuntu" image from Docker Hub
docker pull ubuntu

# Push a local image to Docker Hub
docker push your-username/image-name

# List all local Docker images
docker images

# Remove a Docker image (replace IMAGE_ID with the actual image ID)
docker rmi IMAGE_ID



```

<img width="958" height="56" alt="docker4" src="https://github.com/user-attachments/assets/0324cd9d-8678-436a-b4cf-4c6320d90464" />





