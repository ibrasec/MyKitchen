## Search Docker Hub for images
To find a certain docker image simply run the below commmand passing the image name
```
$ docker search <image-name>

example:
$ docker search redis
```

## Running a docker image
To run a certain image, use the run flag, this will run the image and might get you inside of it, so that whatever you type in the terminal is going to only affect the running image.
```
$ docker run <image-name>
```
To run the image in the background, simply add the -d option, this is similar to passing the & charecter after executing a service.
```
$ docker run -d <image-name>
```
To run the image with a certain version simply add the version after the :
```
$ docker run -d <image-name>:<image-version>

example
$ docker run -d redis:2.3
```

## Finding the running containers
use the below command to list the currently running containers
```
$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
54106c6357da        redis               "docker-entrypoint.s…"   4 minutes ago       Up 4 minutes        6379/tcp            determined_brattain

```

## Get more details about the running container
```
$ docker inspect <container-id>|<container-name>

example:
$ docker inspect 54106c6357da

$ docker inspect determined_brattain
```

## Get the logs the container has written in the stderr/stdout
```
docker logs <container-id>|<container-name>

example:
$ docker logs 54106c6357da

$ docker logs determined_brattain
```
