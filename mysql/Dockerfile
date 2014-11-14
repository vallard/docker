FROM vallard/rails
MAINTAINER Vallard Benincosa "vallard@benincosa.com"
# install MySQL
ENV SECRET_PASSWORD foobar
RUN debconf-set-selections <<< "mysql-server mysql-server/root_password password $SECRET_PASSWORD"
RUN debconf-set-selections <<< "mysql-server mysql-server/root_password_again password $SECRET_PASSWORD"
RUN apt-get install -qq -y mysql-server mysql-client libmysqlclient-dev

