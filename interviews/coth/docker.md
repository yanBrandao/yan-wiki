# Docker

`Q: How to make a docker inspect and what is it for?`

```
docker inspect [container_name]

Docker inspect provides detailed information on constructs controlled by Docker.

We can see something like running State, Environments, Cmd and Entrypoints for example.


```

https://docs.docker.com/reference/cli/docker/inspect/

`Q: How to create a Docker with name xxx and tag yyy;`

```
docker run --name [container_name] -d -p [exposed_port]:[internal_port] [image_name]:[version]

```

`Q: How to create a Dockerfile at regular intervals`

```
docker run --name [container_name] -d -p [exposed_port]:[internal_port] [image_name]:[version]

```

`Q: What is EXPOSE in Dockerfile?`

```
the EXPOSE instruction is used to document the network ports that a container listens on at runtime.

# Expose the HTTP port
EXPOSE 80
```