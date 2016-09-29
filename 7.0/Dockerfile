FROM php:7.0.1111-apache
RUN apt-get update \
    && apt-get install -y libcurl4-gnutls-dev libpng12-dev libpq-dev libmcrypt-dev --no-install-recommends \
    && rm -rf /var/lib/apt/lists/* \
    && a2enmod rewrite \
    && docker-php-ext-install curl pdo_pgsql pdo_mysql pgsql mcrypt bcmath zip gd mbstring \
    && pecl install -o -f apcu \
    && rm -rf /tmp/pear \
    && echo "extension=/usr/local/lib/php/extensions/no-debug-non-zts-20151012/apcu.so" > /usr/local/etc/php/conf.d/apcu.ini \
COPY ./php.ini /usr/local/etc/php/
