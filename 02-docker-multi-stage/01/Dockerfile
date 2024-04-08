# Stage 1: Build PHP application
FROM php:8.1 AS php-builder
WORKDIR /app
COPY . .
RUN apt-get update && apt-get install -y \
    git \
    zip \
    && docker-php-ext-install pdo_mysql \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer install 

# Stage 2: Build Nginx image (final stage)
FROM nginx:latest
COPY --from=php-builder /app /usr/share/nginx/html
EXPOSE 80
