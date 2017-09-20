FROM php:7.1-fpm

MAINTAINER Ahmed Tailouloute <ahmed.tailouloute@gmail.com>

RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-install bcmath

# Install Composer
RUN apt-get update -y \
    && php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +sx /usr/local/bin/composer \
    && php -r "readfile('https://yt-dl.org/downloads/latest/youtube-dl');" >> /usr/local/bin/youtube-dl \
    && chmod +x /usr/local/bin/youtube-dl \
    && apt-get install python -y \
    && apt-get install git -y \
    && apt-get install -y libav-tools

RUN usermod -u 1000 www-data

WORKDIR /var/www/symfony