ARG PHP_VERSION
FROM php:${PHP_VERSION}-fpm-alpine

WORKDIR /var/www/html

# Install php extention
RUN docker-php-ext-install pdo pdo_mysql mysqli

# Install Node.js and npm
RUN apk add --no-cache nodejs npm

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer
