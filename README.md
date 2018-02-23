# radare2-docker

[![Build Status](https://travis-ci.org/0xBANANA/radare2-docker.png?branch=master)](https://travis-ci.org/0xBANANA/radare2-docker)


Easy to use image for radare2, configurate using the `Makefile`.

Example usage:

```
touch $PWD/radare2rc && \
mkdir -p $PWD/r2-config && \
mkdir -p $PWD/sharedFolder && \
xhost +local:root && \
sudo docker run \
    -it \
    --name r2 \
    --cap-drop=ALL  \
    --cap-add=SYS_PTRACE \
    -e DISPLAY=$DISPLAY \
    -v /tmp/.X11-unix:/tmp/.X11-unix:ro \
    -v $PWD/sharedFolder:/var/sharedFolder \
    -v $PWD/radare2rc:/home/r2/.radare2rc \
    -v $PWD/r2-config:/home/r2/.config/radare2 \
    -v $PWD/workdir:/home/r2/workdir \
bananafett/radare2-docker:latest
```
