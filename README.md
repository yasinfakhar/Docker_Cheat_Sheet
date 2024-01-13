# Docker_Cheat_Sheet
This repo contain useful and necessary commands in docker
<hr>

<h2>export image</h2>

origin : `sudo docker save -o [OPTIONAL_IMAGE_NAME].tar [IMAGE_NAME:TAG]`

destination : `sudo docker load < [OPTIONAL_IMAGE_NAME].tar`
<hr>
<h2>save changes (commit)</h2>
<hr>

`sudo docker ps -a` for getting the last container id

`sudo docker commit [CONTAINER_ID] [NEW_IMAGE_NAME:TAG]`
<hr>
<h2>remove image</h2>

`sudo docker rmi --force [IMAGE_NAME:TAG]` or `sudo docker rmi --force [IMAGE_ID]`
<hr>
<h2>run with connecting all ports & use GPUs & use display & connect a volume</h2>

`xhost +local:docker`

`sudo docker run -it --gpus all  --net host -v "path_to_location_in_local_machine":"/resource" -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix [IMAGE_NAME:TAG]`
<hr>
