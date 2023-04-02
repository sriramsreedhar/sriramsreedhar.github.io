# Docker Tutorial



List Docker Images  :
```
docker images
```

Pull a docker image from external docker hub

```
docker pull python:latest
```

Create a new container from docker image

```
docker run -it python:latest /bin/bash 
```

List Docker containers

```
docker ps  [For running containers.]
docker ps -a  [For all containers, i.e containers that was stopped.]
```

Start a container

```
docker start 59cd0020a02e
```


Stop a container

```
docker stop 59cd0020a02e
```

Clean up containers

```
Stop and Remove

docker container stop 092c5dc85044
docker container rm 092c5dc85044

```


Remove unused images

```
 docker system prune

```

To delete all containers
```
docker container rm $(docker container ls -a -q)

```

To delete all images
```
 docker image rm $(docker images -q)
```

To delete all untagged images
```
docker image rm $(docker images -q -f "dangling=true")
```

Check Image history
```
docker image history  python:latest
```

What is the difference between docker-compose.yaml and Dockerfile

```
Docker-composer.yaml lets you configure multiple images.

Dockerfile lets you configure one image.

```

What is the difference between exec and run?

```
- exec helps you to login to already running container.
- run helps you create a new container.
```

How to share a local mount in a container?
```
docker container run --rm -ti \
  --mount type=bind,target=/mnt/session_data,source=/data \
  ubuntu:latest /bin/bash


For read-only mount
 docker container run --rm -ti -v /mnt/session_data:/data:ro \
  ubuntu:latest /bin/bash
```


List Docker volumes
```
docker volume ls
```

To inspect a docker volume in detail

```
docker inspect volume-sriram-dev-environment
```

To remove a docker volume

```
docker volume rm volume-sriram-dev-environment
```

To login as root, if your image is not logged in with root.

```
docker container run --rm -ti --hostname="python-container.example.com" -u root sriram/python:latest /bin/bash
```

How to remove docker container when it exits?

```
 The --rm option tells Docker to automatically remove the container when it exits. 

# docker run --rm -ti -p 8000:80 -p 8443:443 --name pandorafms 
```

What does the -ti option do?


```
-t is for enabling Pseudo terminal
-i is for standard input i.e stdin

docker container run  -ti sriram/python:latest /bin/bash
```

How to check image history?

```
docker image history  python:latest
```




