FROM debian:jessie

MAINTAINER Ahmed Tailouloute <ahmed.tailouloute@gmail.com>

RUN apt-get update && apt-get install -y nginx

ADD nginx.conf /etc/nginx/
ADD symfony.conf /etc/nginx/sites-available/
ADD symfony.conf /etc/nginx/sites-enabled/

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443