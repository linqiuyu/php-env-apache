FROM php:5.6-apache

COPY docker-php-entrypoint /usr/local/bin/

RUN apt-get update && apt install -y libpng-dev libjpeg-dev libjpeg62-turbo-dev libmcrypt-dev redis-server vim && \
    docker-php-ext-configure gd --with-freetype --with-jpeg-dir && \
    docker-php-ext-install bcmath calendar gd mcrypt mysql mysqli pdo pdo_mysql zip && \
    pecl install http://pecl.php.net/get/redis-4.3.0.tgz && \
    pecl install http://pecl.php.net/get/xdebug-2.5.5.tgz