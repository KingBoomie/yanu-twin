# Yanu simulator with isaac sim



## Installation

1. Follow the instructions [here](https://docs.omniverse.nvidia.com/app_isaacsim/app_isaacsim/install_container.html) to 
get the isaac container. 

2. Get an interactive shell in the container:
```docker run --name isaac-sim --entrypoint bash -it --gpus all -e "ACCEPT_EULA=Y" --rm --network=host \
    -v ~/docker/isaac-sim/cache/kit:/isaac-sim/kit/cache/Kit:rw \
    -v ~/docker/isaac-sim/cache/ov:/root/.cache/ov:rw \
    -v ~/docker/isaac-sim/cache/pip:/root/.cache/pip:rw \
    -v ~/docker/isaac-sim/cache/glcache:/root/.cache/nvidia/GLCache:rw \
    -v ~/docker/isaac-sim/cache/computecache:/root/.nv/ComputeCache:rw \
    -v ~/docker/isaac-sim/logs:/root/.nvidia-omniverse/logs:rw \
    -v ~/docker/isaac-sim/data:/root/.local/share/ov/data:rw \
    -v ~/docker/isaac-sim/documents:/root/Documents:rw \
    nvcr.io/nvidia/isaac-sim:2022.2.1
```

3. Start isaac sim with native livestream mode:
```
./runheadless.native.sh
```

4. git clone this repo to `~/docker/isaac-sim/documents/Kit/apps/Isaac-Sim/scripts`:
```bash
cd ~/docker/isaac-sim/documents/Kit/apps/Isaac-Sim/scripts
git clone TODO
cd repo
```

5. start roscore `source /opt/ros/noetic/setup.zsh && roscore`

6. in the container shell, run the script with the command:
```bash
source /opt/ros/noetic/setup.zsh && source ~/dev/yanu-workspace/devel/setup.zsh
./python.sh /root/Documents/Kit/apps/Isaac-Sim/scripts/repo/yanu.py
```

