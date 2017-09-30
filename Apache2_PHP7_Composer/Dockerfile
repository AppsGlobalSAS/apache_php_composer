FROM debian:jessie
ENV app /var/www
WORKDIR ${app}

RUN apt-get update && \
	apt-get -y install \
		ssh \
		wget \
		git \
		iputils-ping \
		cron \ 
		vim \ 
		apache2 \ 
		php \
		php-zip \
		php-mbstring \
		php-xml \
		php-pgsql \
		php-curl \
		php-gd && \
	apt-get -y autoremove && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* && \
	a2enmod ssl && \
	a2enmod rewrite

RUN wget https://getcomposer.org/composer.phar && chmod u+x composer.phar && mv composer.phar /usr/local/bin/composer

RUN dpkg-reconfigure locales && \
    locale-gen C.UTF-8 && \
    /usr/sbin/update-locale LANG=C.UTF-8

ENV LC_ALL C.UTF-8

