FROM centos:latest

RUN yum update  -y
RUN yum install java-11-openjdk -y

RUN mkdir /opt/tomcat

WORKDIR /opt/tomcat

ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.87/bin/apache-tomcat-9.0.87.tar.gz .

RUN tar -xvzf apache-tomcat-9.0.87.tar.gz

RUN mv apache-tomcat-9.0.87/*  /opt/tomcat

EXPOSE 8080

CMD [ "/opt/tomcat/bin/catalina.sh","run" ]