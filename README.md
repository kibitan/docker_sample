# Docker sample

 - https://docs.docker.com/get-started/

# useful tool

- GUI for docker container: [Kitematic](https://kitematic.com/)

# useful link
- [Best practices for writing Dockerfiles | Docker Documentation](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
   - [Create ephemeral containers](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#general-guidelines-and-recommendations)
   - [Understand build context](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#understand-build-context)
   - [Exclude with .dockerignore](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#exclude-with-dockerignore)
   - [Use multi-stage builds](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#use-multi-stage-builds)
   - [Decouple applications](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#decouple-applications)
   - [Leverage build cache](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#leverage-build-cache)
   - [RUN](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#run)
   - [ENV](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#env)
   - [EXPOSE](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#expose)
   - [ADD or COPY](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#add-or-copy)
   - [USER](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#user)
   - [WORKDIR](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#workdir)
   
- [Use multi-stage builds | Docker Documentation](https://docs.docker.com/develop/develop-images/multistage-build/)
- [Docker development best practices | Docker Documentation](https://docs.docker.com/develop/dev-best-practices/#use-cicd-for-testing-and-deployment)

## questions
- [What is the difference between "expose" and "publish" in Docker? - Stack Overflow](https://stackoverflow.com/questions/22111060/what-is-the-difference-between-expose-and-publish-in-docker)

- [Get Started, Part 2: Containers | Docker Documentation](https://docs.docker.com/get-started/part2/#run-the-app)
 > This port remapping of 4000:80 demonstrates the difference between EXPOSE within the Dockerfile and what the publish value is set to when running docker run -p. In later steps, map port 4000 on the host to port 80 in the container and use http://localhost.

- what is layer?

## debug
- [Dockerfileを作っている最中にデバッグするときの基本的な手順 | GENDOSU@NET](https://gendosu.jp/archives/2838)


```
$ docker ps -a

$ docker commit <container id> builddebug

$ docker run --rm -it builddebug /bin/bash
```

- login on container `docker run --rm -it <container name> /bin/bash`

## Cheetsheet - container

### images

#### build image
`docker build -t friendlyhello .`

#### see the images
`docker image ls`


### container

#### run container
`docker run -p 4000:80 friendlyhello`

#### run container in background
`docker run -d -p 4000:80 friendlyhello`

#### debug
`docker run --rm -it friendlyhello bash`

#### see current cuntainers
`docker container ls`

#### stop container
`docker container stop`

#### history of layers
`docker history friendlyhello`

- [docker history | Docker Documentation](https://docs.docker.com/engine/reference/commandline/history/)


### registry

#### tag

`docker tag image username/repository:tag`

#### publish

`docker push username/repository:tag`

#### run from docker hub

`docker run -p 4000:80 kibitan/get-started:part2`


## Cheetsheet - service

### deploy

`docker stack deploy -c docker-compose.yml app_name`

### ls

`docker service ls`

### list tasks

`docker service ps app_name`

### down a app

`docker stack rm getstartedlab`
