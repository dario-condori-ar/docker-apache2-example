FROM php:7.3-apache-stretch
LABEL maintainer="plugins@omv-extras.org"


RUN apt-get update \
  && DEBIAN_FRONTEND=noninteractive apt-get install -y \
  libc6 libstdc++6 libkrb5-3 libcurl3 openssl debconf \
  libfreetype6-dev libjpeg-dev libpng-dev \
  && docker-php-ext-install mysqli pdo_mysql \
  && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
  && docker-php-ext-install gd \
  && apt-get clean \
  && rm -r /var/lib/apt/lists/*

COPY  . /var/www/html/
WORKDIR /var/www/html/