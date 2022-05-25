FROM php:7.2-apache

RUN a2enmod rewrite

RUN apt-get update \
  && apt-get install -y libzip-dev git wget --no-install-recommends \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN docker-php-ext-install pdo mysqli pdo_mysql zip;

RUN php -r "copy('https://getcomposer.org/download/latest-1.x/composer.phar', '/usr/local/bin/composer');" \
    && chmod 755 /usr/local/bin/composer

COPY apache.conf /etc/apache2/sites-enabled/000-default.conf

WORKDIR /var/www

CMD ["apache2-foreground"]