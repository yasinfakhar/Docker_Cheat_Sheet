# Docker_Cheat_Sheet
This repo contain useful and necessary commands in docker
<hr>

export image

origin : `sudo docker save -o {image-name-optional:}.tar {image-name}`

destination : `sudo docker load < {image-name-optional:}.tar`
<hr>
save changes (commit)

`sudo docker commit [CONTAINER_ID] [new_image_name]`
<hr>
