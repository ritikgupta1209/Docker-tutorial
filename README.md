# docker-testapp

This project demonstrates how to use Docker to containerize a simple Node.js application. Docker allows you to convert your Node.js app into an image, which can then be used to create and run containers.

Method 1: Using Docker Compose
1) Clone the application from GitHub.

2) Add a docker-compose.yaml file to the project directory.

3) Define your services such as the Node.js app and any dependent databases or containers.

4) Run the Docker Compose file to build and start the containers along with a default Docker network:
    docker compose -f abc.yaml up -d

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


Method 3: To run directly the image without build and then run. 

You can use abc.yaml to build and run your app directly, and it will automatically use the Dockerfile if you tell it to.
You don’t need to manually run docker build and then docker run — Compose will handle both build and run steps in one go.

1) When you use a abc.yaml file then include:

services:
  app:
    build: .
    image: my-image-name:tag(optional)
    
    Docker Compose will:
     Look in the current directory (.) for a Dockerfile.
     Build the image using that Dockerfile.
     Then create and run the container based on that image.
     Docker Compose uses your Dockerfile to build a new image
     Tags it as my-image-name:1.0

2) Run this compose command . It will build and run in one go.
    docker compose abc.yaml up -d   OR  docker compose up -d  (if docker-compose.yaml is there no need to specify the name)
    


