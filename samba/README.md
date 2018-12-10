# Samba
Run a simple samba server with docker

### Build image
Build samba image with `Dockerfile` arguments (don't forget to replace `<arg>` value):
	docker build -t samba --build-arg DK_SB_LOCAL_PASS=<user (local) password> --build-arg DK_SB_LOCAL_USER=<user (local) password> --build-arg DK_SB_PASS=<samba user password > .
	
### Run container
Run detached container with samba image:
	docker run -d -it -p 139:139 -p 445:445 -p 137:137/udp -p 138:138/udp -v /home/samba/shares:/home/samba/shares --name=smb samba
	
### Get into container
	docker exec -it smb /bin/bash
	
### Remove container
	docker rm -f smb
	
### Remove samba and debian images 
	docker rmi -f samba:latest
	docker rmi -f debian:stretch
	
	

