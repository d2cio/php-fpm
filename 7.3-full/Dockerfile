FROM d2cio/php-fpm:7.3-base

RUN set -x && \
#
	apt-get update && \
	apt-mark showmanual > /tmp/savedAptMark && \
#
	docker-php-source extract && \
# ext: bcmath
	docker-php-ext-install bcmath && \
# ext: bz2
	apt-get install -y --no-install-recommends libbz2-dev && \
	docker-php-ext-install bz2 && \
# ext: calendar
	docker-php-ext-install calendar && \
# ext: dba
	docker-php-ext-install dba && \
# ext: enchant
	apt-get install -y --no-install-recommends libenchant-dev && \
	docker-php-ext-install enchant && \
# ext: exif
	docker-php-ext-install exif && \
# ext: gd
	apt-get install -y --no-install-recommends libjpeg-dev libpng-dev libfreetype6-dev libwebp-dev libgif-dev && \
	docker-php-ext-configure gd --with-jpeg-dir --with-png-dir --with-freetype-dir --with-webp-dir --with-gd && \
	docker-php-ext-install gd && \
# ext: gettext
	docker-php-ext-install gettext && \
# ext: gmp
	apt-get install -y --no-install-recommends libgmp-dev && \
	docker-php-ext-install gmp && \
# ext: imap
	apt-get install -y --no-install-recommends libc-client-dev libkrb5-dev && \
	docker-php-ext-configure imap --with-kerberos --with-imap-ssl && \
	docker-php-ext-install imap && \
# ext: interbase
	apt-get install -y --no-install-recommends firebird-dev && \
	docker-php-ext-install interbase && \
# ext: intl
	apt-get install -y --no-install-recommends libicu-dev && \
	docker-php-ext-install intl && \
# ext: ldap
	apt-get install -y --no-install-recommends libldap2-dev && \
	docker-php-ext-install ldap && \
# ext: mysqli
	docker-php-ext-install mysqli && \
# ext: opcache
	docker-php-ext-install opcache && \
# ext: pcntl
	docker-php-ext-install pcntl && \
# ext: pdo_dblib
	apt-get install -y --no-install-recommends freetds-dev && \
	docker-php-ext-configure pdo_dblib --with-libdir=lib/x86_64-linux-gnu && \
	docker-php-ext-install pdo_dblib && \
# ext: pdo_firebird
	apt-get install -y --no-install-recommends firebird-dev && \
	docker-php-ext-install pdo_firebird && \
# ext: pdo_mysql
	docker-php-ext-install pdo_mysql && \
# ext: pdo_odbc
	apt-get install -y --no-install-recommends unixodbc-dev && \
	docker-php-ext-configure pdo_odbc --with-pdo-odbc=unixODBC,/usr && \
	docker-php-ext-install pdo_odbc && \
# ext: pdo_pgsql
	apt-get install -y --no-install-recommends libpq-dev && \
	docker-php-ext-install pdo_pgsql && \
# ext: pgsql
	apt-get install -y --no-install-recommends libpq-dev && \
	docker-php-ext-install pgsql && \
# ext: pspell
	apt-get install -y --no-install-recommends libpspell-dev && \
	docker-php-ext-install pspell && \
# ext: recode
	apt-get install -y --no-install-recommends librecode-dev && \
	docker-php-ext-install recode && \
# ext: shmop
	docker-php-ext-install shmop && \
# ext: snmp
	apt-get install -y --no-install-recommends libsnmp-dev snmp && \
	echo "snmp" >> /tmp/savedAptMark && \
	docker-php-ext-install snmp && \
# ext: soap
	apt-get install -y --no-install-recommends libxml2-dev && \
	docker-php-ext-install soap && \
# ext: sockets
	docker-php-ext-install sockets && \
# ext: sysvmsg
	docker-php-ext-install sysvmsg && \
# ext: sysvsem
	docker-php-ext-install sysvsem && \
# ext: sysvshm
	docker-php-ext-install sysvshm && \
