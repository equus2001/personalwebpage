FROM ubuntu:18.04

ENV WEB https://github.com/equus2001/personalwebpage/archive/master.zip

RUN apt-get clean
RUN apt-get update
RUN apt-get install -y apache2
RUN apt-get install -y wget
RUN apt-get install -y unzip
RUN wget $WEB
RUN unzip master.zip -d /salida
RUN cp -a /salida/*/* /var/www/html/

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

ENTRYPOINT ["/usr/sbin/apache2ctl"]
CMD ["-D", "FOREGROUND"]

