FROM chunhei2008/jenkins-php:0.0.5

USER root

RUN apt-get update \
    && apt-get install -y --no-install-recommends ant \
    && rm -r /var/lib/apt/lists/*


USER jenkins
