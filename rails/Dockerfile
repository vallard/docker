FROM vallard/nginx:v1
MAINTAINER Vallard Benincosa "vallard@benincosa.com"
# Ruby Setup
RUN apt-get install -y curl
RUN gpg --keyserver hkp://keys.gnupg.net --recv-keys D39DC0E3 && curl -L get.rvm.io | bash -s stable --rails
ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
RUN /bin/bash -l -c "rvm requirements"
RUN /bin/bash -l -c "rvm install 2.1"
RUN /bin/bash -l -c "gem install bundler --no-ri --no-rdoc"
