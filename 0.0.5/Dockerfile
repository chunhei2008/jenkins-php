FROM chunhei2008/jenkins-php:0.0.4

USER root

RUN pecl install xdebug-2.5.0 \
    && docker-php-ext-enable xdebug

USER jenkins
