FROM php:8.4-fpm
# Workdir for image
WORKDIR /var/www/html

RUN apt-get update && apt-get install -y \
    git unzip curl libzip-dev libpng-dev libxml2-dev libonig-dev libxslt-dev libicu-dev libfreetype6-dev \
    zlib1g-dev libjpeg-dev
RUN docker-php-ext-configure gd --with-freetype --with-jpeg 
RUN docker-php-ext-install pdo_mysql mbstring zip intl xsl bcmath soap ftp gd sockets mysqli exif
RUN pecl install -f xmlrpc

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

