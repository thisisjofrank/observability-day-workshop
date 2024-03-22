
# {project-name}

This contains a sample application for use in the Observability Day workshops.

## Running the application

Clone this repository.

TODO: right now you need to build each project, the docker build won't do it for you.

Install Docker.

`docker-compose up`

Access the app:

[http://localhost:8080]()

after making changes:

`docker-compose up --build`

## Publishing

To get new versions of the containers on Dockerhub for caching, log in appropriately.

`WORKSHOP_VERSION=${IMAGE_VERSION} docker compose build --push`

... for each $PROGRAMMING_LANGUAGE implemented.

## structure of the application

### web

The frontend is static files in `services/web/static`

The `services/web` directory also contains a Dockerfile and config for nginx to serve these. The nginx config also directs anything to /backend toward the backend-for-frontend service.

### backend-for-frontend

in `services/backend-for-frontend` is an express app that receives /createPicture.

It returns a .png, not a reference but the contents of the .png

