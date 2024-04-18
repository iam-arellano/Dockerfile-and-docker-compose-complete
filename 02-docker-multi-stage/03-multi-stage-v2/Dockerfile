FROM php:8.2.18-apache as builder

# # COPY apache2.conf /etc/apache2/sites-available/000-default.conf

# RUN a2enmod rewrite

WORKDIR /var/www/html

COPY index.php .

RUN chmod -R 755 .



FROM ubuntu:latest

## update and install  region
ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install -y tcl

## install apache2
RUN apt-get update && apt-get install -y \
    apache2 \
    php \
    libapache2-mod-php \
    nano

COPY apache2.conf /etc/apache2/sites-available/000-default.conf
RUN a2enmod rewrite


# WORKDIR /var/www/html

COPY --from=builder /var/www/html /var/www/html

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]