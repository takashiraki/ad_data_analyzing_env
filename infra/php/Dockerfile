FROM php:8.1-fpm

RUN apt-get update \
  && apt-get install -y unzip libpq-dev \
  && pecl install xdebug \
  && docker-php-ext-enable xdebug \
  && docker-php-ext-install pgsql pdo_pgsql opcache

COPY --from=composer /usr/bin/composer /usr/bin/composer

COPY php.ini /usr/local/etc/php/

WORKDIR /var/www/html/
