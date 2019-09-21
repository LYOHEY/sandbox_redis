FROM php:7.3-apache
COPY php.ini /usr/local/etc/php/
RUN  a2enmod rewrite

RUN apt-get update \
    && apt-get install -y libicu-dev git unzip libzip-dev libssl-dev openssl ssl-cert curl gnupg vim \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && a2enmod ssl \
    && a2ensite default-ssl

RUN git clone https://github.com/phpredis/phpredis.git /usr/src/php/ext/redis 

RUN docker-php-ext-install intl pdo_mysql mbstring zip redis

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sL https://deb.nodesource.com/setup_11.x | bash -
RUN apt-get install -y nodejs
RUN npm install npm@latest -g
