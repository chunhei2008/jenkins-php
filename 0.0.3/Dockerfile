FROM chunhei2008/jenkins-php:0.0.2

USER root

RUN docker-php-source extract \
    && docker-php-ext-install -j$(nproc) pcntl \
    && docker-php-source delete

RUN composer config -g repo.packagist composer https://packagist.phpcomposer.com
RUN composer require phpunit/phpunit --prefer-source --no-interaction 
RUN composer require phpunit/php-invoker --prefer-source --no-interaction 
RUN ln -s /vendor/bin/phpunit /usr/local/bin/phpunit 

USER jenkins
