FROM php:8.2-apache

RUN a2enmod rewrite

RUN apt-get update \
  && apt-get install -y libzip-dev git libpq-dev unzip wget --no-install-recommends \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN docker-php-ext-install pdo mysqli pdo_mysql pgsql pdo_pgsql zip;

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --2

WORKDIR /var/www/html/app

CMD ["apache2-foreground"]
