# Install docker (debian 9)

Remove old docker version and update package index:
	apt-get remove docker docker-engine docker.io
	apt-get update
	
Install extra package:
	apt-get install apt-transport-https 
	apt-get install ca-certificates
	apt-get install	curl -y
	apt-get install	software-properties-common -y
	
Configure Docker repository:
	echo "deb https://download.docker.com/linux/debian stretch stable" | tee /etc/apt/sources.list.d/docker.list
	
Download and import public key used to sign this repository:
	wget --quiet --output-document - https://download.docker.com/linux/debian/gpg  | apt-key add -
	
Update package index:
	apt-get update
	
Install Docker CE:
	apt-get install docker-ce
	
Add current user to the docker group:
	sudo usermod -aG docker $(whoami)

Re-login and run hello-world image to verify that application container engine is correctly installed:
	docker run hello-world

## Ref
- [How to install Docker on Debian Stretch](https://blog.sleeplessbeastie.eu/2018/03/30/how-to-install-docker-on-debian-stretch/)