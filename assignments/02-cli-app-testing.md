# Using different Linux distro containers

### Task

-  Start bash in both centos:7 and Ubuntu:18.04 interactively
-  Learn `docker container --rm`
-  Check curl --version
-  Ensure curl is installed and on latest version for that distro


### Solution


```python
    # Starting bash in ubuntu:18.04 container
    docker container run --rm -it --name my-ubuntu ubuntu:18.04 bash

    # Update packages and install curl
    apt-get update & apt-get install curl

    # Check version
    curl --version

    # Starting bash in centos:7 container
    docker container run --rm -it --name my-cent centos:7 bash

    # Update packages and install curl
    yum update curl

    # Check version
    curl --version

```