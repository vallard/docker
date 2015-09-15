FROM ubuntu:latest
MAINTAINER Vallard Benincosa "vallard@benincosa.com"
RUN apt-get update
# install the software
RUN apt-get install -y python vim python-pip python-dev ssh nano curl

# Install OpenStack Clients
RUN pip install python-novaclient python-keystoneclient python-cinderclient python-heatclient python-glanceclient

RUN service ssh start

# make the .profile look awesome
ADD profile /etc/skel/.profile

# Add the users
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user01
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user02
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user03
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user04
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user05
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user06
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user07
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user08
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user09
RUN useradd -m -p $(openssl passwd -1 Cisco.123) user10


# make VIM awesome. 
ADD vimrc /root/.vimrc
ADD vimsettings /root/.vim


# add priv directory. 
RUN mkdir -p /var/run/sshd
RUN chmod 0755 /var/run/sshd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
