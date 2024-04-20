FROM ubuntu:22.04

LABEL version="1" description="My Dockerfile" maintainer="raemond@gmail.com"

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && apt install -y tcl

# Install Apache and PHP
RUN apt-get install -y \
    apache2 \
    php \
    libapache2-mod-php \
    nano

COPY code /var/www/html


# Expose port 80
EXPOSE 80
    
# Start Apache on container startup
CMD ["apache2ctl", "-D", "FOREGROUND"]
