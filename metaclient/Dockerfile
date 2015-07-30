FROM ubuntu:latest
MAINTAINER Vallard Benincosa "vallard@benincosa.com"
RUN apt-get update
# install the software
RUN apt-get install -y python vim python-pip python-dev

# Install OpenStack Clients
RUN pip install python-novaclient python-keystoneclient python-cinderclient python-heatclient 

# make VIM awesome. 
ADD vimrc /root/.vimrc
ADD vimsettings /root/.vim
