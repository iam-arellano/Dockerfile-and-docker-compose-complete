# Use the official Ubuntu base image
FROM ubuntu:latest


ENV DEBIAN_FRONTEND noninteractive

RUN apt update && apt install -y tcl

# Install Apache and PHP
RUN apt-get -f install -y apache2 php libapache2-mod-php

COPY code/* /var/www/html/



# Expose port 80
EXPOSE 80

# Start Apache on container startup
CMD ["apache2ctl", "-D", "FOREGROUND"]
