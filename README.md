[![Build Status](https://drone.stigler.de/api/badges/patrickstigler/docker-obs-ndi/status.svg)](https://drone.stigler.de/patrickstigler/docker-obs-ndi)
# Docker Open Broadcaster Software (OBS)
This container is based on [bb12489/docker-obs](https://github.com/bb12489/docker-obs). The OBS with NDI is incorporated into the container and can be used to stream your desktop.

I rebuiled the container on the base of [accetto/ubuntu-vnc-xfce-g3](https://github.com/accetto/ubuntu-vnc-xfce-g3) to have a regualar updated base image.

Here is a screenshot:
![Alt](https://raw.githubusercontent.com/patrickstigler/docker-obs-ndi/master/screenshot.png "Example screenshot")

# To run
You can start the container with:

`docker run --shm-size=256m -it -p 5901:5901 -p 6901:6901 -p 4455:4455 patrickstigler/obs-ndi:latest`

The shm-size argument is to make sure that the webclient does not run out of shared memory and crash. 

The VNC password is "headless"

You can connect with your own VNC client via 5901 or use the webclient at 6901

To enable GPU Support also add -e NVIDIA_VISIBLE_DEVICES=<your GPU ID> -e NVIDIA_DRIVER_CAPABILITIES=all and also add --runtime=nvidia as extra parameter.
