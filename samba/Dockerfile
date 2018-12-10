FROM debian:stretch
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get -q -y update
RUN apt-get -q -y upgrade

# New user (local)
ARG DK_SB_LOCAL_PASS

# New user (local) password
ARG DK_SB_LOCAL_USER

# New samba user password 
ARG DK_SB_PASS

# Create new user and samba shares directory
RUN useradd -ms /bin/bash -p $DK_SB_LOCAL_PASS $DK_SB_LOCAL_USER
RUN mkdir /home/$DK_SB_LOCAL_USER/shares
RUN chown -R $DK_SB_LOCAL_USER:$DK_SB_LOCAL_USER /home/$DK_SB_LOCAL_USER/shares/

# Install and config samba
RUN apt-get -q -y install samba samba-common-bin
RUN sed -ie '0,/read only = yes/s/read only = yes/read only = no/' /etc/samba/smb.conf

# Create new samba user
RUN (echo $DK_SB_PASS; echo $DK_SB_PASS) | smbpasswd -s -a $DK_SB_LOCAL_USER

# Expose samba port
EXPOSE 137/udp 138/udp 139 445

# Add start samba script
ADD start.sh /usr/local/bin/start.sh

# Tricks to avoid exiting the container just after running the script (CMD)
CMD bash -C '/usr/local/bin/start.sh';'bash'