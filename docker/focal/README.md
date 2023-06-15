# Building
docker build -t local/rtabmap:rtabmap_opencl_new --progress=plain -f docker/focal/Dockerfile_opencl . | tee build_`date +%Y%m%d_%H%M`.log
# Running
xhost local:$USER
docker run --privileged -v /home/alison/:/home/host -v /dev/bus/usb:/dev/bus/usb -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=:0.0 -e WAYLAND_DISPLAY=wayland-0 -e XDG_RUNTIME_DIR=/mnt/wslg/runtime-dir -e PULSE_SERVER=/mnt/wslg/PulseServer --device=/dev/dri:/dev/dri --name rtabmap --rm local/opencl_test rtabmap

