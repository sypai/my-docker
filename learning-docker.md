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

**Delete all running and stopped containers**

`docker container rm -f <docker ids / docker names>`

**Print container's logs**

`docker container logs --tail 100 <docker id / docker name>`

`--tail` print last 100 lines of log