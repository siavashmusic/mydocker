FROM php:7.1-fpm

RUN apt-get update
RUN apt-get install -y g++

# pour ext intl
RUN apt-get install -y libicu-dev
RUN docker-php-ext-install intl

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
	php /usr/local/bin/composer self-update

RUN docker-php-ext-install pdo pdo_mysql


RUN apt-get install -y libmcrypt-dev
RUN docker-php-ext-install mcrypt

RUN apt-get install -y libxml2-dev
RUN docker-php-ext-install dom

RUN docker-php-ext-install gettext mbstring soap
RUN apt-get install -y zlib1g-dev
# Pour C&P et composer
RUN docker-php-ext-install zip

RUN apt-get autoremove -y && apt-get clean all
