FROM debian:buster

RUN apt-get update ; apt-get -y install php7.3 php-mysqli php-fpm mariadb-client
COPY ./conf/www.conf /etc/php/7.3/fpm/pool.d
COPY ./conf/wp-config.php ./var/www/wordpress/

ADD https://ru.wordpress.org/wordpress-5.7.2-ru_RU.tar.gz /var/www/
RUN cd /var/www && tar -xzvf wordpress-5.7.2-ru_RU.tar.gz 
RUN	rm -f /var/www/wordpress-5.7.2-ru_RU.tar.gz 
RUN	rm -f /var/www/wordpress/wp-config-sample.php 
RUN mkdir ./run/php/

CMD ./usr/sbin/php-fpm7.3 -F