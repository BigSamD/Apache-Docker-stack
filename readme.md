# Docker Compose for a Web Application

This docker-compose.yml file defines two services, web and node, to create a simple web application.

## Services NGIX

### web

This service uses the nginx:alpine image and exposes port 80. It mounts the host directory ./ to /usr/share/nginx/html to serve static files.

### node

This service uses the node:alpine image and mounts the host directory ./ to /app. It sets the working directory to /app and runs `npm install` to install dependencies.

The two services work together to run a Node.js application. The web service handles the HTTP requests and serves static files, while the node service runs the actual application.

## Usage

To start the containers, run:

```
docker-compose up
```

This will pull the images if needed, build the containers, and start the services based on the docker-compose.yml file.

The application can be accessed on http://localhost when the containers are running.

Code changes made on the host should be immediately reflected in the containers.

To stop the services, run:

```
docker-compose down
```

This stops and removes the containers.
