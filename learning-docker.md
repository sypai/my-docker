## Getting Started with Containers

**Run a container**

`docker container run --publish --detach 8080:80 --name webhost nginx`

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

**Process Monitoring**

`docker top [container]` Display the running processes of a container

`docker inspect [container]` Display detailed information on one or more containers

`docker stats [container]` Display a live stream of container(s) resource usage statistics

**Getting a shell inside containers**

`docker container exec [OPTIONS] <container-name>` Run a command in a running container

`-t` or `--tty` Allocates a pseudo-TTY and simulates a real terminal like what SSH does

`-i` or `--interactive` Keep STDIN open even if not attached (Keep session open to receive terminal input)

## Docker Networks

`docker network ls` List Networks

`docker network create` Create a network. The `DRIVER` accepts `bridge` or `overlay` which are the built-in network drivers. If you have installed a third party or your own custom network driver you can specify that `DRIVER` here also. If you don’t specify the `--driver` option, the command automatically creates a `bridge` network for you. When you install Docker Engine it creates a `bridge` network automatically. This network corresponds to the `docker0` `bridge` that Engine has traditionally relied on. When you launch a new container with `docker run` it automatically connects to this `bridge` network. You cannot remove this default `bridge` network, but you can create new ones using the network create command. 

`$ docker network create -d bridge my-bridge-network
`

`docker network inspect` Display detailed information on one or more networks. Returns information about one or more networks. By default, this command renders all results in a JSON object.

`docker network connect` Connect a container to a network

`docker network disconnect` Disconnect a container from a network

`docker network prune` Remove all unused networks. Unused networks are those which are not referenced by any containers.

`docker network rm` Remove one or more networks by name or identifier. To remove a network, you must disconnect any containers connected to it.