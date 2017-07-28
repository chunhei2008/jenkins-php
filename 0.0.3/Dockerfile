FROM chunhei2008/jenkins-php:0.0.2

USER root

RUN composer require phpunit/phpunit --prefer-source --no-interaction \
    && composer require phpunit/php-invoker --prefer-source --no-interaction \
    && mv /tmp/vendor/bin/phpunit /usr/local/bin/phpunit \
    && chmod +x /usr/local/bin/phpunit

USER jenkins
