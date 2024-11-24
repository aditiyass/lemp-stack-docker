FROM php:5.6-fpm-alpine

# Install dependencies for GD and install GD with support for jpeg, png webp and freetype
# Info about installing GD in PHP https://www.php.net/manual/en/image.installation.php
RUN apk add --no-cache \
        git \
        zlib \
        libjpeg-turbo-dev \
        libpng-dev \
        libwebp-dev \
        freetype-dev \
		imagemagick \
		imagemagick-libs \
		imagemagick-dev \
		socat

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions gd bcmath bz2 calendar intl mysqli pdo_mysql pgsql pdo_pgsql snmp soap sockets zip

RUN chmod 777 /tmp

# RUN socat TCP-LISTEN:80,fork TCP:10.10.10.10:80 &
