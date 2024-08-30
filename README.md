# Overview

The repository contains various Dockerfiles tailored for different systems, each equipped with the necessary software tools and libraries, allowing users to easily build and complete their projects. Each dockerfile is inside a folder in the repository based on different systems. For example, to build a ROS humble system using docker, use the dockerfile inside the ros_humble folder and build your container.

The repository is open for pull requests and collaboration to provide users with readily available Dockerfiles. Currently, the repository contains Dockerfiles for various ROS versions, which are useful for robotics projects.

## Instructions to Build a Docker Image

1. Make sure Docker is installed on your system.
2. For ease of use rocker is recommended, which can be installed using below command. If you faces issues installing rocker with below command refer to this documentation -> [Rocker](https://github.com/osrf/rocker)
```
sudo apt install python3-rocker
```
3. To use the dockerfile, download the required file or Clone the repository using the command below. Use terminal in Ubuntu or Git Bash Terminal in Windows
```
git clone https://github.com/vinay06vinay/DockerFiles.git
```
4. In the terminal make sure you are inside the folder required. For example, if you want a ROS humble system use below process
```
cd ros_humble
```
5. Build the docker image using below command in terminal 
```
# This command uses the docker file in your directory and builds an image with name humble
docker build . -t humble
```
6. Once the docker image is built, check the image by using below command
```
docker images
```
7. Use the below rocker command to run the docker container. It will open a terminator window with the ros package built
```
rocker --x11 --privileged humble terminator
```
8. If you want to run the container using native docker commands use below command
```
 docker run -it humble
```