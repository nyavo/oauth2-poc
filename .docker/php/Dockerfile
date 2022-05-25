FROM php:8.1-fpm-bullseye

# Composer
RUN apt-get update && apt-get install -y --no-install-recommends git unzip \
    && apt-get clean && rm -rf /var/lib/apt/lists/*
RUN php -r "copy('https://getcomposer.org/download/latest-2.x/composer.phar', '/usr/local/bin/composer');" \
    && chmod 755 /usr/local/bin/composer

# app requirements
RUN apt-get update && apt-get install -y --no-install-recommends \
    libicu-dev \
  && docker-php-ext-install pdo pdo_mysql \
  && docker-php-ext-install gettext \
  && docker-php-ext-configure intl \
  && docker-php-ext-install intl \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN echo 'memory_limit = 512M' > /usr/local/etc/php/conf.d/docker-php-custom.ini \
  && echo 'upload_max_filesize = 20M' >> /usr/local/etc/php/conf.d/docker-php-custom.ini \
  && echo 'post_max_size = 30M' >> /usr/local/etc/php/conf.d/docker-php-custom.ini

WORKDIR /oauth
