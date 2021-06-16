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
    EHOME=/etc/php8 \
    # should user home dir get chown'ed? (yes/no) \
    ECHOWNHOME=yes \
    # additional directories to create + chown (space separated) \
    ECHOWNDIRS="/var/log/php-fpm" \
    # additional files to create + chown (space separated) \
    ECHOWNFILES="/var/log/php-fpm/access.log /var/log/php-fpm/error.log" \
    # container timezone \
    TZ=UTC 

RUN apk --no-cache --update add \
    php8 \
    php8-fpm \
    # php8-amqp \
    # php8-apache2 \
    # php8-apcu \
    php8-bcmath \
    php8-bz2 \
    php8-calendar \
    php8-ctype \
    php8-curl \
    # php8-dba \
    php8-dom \
    php8-embed \
    # php8-enchant \
    # php8-exif \
    # php8-fileinfo \
    # php8-ftp \
    php8-gd \
    php8-gettext \
    php8-gmp \
    php8-iconv \
    php8-imagick \
    php8-imap \
    php8-intl \
    php8-json \
    # php8-ldap \
    # php8-litespeed \
    # php8-mailparse \
    php8-mbstring \
    # php8-mcrypt \
    # php8-memcached \
    php8-mysqli \
    php8-mysqlnd \
    # php8-oauth \
    # php8-odbc \
    php8-opcache \
    php8-openssl \
    # php8-pcntl \
    php8-pdo \
    # php8-pdo_dblib \
    php8-pdo_mysql \
    # php8-pdo_odbc \
    # php8-pdo_pgsql \
    php8-pdo_sqlite \
    # php8-pear \
    # php8-pear-auth_sasl \
    # php8-pear-auth_sasl2 \
    # php8-pear-mail_mime \
    # php8-pear-mdb2_driver_mysql \
    # php8-pear-mdb2_driver_pgsql \
    # php8-pear-net_idna2 \
    # php8-pear-net_smtp \
    # php8-pear-net_socket \
    php8-pgsql \
    php8-phar \
    # php8-phpdbg \
    # php8-posix \
    # php8-pspell \
    # php8-recode \
    php8-redis \
    php8-session \
    # php8-shmop \
    # php8-simplexml \
    # php8-snmp \
    php8-soap \
    php8-sockets \
    php8-sqlite3 \
    # php8-ssh2 \
    # php8-sysvmsg \
    # php8-sysvsem \
    # php8-sysvshm \
    # php8-tidy \
    # php8-tokenizer \
    # php8-wddx \
    # php8-xdebug \
    php8-xml \
    php8-xmlreader \
    # php8-xmlrpc \
    # php8-xmlwriter \
    # php8-xsl \
    php8-zip \
    # php8-zmq \
    && touch /var/log/php-fpm-access.log /var/log/php-fpm-error.log \
    && ln -sf /dev/stdout /var/log/php-fpm-access.log \
    && ln -sf /dev/stderr /var/log/php-fpm-error.log

ENTRYPOINT ["entrypoint-su-exec", "php8-fpm"]
