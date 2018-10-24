# Docker sample

 - https://docs.docker.com/get-started/

# useful tool

- GUI for docker container: [Kitematic](https://kitematic.com/)

## questions
- [What is the difference between "expose" and "publish" in Docker? - Stack Overflow](https://stackoverflow.com/questions/22111060/what-is-the-difference-between-expose-and-publish-in-docker)

- [Get Started, Part 2: Containers | Docker Documentation](https://docs.docker.com/get-started/part2/#run-the-app)
 > This port remapping of 4000:80 demonstrates the difference between EXPOSE within the Dockerfile and what the publish value is set to when running docker run -p. In later steps, map port 4000 on the host to port 80 in the container and use http://localhost.

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

#### see current cuntainers
`docker container ls`

#### stop container
`docker container stop`


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
