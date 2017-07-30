FROM chunhei2008/jenkins-php:0.0.4

USER root

RUN pecl install xdebug-2.5.0 \
    && docker-php-ext-enable xdebug

RUN composer require phpunit/dbunit --prefer-source --no-interaction \
    && ln -s /vendor/bin/dbunit /usr/local/bin/dbunit

USER jenkins
