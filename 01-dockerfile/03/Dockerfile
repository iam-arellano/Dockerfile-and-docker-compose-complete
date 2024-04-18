FROM ubuntu:22.04

RUN apt-get update && apt-get install -y


RUN useradd -ms /bin/bash raemond

USER raemond
WORKDIR /home/raemond

CMD  ["/bin/sh"]