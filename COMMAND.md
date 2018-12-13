# Docker commands

Build image:

	docker build -t <image_name> .
	
Build image with args:

	docker build -t <image_name> --build-arg ARG_1=aa --build-arg ARG_2=bb .

Remove build image:

	docker rmi <image_name/image_id>

Force remove build image:

	docker rmi -f <image_name/image_id>
	
Get all images:

	docker images
	docker image ls
	
Run docker image:

	docker run -it -p 1399:139 -p 4455:445 --name=<container_name> <image_name/image_id>

Run dettached docker image:

	docker run -d -it --name=<container_name> <image_name/image_id>

Run docker image with ports exported:

	docker run -it -p <host_port>:<container_port> --name=<container_name> <image_name/image_id>
	
Run docker image with volume attached:

	docker run -it -v <host_path>:<container_path> --name=<container_name> <image_name/image_id>
	
Run fresh docker image:

	docker run -it --rm --name=<container_name> <image_name/image_id>
	
Get all docker containter:

	docker ps

Remove container:

	docker rm <container_name/container_id>

Force remove container:

	docker rm -f <container_name/container_id>

Get into containter:

	docker exec -it <container_name/container_id> /bin/bash

Stop container:

	docker stop <container_name/container_id>

Get all container infos:

	docker inspect <container_name/container_id>
	
Get container IP address (debian 9):

	docker inspect <container_name/container_id> | grep "IPAddress"
	
Run commands into container:

	docker exec -it <container_name/container_id> ls -l

	
## Ref

- [How do I run a command on an already existing Docker container?](https://stackoverflow.com/questions/26153686/how-do-i-run-a-command-on-an-already-existing-docker-container)
- [Use volumes](https://docs.docker.com/storage/volumes/#choose-the--v-or---mount-flag)



