FROM php:5.6-apache
MAINTAINER Anton Anuchin <anychin@gmail.com>

RUN apt-get update && apt-get install -y \
  libbz2-dev \
  libfreetype6-dev \
  libgd-dev \
  libjpeg62-turbo-dev \
  libmcrypt-dev \
  libpng16-16 \
  libxml2-dev \
  zlib1g-dev \
  nano \
  && docker-php-ext-install iconv mbstring mcrypt soap sockets zip \
  && docker-php-ext-configure gd --enable-gd-native-ttf --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
  && docker-php-ext-install gd \
  && docker-php-ext-install session \
  && docker-php-ext-install mbstring \
  && docker-php-ext-configure mysql --with-mysql=mysqlnd \
  && docker-php-ext-install mysql

#COPY php.ini /usr/local/etc/php/

RUN a2enmod rewrite
RUN a2enmod session
