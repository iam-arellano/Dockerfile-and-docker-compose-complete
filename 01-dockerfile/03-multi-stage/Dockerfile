# Stage 1: Build the PHP Apache image
FROM ubuntu:latest as builder


ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install -y tcl


## install apache2
RUN apt-get update && apt-get install -y \
    apache2 \
    php \
    libapache2-mod-php


WORKDIR /var/www/html

# copy the code to container
COPY index.php /var/www/html/

#give permission to folder
RUN chmod -R 755 .



# Stage 2: Create a lightweight image
FROM php:8.2.18-apache

COPY --from=builder /var/www/html /var/www/html

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]
