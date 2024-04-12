#BASE IMAGE FROM DOCKERHUB
FROM alpine:latest

# TO INSTALL CURL
RUN apk add curl

# DIRECTORY OF YOUR CONTAINTER
WORKDIR /var/www/my_app 

# FOR CREATiNG USER 
RUN  adduser -D raemond

USER raemond
