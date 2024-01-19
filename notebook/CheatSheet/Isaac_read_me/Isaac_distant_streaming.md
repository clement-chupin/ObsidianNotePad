

Based on :
https://docs.omniverse.nvidia.com/isaacsim/latest/installation/install_container.html#isaac-sim-setup-remote-headless-container


### Server :

![[Screenshot from 2024-01-16 17-20-51.png|800]]

bzBoZmQ2NHUzbGgwNnM2MHBzdW0ycjIzODg6OThiOTQzZTEtZGQ3Ny00YjBjLTgxYzktMjAyYTY4N2Y1MTlm


```bash 
hostname -I #get server ip
docker login nvcr.io
docker pull nvcr.io/nvidia/isaac-sim:2023.1.1
docker run --name isaac-sim --entrypoint bash -it --gpus all -e "ACCEPT_EULA=Y" --rm --network=host \
    -e "PRIVACY_CONSENT=Y" \
    -v ~/docker/isaac-sim/cache/kit:/isaac-sim/kit/cache:rw \
    -v ~/docker/isaac-sim/cache/ov:/root/.cache/ov:rw \
    -v ~/docker/isaac-sim/cache/pip:/root/.cache/pip:rw \
    -v ~/docker/isaac-sim/cache/glcache:/root/.cache/nvidia/GLCache:rw \
    -v ~/docker/isaac-sim/cache/computecache:/root/.nv/ComputeCache:rw \
    -v ~/docker/isaac-sim/logs:/root/.nvidia-omniverse/logs:rw \
    -v ~/docker/isaac-sim/data:/root/.local/share/ov/data:rw \
    -v ~/docker/isaac-sim/documents:/root/Documents:rw \
    nvcr.io/nvidia/isaac-sim:2023.1.1

#Inside the docker
./runheadless.native.sh -v
```


Client : 
- 1 : Launch "Nvidia Streaming Client" in the Omniverse launcher
- 2 : specify the server ip 

ssh connection : 
You might directly connect to the server with ssh
```
ssh your_username@the_server_ip
```
