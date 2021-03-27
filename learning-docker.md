## Getting Started with Containers

**Run a container**

`docker container run --publish --detach --name webhost 8080:80 nginx`

`run` Start a new container from image `nginx` (download from docker hub if not found locally)

`--publish` or `-p` Binds container's TCP port 8080 to host's port 80

`--detach` or `-d` Runs the container in background

**Stop a container**

`docker container stop <docker_id / docker_name>`

**List running containers**

`docker container ls`

Add `-a` or `-all` to include stopped containers

`docker ps`

`docker ps` is shorthand that stands for "docker process status", whilst `docker container ls` is shorthand for the more verbose docker container list. There is no difference in how they work, and `docker container ls` is the 'newer' command, so you should probably prefer it.

**Delete all running and stopped containers**

`docker container rm -f <docker ids / docker names>`

**Print container's logs**

`docker container logs --tail 100 <docker id / docker name>`

`--tail` print last 100 lines of log

**List processes running inside a container**

`docker top <container name>`

Display the running processes of a container

**Create, start & run**

`docker create` adds a writeable container on top of your image and sets it up for running whatever command you specified in your CMD. The container ID is reported back but it’s not started.

`docker start` will start any stopped containers. This includes freshly created containers.

`docker run` is a combination of create and start. It creates the container and starts it.


