FROM php:8.4-fpm
# Workdir for image
WORKDIR /var/www/html

RUN apt-get update && apt-get install -y \
    git unzip curl libzip-dev libpng-dev libxml2-dev libonig-dev libxslt-dev libicu-dev libfreetype6-dev \
    zlib1g-dev libjpeg-dev 
RUN docker-php-ext-configure gd --with-freetype --with-jpeg 
RUN docker-php-ext-install pdo_mysql mbstring zip intl xsl bcmath soap ftp gd sockets

# # Copy files from first image
# COPY --from=prebuild-fpm /var/www/html /opt/html

# # script to deploy files to volume
# COPY init-magento.sh /usr/local/bin/init-magento.sh
# RUN chmod +x /usr/local/bin/init-magento.sh
# CMD ["/usr/local/bin/init-magento.sh"]
# RUN echo "memory_limit=512M" > /usr/local/etc/php/conf.d/99-custom.ini

LABEL org.opencontainers.image.source=https://github.com/tsmu-hub/moodle-docker-php