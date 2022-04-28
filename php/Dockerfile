FROM php:5.6-apache

COPY docker-php-entrypoint /usr/local/bin/

RUN apt-get update && apt install -y libpng-dev libmcrypt-dev redis-server vim && \
    docker-php-ext-install bcmath calendar gd mcrypt mysql mysqli pdo pdo_mysql zip && \
    pecl install http://pecl.php.net/get/redis-4.3.0.tgz && \
    pecl install http://pecl.php.net/get/xdebug-2.5.5.tgz && \
    chmod +x docker-php-entrypoint

ENTRYPOINT ["docker-php-entrypoint"]