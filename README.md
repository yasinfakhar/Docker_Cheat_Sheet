# Docker_Cheat_Sheet
This repo contain useful and necessary commands in docker
<hr>

export image

origin : `sudo docker save -o [OPTIONAL_IMAGE_NAME].tar [IMAGE_NAME:TAG]`

destination : `sudo docker load < [OPTIONAL_IMAGE_NAME].tar`
<hr>
save changes (commit)

`sudo docker commit [CONTAINER_ID] [NEW_IMAGE_NAME]`
<hr>
remove image

`sudo docker rmi --force [IMAGE_NAME:TAG]`
<hr>
