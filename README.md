# Alpine Builder For LXD and DOCKER

***
## BIG UPDATE:
I maded one file which can build alpine for LXD and DOCKER!
****

Alpine Builder container for lxd or docker container. Usually used in pentesting, exactly docker and lxd group permission.
Based on [lxd-alpine-builder](https://github.com/saghul/lxd-alpine-builder/) for Saghul.

[Alpine Linux](http://alpinelinux.org/) images for their use with [LXD](https://linuxcontainers.org/lxd/) and [DOCKER](https://docker.com/).

The image will be built just by installing the `alpine-base` and `bash packgs` meta-package.
Networking and syslog are enabled by default.

## Usage:

### For LXD:

In order to build the latest Alpine image just run the script (must be done as root):

    sudo ./build-alpine

For more options check the help:

    sudo ./build-alpine -h

After the image is built it can be added as an image to LXD as follows:

    lxc image import alpine-{version}-{arch}-{date-and-time}.tar.gz metadata.tar.gz --alias alpine-v3.3

### For Docker:

First build latest image like that:

    sudo ./build-alpine

For help:

    sudo ./build-alpine -h

After building image an **Dockerfile** WILL BE created, you should run it like that:

    docker build . -t $USER/alpine:0.1
