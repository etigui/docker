# Docker
Here you can find the folder with the script to build my docker images:

- [Install simple samba server](/samba/README.md)

## Build infos
All my images have successfully built with the following docker, debian and kernel version:

    $ docker -v
    Docker version 18.09.0, build 4d60db4

    $ lsb_release -a
    No LSB modules are available.
    Distributor ID: Debian
    Description:    Debian GNU/Linux 9.6 (stretch)
    Release:        9.6
    Codename:       stretch

    $ uname -a
    Linux pc-508 4.9.0-8-amd64 #1 SMP Debian 4.9.130-2 (2018-10-27) x86_64 GNU/Linux

## Install docker (debian 9)
If you don't have docker already installed on your computer, you can follow [this procedure](/INSTALL.md)

## Docker commands
If you are not used to type docker command, [here a bunch of exemple](/COMMAND.md)

## Ref
- [Learn Docker in 12 Minutes](https://www.youtube.com/watch?v=YFl2mCHdv24)
- [Docker Compose in 12 Minutes](https://www.youtube.com/watch?v=Qw9zlE3t8Ko)
- [Deploy Docker Containers with Docker Cloud](https://www.youtube.com/watch?v=F82K07NmRpk)
