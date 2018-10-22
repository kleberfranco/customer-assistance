FROM composer

FROM php:7.2-fpm-alpine

COPY --from=0 /usr/bin/composer /usr/bin/composer

RUN apk add --no-cache \
        libmcrypt-dev \
        freetype \
        libpng \
        libjpeg-turbo \
        freetype-dev \
    && docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) \
        bcmath \
        mbstring \
        opcache \
        pdo_mysql \
        gd

WORKDIR /app
ADD app /app