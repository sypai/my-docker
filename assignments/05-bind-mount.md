# Bind Mounts


## Task
- Use a Jekyll "Static Site Generator" to start a local web server

- Use editor to make changes in the files on our host

-   Container detects changes with host files and updates web server


## Solution

- Go to folder bindmount-sample-1 

```bash
docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve
```

