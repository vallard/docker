FROM ubuntu:latest
MAINTAINER Vallard Benincosa "vallard@benincosa.com"
RUN apt-get update
# install the software
RUN apt-get install -y python vim python-pip python-dev ssh nano curl ansible bash-completion
RUN apt-get update
RUN apt-get install -y lxc docker docker.io iptables

# Install OpenStack Clients
RUN pip install python-novaclient python-keystoneclient python-cinderclient python-heatclient python-glanceclient

# make the .profile look awesome
ADD profile /etc/skel/.profile

# Add the users
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user01 
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user02
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user03
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user04
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user05
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user06
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user07
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user08
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user09
RUN useradd -m -G sudo -p $(openssl passwd -1 Cisco.123) -s /bin/bash user10


# make VIM awesome. 
ADD vimrc /root/.vimrc
ADD vimsettings /root/.vim


# add priv directory. 
RUN mkdir -p /var/run/sshd
RUN chmod 0755 /var/run/sshd

# add Jerome's docker magic
ADD ./wrapdocker /usr/local/bin/wrapdocker
RUN chmod +x /usr/local/bin/wrapdocker

# add the stuff
ADD ./startit /usr/local/bin/
RUN chmod +x /usr/local/bin/startit

VOLUME /var/lib/docker
EXPOSE 22
CMD ["/usr/local/bin/startit"]
