FROM martinussuherman/alpine:3.13-amd64

ENV \
    # container/su-exec UID \
    EUID=1001 \
    # container/su-exec GID \
    EGID=1001 \
    # container/su-exec user name \
    EUSER=www-data \
    # container/su-exec group name \
    EGROUP=www-data \
    # container user home dir \
    EHOME=/etc/php7 \
    # should user home dir get chown'ed? (yes/no) \
    ECHOWNHOME=yes \
    # additional directories to create + chown (space separated) \
    ECHOWNDIRS="/var/log/php-fpm" \
    # additional files to create + chown (space separated) \
    ECHOWNFILES="/var/log/php-fpm/access.log /var/log/php-fpm/error.log" \
    # container timezone \
    TZ=UTC 

RUN apk --no-cache --update add \
    php7 \
    php7-fpm \
    # php7-amqp \
    # php7-apache2 \
    # php7-apcu \
    php7-bcmath \
    php7-bz2 \
    php7-calendar \
    php7-ctype \
    php7-curl \
    # php7-dba \
    php7-dom \
    php7-embed \
    # php7-enchant \
    # php7-exif \
    # php7-fileinfo \
    # php7-ftp \
    php7-gd \
    php7-gettext \
    php7-gmp \
    php7-iconv \
    php7-imagick \
    php7-imap \
    php7-intl \
    php7-json \
    # php7-ldap \
    # php7-litespeed \
    # php7-mailparse \
    php7-mbstring \
    # php7-mcrypt \
    # php7-memcached \
    php7-mysqli \
    php7-mysqlnd \
    # php7-oauth \
    # php7-odbc \
    php7-opcache \
    php7-openssl \
    # php7-pcntl \
    php7-pdo \
    # php7-pdo_dblib \
    php7-pdo_mysql \
    # php7-pdo_odbc \
    # php7-pdo_pgsql \
    php7-pdo_sqlite \
    # php7-pear \
    # php7-pear-auth_sasl \
    # php7-pear-auth_sasl2 \
    # php7-pear-mail_mime \
    # php7-pear-mdb2_driver_mysql \
    # php7-pear-mdb2_driver_pgsql \
    # php7-pear-net_idna2 \
    # php7-pear-net_smtp \
    # php7-pear-net_socket \
    php7-pgsql \
    php7-phar \
    # php7-phpdbg \
    # php7-posix \
    # php7-pspell \
    # php7-recode \
    php7-redis \
    php7-session \
    # php7-shmop \
    # php7-simplexml \
    # php7-snmp \
    php7-soap \
    php7-sockets \
    php7-sqlite3 \
    # php7-ssh2 \
    # php7-sysvmsg \
    # php7-sysvsem \
    # php7-sysvshm \
    # php7-tidy \
    # php7-tokenizer \
    # php7-wddx \
    # php7-xdebug \
    php7-xml \
    php7-xmlreader \
    # php7-xmlrpc \
    # php7-xmlwriter \
    # php7-xsl \
    php7-zip \
    # php7-zmq \
    && touch /var/log/php-fpm-access.log /var/log/php-fpm-error.log \
    && ln -sf /dev/stdout /var/log/php-fpm-access.log \
    && ln -sf /dev/stderr /var/log/php-fpm-error.log

ENTRYPOINT ["entrypoint-su-exec", "php-fpm7"]
