
FROM php:7.1.17-apache
LABEL maintainer="Daro"

RUN a2enmod rewrite

RUN apt-get update
RUN apt-get install -y zlib1g-dev
RUN apt-get install -y libicu-dev 
RUN apt-get install -y libxml2-dev
RUN apt-get install -y libpq-dev
RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
RUN docker-php-ext-install pdo pdo_mysql pdo_pgsql zip intl xmlrpc soap opcache \
RUN docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd \
RUN apt-get install vim -y

COPY  . /var/www/html/
WORKDIR /var/www/html/