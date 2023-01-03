

## From Docker Hub bring a Registry image
```shell
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

The `docker run` command is used to run a container from a Docker image. The `-d` flag runs the container in detached mode, which means it will run in the background and the command prompt will be returned to you. The `-p` flag binds the container's ports to the host machine. In this case, the `5000:5000` argument binds the container's port 5000 to port 5000 on the host machine.

The `--restart=always` flag tells Docker to automatically restart the container if it exits or stops for any reason. This can be useful for ensuring that the container is always running.

The `--name` flag **assigns a name** to the container. In this case, the name is `registry`. This can be used to reference the container in other Docker commands.

The `registry:2` argument specifies the image to use for the container. The `registry` part specifies the repository, and the `2` part specifies the tag. In this case, the image is the `registry:2` image, which is a pre-built image containing the Docker Registry software.


