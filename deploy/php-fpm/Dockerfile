#使用微镜像
FROM php:7.0-fpm-alpine

MAINTAINER jeeinn thinkwei2012@gmail.com

# 更新
RUN apk update && apk upgrade \
    && apk add ca-certificates

# mcrypt 扩展
RUN apk add libmcrypt-dev \
    && docker-php-ext-install mcrypt

# gd 扩展
RUN apk add libjpeg-turbo-dev \
    && apk add libpng-dev \
    && docker-php-ext-install gd

# pdo_mysql 扩展
RUN docker-php-ext-install pdo_mysql

RUN rm -rf /var/cache/apk/*

# 配置php.ini, 项目中是默认的，可自行配置；移动至docker-compose.yml
#COPY config/php.ini /usr/local/etc/php/
