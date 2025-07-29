# Working with Docker Images

## What Are Docker Images?
Docker images are lightweight, portable, and self-contained blueprints for containers. Each image packages everything an application needs—code, runtime, libraries, and system dependencies—based on instructions defined in a Dockerfile.

## Pulling Images from Docker Hub
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

To download the official ubuntu image to your computer, use the following command.

```
docker pull ubuntu
````

<img width="721" height="102" alt="image" src="https://github.com/user-attachments/assets/f54b536c-9949-4fd1-b657-37012cae6605" />

Once an image has been successfully downloaded, you can proceed to run a container using that downloaded image by employing the "run" subcommand. if an image is not present locally when the docker run subcommand is invoked, Docker will automatically download the required image before initiating the container.
To view the list of images that have been downloaded and are available on your local machine, enter the following command:

```
docker images
```
Executing this command provides a comprehensive list of all the images stored locally, allowing you to verify the presence of the downloaded image and gather information about its size, version, and other relevant details.

<img width="715" height="78" alt="image" src="https://github.com/user-attachments/assets/cb5ecb74-a805-46a9-9500-d6a84546028a" />

## Dockerfile Overview
A Dockerfile is a plain text file that defines a series of instructions for building a Docker image. It acts as a blueprint for setting up a consistent, reproducible environment—specifying how to install dependencies, copy files, and configure the application.

## Writing a Dockerfile (Using NGINX)
In this example, we’ll use the official nginx image to serve a static HTML file.
NGINX is a high-performance open-source web server, often used for load balancing, caching, and reverse proxying.

To create a Dockerfile:

1. Open a text editor like vim, nano, or VS Code.

2. Define:

 A base image (e.g., nginx)

 Copy instructions for your HTML

 Any necessary configuration steps

```
# Use the official NGINX base image
FROM nginx:latest
# Set the working directory in the container
WORKDIR  /usr/share/nginx/html/

# Copy the local HTML file to the NGINX default public directory
COPY index.html /usr/share/nginx/html/

# Expose port 80 to allow external access
EXPOSE 80

# No need for CMD as NGINX image comes with a default CMD to start the server

```
To build an image from the Dockerfile, navigate to the directory containing the file and run

```
docker build -t dockerfile .

```
<img width="718" height="183" alt="image" src="https://github.com/user-attachments/assets/7a194d31-3c47-419c-90f9-fbe56beee590" />

To run a container based on the custom NGINX created with a dockerfile, run the command

```
docker run -p 8080:80 dockerfile
```

<img width="717" height="324" alt="image" src="https://github.com/user-attachments/assets/32f03eb9-a678-4e6a-ad9a-5e6ee8044792" />

To see list of available containers

```
docker ps -a
```
<img width="718" height="119" alt="image" src="https://github.com/user-attachments/assets/a0beeaa1-2f90-4ea9-adb8-a0fa8c8ea736" />


<img width="720" height="35" alt="image" src="https://github.com/user-attachments/assets/19c93be0-b4fb-466c-9879-bfa95a386acb" />

We can access the content of our browser with  http://54.226.254.180:8080/
<img width="1267" height="155" alt="image" src="https://github.com/user-attachments/assets/c715e57a-f798-493c-89b8-da56c072426b" />

## Pushing Docker Images To Docker Hub

Let’s recall our git project, where we push changes made on our local computer to a remote repository (github) so everyone can track the chages we made and also collaborate on it. Now that we have created a docker images on our own computer, we need to think about how to reuse this image in the future or how do people in other region make use of this image and possibly collaborate on it. This is where Docker Hub comes in. Let’s go ahead and push our image to docker hub

i. Create an account on Docker Hub if you don’t have one.

ii. Create a repository on docker hub

iii. Tag Your Docker Image Before pushing, ensure that your Docker image is appropriately tagged. You typically tag your image with your Docker Hub username and the repository name.

<img width="718" height="25" alt="image" src="https://github.com/user-attachments/assets/6ce7aa25-053c-4ffa-8fd4-98885758d3b2" />

iv. Login to Docker Hub and input your username and password

<img width="718" height="117" alt="image" src="https://github.com/user-attachments/assets/142bc45b-68b4-4f63-bd65-4c2d1dbd4473" />

v. Push the image to Docker hub

<img width="714" height="204" alt="image" src="https://github.com/user-attachments/assets/1778ea67-8a36-45d2-81dc-a50791ba7d30" />

vi. Verify the image is in your Docker hub repository

<img width="1008" height="433" alt="image" src="https://github.com/user-attachments/assets/d776d11b-4173-4ebc-bda5-b8d475593f0a" />


















