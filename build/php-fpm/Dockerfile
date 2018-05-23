FROM php:7.2-fpm

LABEL maintainer="Nathan Daly <justlikephp@gmail.com>"

# Install developer dependencies
RUN apt-get update -yqq && apt-get install -y zlib1g-dev libpq-dev libxml2-dev bison \
    libsqlite3-dev libxml2-dev libicu-dev libfreetype6-dev libmcrypt-dev libreadline-dev \
    libjpeg62-turbo-dev libpng-dev libcurl4-gnutls-dev libbz2-dev libssl-dev -yqq

# Install PECL extensions
RUN pecl install mcrypt-1.0.1
RUN pecl install xdebug

# Install php extensions
RUN docker-php-ext-install pdo_mysql pdo_sqlite opcache json \
    calendar bcmath bcmath xml zip bz2 curl intl

# Enable PHP extensions
RUN docker-php-ext-enable mcrypt xdebug

# Configure XDebug
COPY xdebug.ini /etc/php/7.2/apache2/conf.d/20-xdebug.ini
