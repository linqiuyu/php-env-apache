FROM linqiuyu/php:5.6-apache-jancent

COPY ext/freetype-2.7.1.tar.gz /usr/local/src/freetype-2.7.1.tar.gz
WORKDIR /usr/local/src/
RUN tar -zxvf  freetype-2.7.1.tar.gz
WORKDIR /usr/local/src/freetype-2.7.1
RUN ./configure --prefix=/usr/local/freetype && make && make install

RUN apt install -y libmagick++-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/local/freetype --with-jpeg-dir && \
    pecl install https://pecl.php.net/get/imagick-3.7.0.tgz