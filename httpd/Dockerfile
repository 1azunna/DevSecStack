FROM httpd:2.4.46-alpine

LABEL Maintainer="Carbon Infrastructure Team <infrastructure@getcarbon.co>"

#Create apache user
RUN  addgroup -S apache && adduser -D -h /usr/local/apache2 -G apache apache 
RUN  chown -R apache:apache /usr/local/apache2


COPY httpd.conf /usr/local/apache2/conf
COPY . /usr/local/apache2/htdocs

RUN  chmod –R 750 bin conf

USER apache

