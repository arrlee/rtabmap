# Building
docker build -t local/opencl_test --progress=plain - 2>&1 < docker/focal/Dockerfile_opencl
# Running
xhost local:$USER
alison@usblnx001:~/rtabmap$ docker run -ti --privileged -v /home/alison/:/home/host -v /dev/bus/usb:/dev/bus/usb -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=:0.0 -e WAYLAND_DISPLAY=wayland-0 -e XDG_RUNTIME_DIR=/mnt/wslg/runtime-dir -e PULSE_SERVER=/mnt/wslg/PulseServer --device=/dev/dri:/dev/dri -v /dev/bus/usb:/dev/bus/usb --name rtabmap_realsense local/rtabmap:rtabmap_realsense rtabmap 

opencv_version --opencl
