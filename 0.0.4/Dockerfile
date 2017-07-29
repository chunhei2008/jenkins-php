FROM chunhei2008/jenkins-php:0.0.3

USER root

RUN composer require squizlabs/php_codesniffer --prefer-source --no-interaction \
    && ln -s /vendor/bin/phpcs /usr/local/bin/phpcs \
    && ln -s /vendor/bin/phpcbf /usr/local/bin/phpcbf

RUN composer require sebastian/phpcpd --prefer-source --no-interaction \
    && ln -s /vendor/bin/phpcpd /usr/local/bin/phpcpd

RUN apt-get update; \
    apt-get install -y --no-install-recommends libxslt-dev; \

RUN docker-php-source extract \
    && docker-php-ext-install -j$(nproc) xsl \
    && docker-php-source delete

RUN composer require theseer/phpdox --prefer-source --no-interaction \
    && ln -s /vendor/bin/phpdox /usr/local/bin/phpdox

RUN composer require pdepend/pdepend --prefer-source --no-interaction \
    && ln -s /vendor/bin/pdepend /usr/local/bin/pdepend

RUN composer require phploc/phploc --prefer-source --no-interaction \
    && ln -s /vendor/bin/phploc /usr/local/bin/phploc

RUN composer require phpmd/phpmd --prefer-source --no-interaction \
    && ln -s /vendor/bin/phpmd /usr/local/bin/phpmd


USER jenkins
