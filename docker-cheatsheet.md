# Docker container

## Code

```bash
# build image

docker build ./ -t nginx-image

# login to repository

docker login -u {username} -p {password} {host}:{port}
#                                        |___________|
#                                          optional
#                                     (default dockerhub)

# retag image

docker tag nginx-image {host}:{port}/nginx-image:0.1.0
#                      |___________|
#                  or dockerhub username

# push image

docker push {host}:{port}/nginx-image:0.1.0
#           |___________|
#       or dockerhub username

# run image

docker run --name nginx -d -p 8080:80 nginx-image

# run image and mount container

docker run --name nginx -d -p 8080:80 --volume //c/Users/path/to/folder/with/index.html:/var/www/html nginx-image
```

## Dockerfile

```dockerfile
FROM ubuntu:20.04

RUN apt update
RUN apt -y install nginx

COPY ./test.html /var/www/html/index.html

CMD ["/bin/bash", "-c", "nginx -g \"daemon off;\""]
```
