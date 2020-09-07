FROM php:fpm

RUN apt-get update \
    && apt-get install -y \
    libfreetype6-dev \
    libjpeg-dev \
    libpng-dev \
    && yes | pecl install xdebug \
    && docker-php-ext-configure gd \
    && docker-php-ext-install gd \
    && docker-php-ext-install mysqli \
    && docker-php-ext-enable mysqli

RUN echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini
