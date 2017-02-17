# Docker most frequent commands

- [Docker](#docker)
- [Docker Compose](#docker-compose)
- [Example Docker setups](#example-docker-setups)

## Docker

### Run image:

`docker run docker/whalesay`

`docker run docker/whalesay cowsay boo # Run image with parameters.`

`docker run docker/whalesay -d # Run in the background.`

### Run container:

`docker start 97d0c0043df3 # Start a container in the background.`

`docker restart 97d0c0043df3 # Restart a container.`

`docker attach 97d0c0043df3 # Attach a terminal & stdin to the container.`

### Build image

`docker build -t name/repo:version . # Builds a docker image out of the Dockerfile.`

`docker build --rm=false -t name/repo:version . # Builds a docker image wihtout deleting the container.`

`docker commit 97d0c0043df3 name/new-repo # Builds a docker image from a container.`

### Remove

`docker rm 97d0c0043df3 # Remove one or more containers.`

`docker rmi docker/whalesay # Remove one or more images.`

### Monitor:

`docker containers`

`docker images`

`docker ps # Show running containers.`

`docker ps -a # Show all containers.`

## Docker Compose

`docker-compose up`

`docker-compose up -d # Run in the background.`

`docker-compose up --force-recreate # Force recreate containers` ([be aware](https://github.com/docker/compose/issues/2127))

`docker-compose up --build # Force build images on start.`

`docker-compose -f docker-compose.dev.yml up`

`docker-compose -f docker-compose.yml -f docker-compose.dev.yml up # Extend docker-compose.yml configuration file.`

`docker-compose build # Create or rebuild services.`

`docker-compose pull # Pull the latest image(s) version.`

`docker-compose run web # Start a specific docker-compose service.`

`docker-compose run web npm start # Override default service command.`

`docker-compose run web /bin/bash -c "npm start"`

`docker-compose --service-ports run web npm start # Run command with the service's ports enabled and mapped to the host.`

`docker-compose stop # Stop docker containers`

`docker-compose rm -f # Remove containers`

## Example Docker setups

[Node.js + MongoDB](https://github.com/zurfyx/docker-node)