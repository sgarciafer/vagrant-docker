FROM drupal:8.2.5-apache

MAINTAINER Sergio Garcia <s.garcia.fe@gmail.com>

RUN apt-get update \
    && apt-get install -y nano git vim 

RUN curl -fSL "http://files.drush.org/drush.phar" -o /usr/local/bin/drush \
    && chmod +x /usr/local/bin/drush

WORKDIR /var/www/html
