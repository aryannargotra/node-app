# Node.js Application Containerization
In this repository, we demonstrate how to containerize a simple Node.js application using Docker and replicate common CI/CD steps found in real-world scenarios.

Simulating CI/CD Integration
The following screenshot illustrates how Jenkins can be configured to push Docker images to a repository:

![Screenshot 2024-08-23 at 1 11 49 PM](https://github.com/user-attachments/assets/1f3ec579-a7a8-4a36-aec8-00b006deb5fb)

Building the Docker Image
To build a Docker image for your Node.js application, use the following command:

```
docker build -t my-app:1.0 .
```
This command will create a Docker image tagged as my-app:1.0.

Running the Docker Container
To run a container from the image, use:

```
docker run -d -p 3000:3000 --name my-running-app my-app:1.0
```
This command starts a container in detached mode, mapping port 3000 from the container to port 3000 on your host machine.

Pushing the Image to AWS Elastic Container Registry (ECR)
1. Authenticate Docker with AWS ECR
First, authenticate Docker to your AWS ECR repository:

```
aws ecr get-login-password --region ap-south-1 | {authentication command}.amazonaws.com
```
2. Tag the Docker Image
Tag your Docker image to prepare it for pushing to AWS ECR:

```
docker tag my-app:1.0 {docker registry}.amazonaws.com/my-app:1.0
```
3. Push the Docker Image to ECR
Push the tagged image to your AWS ECR repository:

```
docker push {docker registry}.amazonaws.com/my-app:1.0
```

4 . So, after you package your application in a docker image and save it in a private repository you need to deploy it on some server so that developer and testers and actually try to app working.
