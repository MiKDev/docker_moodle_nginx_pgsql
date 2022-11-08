FROM php:8.0-fpm

RUN apt-get update && apt-get install -y \
    libpq-dev \
    libpng-dev \
    zlib1g-dev \
    libicu-dev \
    libzip-dev \
    libxml2-dev \
    zip \
    ghostscript

RUN docker-php-ext-install -j$(nproc) pdo pdo_pgsql pgsql gd intl zip xml opcache soap \
    && docker-php-source delete

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"