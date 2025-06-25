# docker-testapp

This project demonstrates how to use Docker to containerize a simple Node.js application. Docker allows you to convert your Node.js app into an image, which can then be used to create and run containers.

Method 1: Using Docker Compose
1) Clone the application from GitHub.

2) Add a docker-compose.yaml file to the project directory.

3) Define your services such as the Node.js app and any dependent databases or containers.

4) Run the Docker Compose file to build and start the containers along with a default Docker network:
    docker-compose -f abc.yaml up -d

5) Start the Node.js application:
    node app.js


Method 2: Using Dockerfile
1) Clone the application from GitHub.

2) Add a Dockerfile to the root of the project directory.

3) Build the Docker image in the same directory as the Dockerfile:
    docker build -t testapp:1.0 .

4) Run the Docker container:
    docker run testapp:1.0

5) Access an interactive terminal within the running container (optional):
docker run -it testapp:1.0 bash
