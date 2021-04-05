# Database upgrades with Containers

### Task

-   Create a `postgres` container with named volume psql-data using version `9.6.1`
-   Use Docker Hub to learn `VOLUME` path and versions needed to run it 
-   Check logs, stop container
-   Create a new `postgres` container with same named volume using `9.6.2`
-   Check logs to validate


### Solution

```python

    # Start a postgres:9.6.1 container
    docker container run -d --name psql -v psql-data:/var/lib/postgresql/data postgres:9.6.1

    # Check logs
    docker logs <container_name>

    # Start a postgres:9.6.2 container with same volume
    docker container run -d --name psql2 -v psql-data:/var/lib/postgresql/data postgres:9.6.2
    
     
```