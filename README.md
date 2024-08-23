# Node App

In this repository, we will containerize a simple Node.js application using Docker and replicate common CI/CD steps performed in real-world scenarios.

## Building the Docker Image

Firstly, to build a Docker image from the application, use the following command:

```
docker build -t my-app:1.0 .
```
# Running the Docker Container

```
 docker run -d -p 3000:3000 --name my-running-app my-app:1.0 
```
# Creating repo in AWS Elastic container Repository (ECR)
Pushing Private repo so we will give Docker log in to authenticate

```
aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 088005245182.dkr.ecr.ap-south-1.amazonaws.com
```
tag your image so you can push the image to this repository:
```
# Docker push command may wary for you 
docker tag my-app:1.0.amazonaws.com/my-app:1.0
```
Docker Push ```Image Name```
# Here We simulated how a jenkins will push an image to docker repository
![Screenshot 2024-08-23 at 1 11 49 PM](https://github.com/user-attachments/assets/bd6c0e61-db57-4eb3-8c70-2596fe25528d)
