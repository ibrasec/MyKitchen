# Basic Docker Commands
<details>
<summary> show/hide...
</summary>
  
## Search Docker Hub for images
To find a certain docker image simply run the below commmand passing the image name
```
$ docker search <image-name>

example:
$ docker search redis
```

## Running a docker image
To run a certain image, use the run flag, this will run the image and might get you inside of it, so that whatever you type in the terminal is going to only affect the running image, (foreground process). Note that adding the keyword **latest** is the default, where the image version to ran will be the latest.

--name option will assigne the container the name you choose
```
$ docker run <image-name>:latest --name myImageName
```
To run the image in the background, simply add the -d option, this is similar to passing the & charecter after executing a service.
```
$ docker run -d <image-name>:latest
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

## Exposing particular port
by default the port that is running on the container are not exposed and can't be reached, as example, if the container has an ssh service running on port 2222 any one who wants to connect to this port will fail to connect to it unless that port is exposed, to expose the container port use the -p option as follows:

## Static port mapping
```
$ docker run -d <image-name>:latest -p <system-port>:<container-port> 

example: exposing container ssh port 2222 with the system port 2002
$ docker run -d redis:latest -p 2002:2222
```

**Note**: by default the port will be mapped to the ip address 0.0.0.0, which means any active ip address running on the system will be have its mapped port open, to only restrict this port to be mapped to a certain ip address simple add the following 
```
$ docker run -d <image-name>:latest -p <system-ip-address>:<system-port>:<container-port> 

example
$ docker run -d redis:latest -p 127.0.0.1:2002:2222 
```
### Dynamic port mapping
To run the container on dynamic port instead of fixed port
```
$ docker run -d redis:latest -p 127.0.0.1:2002 --name DynamicPort 
```

## finding the Port mapping number running On a certain container
To find all port mapping
```
$ docker port <container-id>|<container-name>
```
To find a certain port mapping 
```
$ docker port <container-id>|<container-name> <port-name>
```

## Executing a command from outside of the container
```
$ docker run <image-name> <command-to-execute>

example
$ docker run ubuntu ps
```

## Getting a Bash shell of the container
```
$ docker run -it <image-name> bash

example:
$ docker run -it ubuntu bash
root@b123ujs123:/#
```

</details>


# Building docker image
<details>
<summary> show/hide...
</summary>
  
To build a docker image, you need a file that have instructions to follow for building, these instructinos are located inside a file called the **Dockerfile**, the Dockerfile looks like this:

```
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

FROM means what is the image name:tag we want our container to have.

The build command executes each instruction within the Dockerfile.

```
docker build <chosen-image-name> .
```

By default the tag for the newly created image will be set **latest**, if we want to specify the version then we can use the **-t** or **--tag**

**NOTE: it is recommended to always set a tag for your images in order to keep track of your versions and not to overwrite each other as always being the latest**

```
$ docker build -t <chosen-image-name>:<tag> .
or 
$ docker build --tag <chosen-name>:<tag> .
```

if you list the currently installed images, you will find the new image with its tag listed

```
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
webserver-image     v1                  ba094421bc0        31 seconds ago      20.5MB
```

</details>


# Dockerfile commands
## COPY
used to copy the contents from the directory containing the Dockerfile into the directory of the container's image.
```
COPY <src> <dst>

example
COPY index.html /usr/share/nginx/html
```

## RUN
used to run commands within the image, as example installaing something or executing something else
```
RUN
```
