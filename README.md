# Docker overview

Docker - a service to launch applications in containers

- Applications run in an isolated environment.
- Easy to run applications on different servers.
- All application dependencies are installed inside containers.
- Easy to scale by increasing the number of containers.
- Very convenient to use in the application development process.

## Docker Components:
- Client
- Daemon (service)
- Host
- Container
- Image
- Repository
- Registry

![image](https://github.com/nikvolynets/docker-info/assets/151893648/8bb86702-b9ee-4e1b-b806-d122b5796930)


## Concepts:
- One Image -> Several Containers
- Image consist of Layers
- Different versions of the image are stored in the repository
- Different versions are marked with different tags
- One version of the image can have multiple tags

## CLI Commands:
- `docker version` - info about docker server & client
- `docker ps -a` - shows a list of running and stopped containers
- `docker images` - list of all images
- `docker run hello-world` - creates and runs a container
- `docker rm <container id>` - delete a container
- `docker -i -t <container name>` - interactive terminal
- `hostname -i` - find out the IP address of the container
- `exit` - stop the container
- `docker container prune` - deletes all containers
- `docker run -d <container name>` - -d is running in the background
- `docker container inspect <docker id> | grep IPAddress`
- `docker stop <container id>` - stops the container
- `docker exec -it <container id> bash` - runs a specific process in the container
- `docker run -d -name my_nginx nginx` - starts a new container and assigns a new name
- `docker run -p 8080:80 nginx` - create and run container 8080 - external port, 80 - container port (port mapping)
- `docker run -v ${PWD}:/usr/share/nginx/html nginx` - connecting a volume (volume mapping)
- `docker run -it -rm <container name>` - automatically delete the container after setup
- `\` - used for line breaks in the terminal

#### Docker automatically stops containers if the process is completed

### Image Creation Steps
- Need a Dockerfile
- Dockerfile is placed in the root folder of the application
- Dockerfile contains instructions for creating an image
- When creating an image, you can specify the name and tag for the image
- Containers can be created based on the ready image

### Example Instruction:

```SQL
FROM python:alpine ## specifying the image, alpine - minimal version of the image
WORKDIR /app ## path to the folder inside the image
COPY . . ## path to the local folder on the computer
CMD ["python","main.py"] ## name of the executable file
docker build . - creates an image (run from the directory with Dockerfile)
```

- `docker build .` - create image (run command from Dockerfile directory)
