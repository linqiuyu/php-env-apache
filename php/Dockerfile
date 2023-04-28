FROM php:5.6-apache

COPY docker-php-entrypoint /usr/local/bin/
COPY composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer

#安装freetype扩展
COPY ext/freetype-2.7.1.tar.gz /usr/local/src/freetype-2.7.1.tar.gz
WORKDIR /usr/local/src/
RUN tar -zxvf  freetype-2.7.1.tar.gz
WORKDIR /usr/local/src/freetype-2.7.1
RUN ./configure --prefix=/usr/local/freetype && make && make install

RUN apt-get update && apt install -y libpng-dev libjpeg-dev libjpeg62-turbo-dev libmcrypt-dev redis-server vim ffmpeg memcached && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/local/freetype --with-jpeg-dir && \
    docker-php-ext-install bcmath calendar gd mcrypt mysql mysqli pdo pdo_mysql zip && \
    pecl install http://pecl.php.net/get/redis-4.3.0.tgz && \
    pecl install http://pecl.php.net/get/xdebug-2.5.5.tgz && \
    pecl install https://pecl.php.net/get/memcache-2.2.7.tgz && \
    pecl install https://pecl.php.net/get/imagick-3.7.0.tgz