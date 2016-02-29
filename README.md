Zephyr Project Docker Image
---

This docker image makes it easy to get going with building and running apps based
on the [Zephyr Project](http://zephyrproject.org) RTOS from the Linux Foundation

### What's included

* Based on v0.9.18 of phusion's modified ubuntu [baseimage](https://github.com/phusion/baseimage)
* Zephyr SDK v0.7.2 installed at `/opt/zephyr-sdk` (can be overridden and rebuilt with the build argument `SDK_VERSION`)
* python / make / gcc and friends

### Example w/ Hello World

1. Clone Zephyr Project and Download the docker image

        $ cd ~
        $ git clone https://gerrit.zephyrproject.org/r/zephyr zephyr-project
        $ docker pull marshallc/zephyr-project

2. Build and run the `hello_world` example in qemu

        $ cd ~/zephyr-project
        $ docker run -v $PWD:/build -w /build/samples/microkernel/apps/hello_world -it marshallc/zephyr-project make qemu