# ext: tidy
	apt-get install -y --no-install-recommends libtidy-dev && \
	docker-php-ext-install tidy && \
# ext: wddx
	apt-get install -y --no-install-recommends libxml2-dev && \
	docker-php-ext-install wddx && \
# ext: xmlrpc
	apt-get install -y --no-install-recommends libxml2-dev && \
	docker-php-ext-install xmlrpc && \
# ext: xsl
	apt-get install -y --no-install-recommends libxslt1-dev && \
	docker-php-ext-install xsl && \
# ext: zip
	apt-get install -y --no-install-recommends zlib1g-dev libzip-dev && \
	docker-php-ext-configure zip --with-libzip && \
	docker-php-ext-install zip && \
# pecl: amqp
	apt-get install -y --no-install-recommends librabbitmq-dev && \
	pecl install -f amqp && \
	docker-php-ext-enable amqp && \
# pecl: apcu
	pecl install -f apcu && \
	docker-php-ext-enable apcu && \
# pecl: ast
	pecl install -f ast && \
	docker-php-ext-enable ast && \
# pecl: ds
	pecl install -f ds && \
	docker-php-ext-enable ds && \
# ext: sockets
	docker-php-ext-install sockets && \
# pecl: event
	apt-get install -y --no-install-recommends libevent-dev libssl1.0-dev && \
	pecl install -f event && \
	docker-php-ext-enable event && \
# pecl: geoip
	apt-get install -y --no-install-recommends libgeoip-dev && \
	pecl install -f geoip-beta && \
	docker-php-ext-enable geoip && \
# pecl: grpc
	apt-get install -y --no-install-recommends libzip-dev && \
	pecl install -f grpc && \
	docker-php-ext-enable grpc && \
# pecl: igbinary
	pecl install -f igbinary && \
	docker-php-ext-enable igbinary && \
# pecl: imagick
	apt-get install -y --no-install-recommends libmagick++-dev && \
	pecl install -f imagick && \
	docker-php-ext-enable imagick && \
# pecl: mcrypt
	apt-get install -y --no-install-recommends libmcrypt-dev && \
	pecl install -f mcrypt && \
	docker-php-ext-enable mcrypt && \
# pecl: memcached
	apt-get install -y --no-install-recommends libmemcached-dev libzip-dev && \
	pecl install -f memcached && \
	docker-php-ext-enable memcached && \
# pecl: mongodb
	pecl install -f mongodb && \
	docker-php-ext-enable mongodb && \
# pecl: oauth
	apt-get install -y --no-install-recommends libpcre3-dev && \
	pecl install -f oauth && \
	docker-php-ext-enable oauth && \
# pecl: rdkafka
	apt-get install -y --no-install-recommends librdkafka-dev && \
	pecl install -f rdkafka && \
	docker-php-ext-enable rdkafka && \
# pecl: redis
	pecl install -f redis && \
	docker-php-ext-enable redis && \
# pecl: uuid
	apt-get install -y --no-install-recommends uuid-dev && \
	pecl install -f uuid && \
	docker-php-ext-enable uuid && \
# pecl: xdebug
	pecl install -f xdebug-beta && \
	docker-php-ext-enable xdebug && \
# pecl: yaml
	apt-get install -y --no-install-recommends libyaml-dev && \
	pecl install -f yaml && \
	docker-php-ext-enable yaml && \
#
	docker-php-source delete && \
#
	apt-mark auto '.*' > /dev/null && \
	[ -z "$(cat /tmp/savedAptMark)" ] || apt-mark manual $(cat /tmp/savedAptMark) && \
	find /usr/local -type f -name '*.so*' -exec ldd '{}' ';' | awk '/=>/ { print $(NF-1) }' | sort -u | \
		xargs -r dpkg-query --search | cut -d: -f1 | sort -u | xargs -r apt-mark manual && \
	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false && \
	rm -rf /tmp/* ~/.pearrc /var/lib/apt/lists/*
