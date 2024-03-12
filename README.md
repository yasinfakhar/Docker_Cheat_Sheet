# Docker_Cheat_Sheet
This repo contains useful and necessary commands in docker

<h2>Install Docker with GPUS enabled in Linux</h2>

```
sudo apt-get update
sudo apt-get remove docker docker-engine docker.io
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
docker --version

# Put the user in the docker group
sudo usermod -a -G docker $USER
newgrp docker

# Nvidia Docker
sudo apt install curl
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker
```

<hr>

<h2>export image</h2>

origin : `sudo docker save -o [OPTIONAL_IMAGE_NAME].tar [IMAGE_NAME:TAG]`

destination : `sudo docker load < [OPTIONAL_IMAGE_NAME].tar`
<hr>
<h2>save changes (commit)</h2>

`sudo docker ps -a` for getting the last container id

`sudo docker commit [CONTAINER_ID] [NEW_IMAGE_NAME:TAG]`
<hr>
<h2>remove image</h2>

`sudo docker rmi --force [IMAGE_NAME:TAG]` or `sudo docker rmi --force [IMAGE_ID]`
<hr>
<h2>remove container</h2>
remove specific container 

`sudo docker container rm {CONTAINER_ID} --force` or `sudo docker container kill --sigal=SIGTERM {CONTAINER_ID}`

remove all stop containers

`sudo docker prune`

<hr>
<h2>run with connecting all ports & use GPUs & use display & connect a volume</h2>

`xhost +local:docker`

`sudo docker run -it --gpus all  --net host -v "path_to_location_in_local_machine":"/resource" -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix [IMAGE_NAME:TAG]`
<hr>
<h2>define share volume</h2>

`sudo docker volume create {folder_name}`

`sudo docker run ... -v /{folder_name}:{path_to_shared_folder_inside_docker} ...`




