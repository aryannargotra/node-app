# node-app

In this repo we will containerise a simple node app using docker and try to replicate all the CI/CD steps we perform in real worrld scenario 

Firstly To build a docker image from the application

docker build -t my-app:1.0 .       

To run your image and start a container, you can use the docker run command

docker run -d -p 3000:3000 --name my-running-app my-app:1.0
