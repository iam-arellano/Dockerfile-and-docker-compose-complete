FROM ubuntu:22.04 as builder


ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install -y tcl

    # RUN apt-get update && apt-get install -y \
    # curl \
    # nano \
    # git \
    # wget \
    # iputils-ping

COPY . /var/www/html
RUN chown -R $USER:www-data /var/www/html/storage 
RUN chmod -R 775 /var/www/html/storage  



FROM php:8.1.6-apache

COPY --from=builder /var/www/html /var/www/html

RUN apt-get update && apt-get install -y \
    git \
    nano \
    iputils-ping

COPY apache2.conf /etc/apache2/sites-available/000-default.conf
RUN a2enmod rewrite

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions \
        && install-php-extensions mongodb


COPY --from=composer:2.5.4 /usr/bin/composer /usr/local/bin/composer

#port
EXPOSE 80

#run
CMD ["apache2ctl", "-D", "FOREGROUND"]