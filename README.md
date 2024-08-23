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
