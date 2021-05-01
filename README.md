
# Alpine Builder For LXD and DOCKER


Alpine Builder container for lxd or docker container. Usually used in pentesting, exactly docker and lxd group permission.
Based on [lxd-alpine-builder](https://github.com/saghul/lxd-alpine-builder/) for Saghul.

[Alpine Linux](http://alpinelinux.org/)
images for their use with [LXD](https://linuxcontainers.org/lxd/) and [DOCKER](https://docker.com/).

The image will be built just by installing the `alpine-base` meta-package.
Networking and syslog are enabled by default.


## Usage

In order to build the latest Alpine image just run the script (must be done
as root):

    $ sudo ./build-alpine

For more options check the help:

    $ sudo ./build-alpine -h

After the image is built it can be added as an image to LXD as follows:

    $ lxc image import alpine-{version}-{arch}-{date-and-time}.tar.gz --alias alpine-v3.3

Or for DOCKER like that:

    $ docker import alpine-{version}-{arch}-{date-and-time}.tar.gz alpine-v3.3

