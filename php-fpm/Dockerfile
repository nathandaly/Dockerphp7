FROM php:7.2-fpm

MAINTAINER Nathan Daly <justlikephp@gmail.com>

# Install developer dependencies
RUN apt-get update -yqq && apt-get install -y zlib1g-dev libpq-dev libxml2-dev bison \
    libsqlite3-dev libxml2-dev libicu-dev libfreetype6-dev libmcrypt-dev libreadline-dev \
    libjpeg62-turbo-dev libpng-dev libcurl4-gnutls-dev libbz2-dev libssl-dev -yqq

# Install php extensions
RUN docker-php-ext-install pdo_mysql pdo_sqlite opcache json \
    calendar bcmath bcmath xml zip bz2 curl intl

# Install PECL extensions
RUN pecl install xdebug
RUN pecl install mcrypt-1.0.1
RUN docker-php-ext-enable xdebug
RUN docker-php-ext-enable mcrypt