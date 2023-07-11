Choice of the base image on which to build each container. 
//Backend Container

Used node:18-alpine as the base image, alpine is a variant of Node.js that is used in minimizing image size.

//Client Container

Used a multi-stage build to separate the build environment from the production environment, allowed me to avoid including unnecessary build tools and files in the final image hence reducing the size of the image.

Used node:18-alpine at the build stage ,as the base image, alpine is a variant of Node.js that is used in minimizing image size.

Used node:18-alpine at the production stage ,as the base image, alpine is a variant of Node.js that is used in minimizing image size.

Dockerfile directives used in the creation and running of each container. 
FROM: Specifies the base image

WORKDIR: Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow it.

COPY: Copies files and directories from the host to the container.

RUN: Runs a command inside the container.

EXPOSE: Exposes a port from the container to the host machine.

CMD: Specifies the command to run when the container starts.

In the docker-compose.yml file used to run the containers, the following directives are used version: Specifies the version of the Docker Compose file format to use.

services: Specifies the different services (containers) to run that is the Backend and Client containers.

build: Specifies the build context and Dockerfile for building the container image.

ports: Specifies the port mapping between the container and host machine.

volumes: Specifies the volumes to mount between the container and host machine.

depends_on: Specifies the order in which the services should be started.

Docker-compose Networking (Application port allocation and a bridge network implementation) where necessary. In Docker Compose, the networks directive is used to define networks for containers to connect to each other

Docker-compose volume definition and usage (where necessary). 
../client:/app - This is a bind mount volume that maps the local ../client directory to the /app directory inside the client container.It allows changes made to files in the ../client directory on the host system to be reflected inside the container. ../backend:/app - This is a bind mount volume that maps the local ../backend directory to the /app directory inside the backend container. This allows changes made to files in the ../backend directory on the host system to be reflected inside the container.