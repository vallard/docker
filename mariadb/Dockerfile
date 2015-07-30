FROM vallard/nginx
MAINTAINER Vallard Benincosa "vallard@benincosa.com"
# install MariaDB

#RUN debconf-set-selections << "mariadb-server mysql-server/root_password password $SECRET_PASSWORD"
#RUN debconf-set-selections << "mysql-server mysql-server/root_password_again password $SECRET_PASSWORD"
RUN apt-get update \
  && apt-get install -y mariadb-server mariadb-client libmariadbclient-dev \
  && rm -rf /var/lib/mysql/mysql \ 
  && rm -rf /var/lib/apt/lists/* # as seen in sameersbn/docker-mysql

ADD start /start
RUN chmod 755 /start

EXPOSE 3306

VOLUME ["/var/lib/mysql"]
VOLUME ["/run/mysqld"]

CMD ["/start"]
