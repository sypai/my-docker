# Running and Managing multiple containers

### Task 

-   `Run a `nginx`, a `mysql` and a `httpd`(apache) server. Run all of them in the background with a name.
-   `nginx` should listen on `80:80`, `httpd` on `8080:80`, `mysql` on `3306:3306`
-   When running `mysql`, use the `--env` option to pass in `MYSQL_RANDOM_ROOT_PASSWORD=yes`, Use logs on mysql to find the random password it created on startup.
-   Clean it all up with `stop` and `rm`.


### Solution

```python
    # Starting nginx
    docker container run --detach --publish 80:80 --name my-nginx nginx

    # Starting apache
    docker container run -d -p 8080:80 --name my-apache httpd

    # Starting mysql server
    docker container run -d -p 3036:3036 --name my-sql --env MYSQL_RANDOM_ROOT_PASSWORD=yes mysql

    # Check for random password
    docker container logs my-sql

    # List all containers
    docker container ls -a

    # Stop all containers
    docker container stop my-nginx my-sql my-apache

    # Delete all containers
    docker container rm my-nginx my-sql my-apache
```