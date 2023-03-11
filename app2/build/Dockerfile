FROM php:8.0-apache

COPY . /var/www/html

RUN sed -i 's/80/8081/g' /etc/apache2/sites-available/000-default.conf /etc/apache2/ports.conf

EXPOSE 8081
