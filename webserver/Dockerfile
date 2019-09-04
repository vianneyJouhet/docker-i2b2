FROM ubuntu:18.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install unzip apache2 -y
RUN apt-get update
RUN apt-get install php7.2 curl -y
RUN apt-get install php7.2-curl -y
RUN apt-get install libapache2-mod-php7.2 -y

RUN a2enmod php7.2
RUN a2enmod rewrite

ADD ./webclient/i2b2webclient.zip /opt/i2b2webclient.zip

ADD ./start.sh .
RUN chmod +x start.sh
ADD ./parametrage.sh .
RUN chmod +x parametrage.sh

RUN touch deployed
RUN echo 'false'>deployed

ENTRYPOINT ["./start.sh"]
