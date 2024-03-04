FROM php:8.2-fpm


# PHP extension
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions gd xdebug

RUN install-php-extensions \
        gd \
        intl \
        mbstring \
        mcrypt \
        pdo \
        pdo_mysql \
        xsl \
        zip \
        soap \
        bcmath

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
	php /usr/local/bin/composer self-update

RUN apt-get update && apt-get upgrade -y && apt-get autoremove -y

RUN apt-get autoremove -y && apt-get clean all
