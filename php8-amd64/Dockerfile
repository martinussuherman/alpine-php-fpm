# buildkit bug workaround - https://github.com/moby/buildkit/issues/1368
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
    # php8-apache2 \
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
    # php8-ffi \
    php8-fileinfo \
    # php8-ftp \
    php8-gd \
    php8-gettext \
    php8-gmp \
    php8-iconv \
    php8-imap \
    php8-intl \
    # php8-ldap \
    # php8-litespeed \
    php8-mbstring \
    php8-mysqli \
    php8-mysqlnd \
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
    php8-pgsql \
    php8-phar \
    # php8-phpdbg \
    php8-posix \
    # php8-pspell \
    php8-session \
    # php8-shmop \
    php8-simplexml \
    # php8-snmp \
    php8-soap \
    php8-sockets \
    php8-sodium \
    php8-sqlite3 \
    # php8-sysvmsg \
    # php8-sysvsem \
    # php8-sysvshm \
    # php8-tidy \
    php8-tokenizer \
    php8-xml \
    php8-xmlreader \
    # php8-xmlwriter \
    # php8-xsl \
    php8-zip \
    # php8-pecl-imagick \
    # php8-pecl-igbinary \
    # php8-pecl-xdebug \
    # php8-pecl-mongodb \
    # php8-pecl-event \
    # php8-pecl-redis \
    # php8-pecl-apcu \
    # php8-pecl-maxminddb \
    # php8-pecl-timezonedb \
    # php8-pecl-memcached \
    # php8-pecl-vips \
    # php8-brotli \
    # php8-pecl-msgpack \
    # php8-pecl-xhprof \
    # php8-pecl-xhprof-assets \
    # php8-pecl-yaml \
    # php8-pecl-uploadprogress \
    # php8-pecl-uuid \
    # php8-pecl-memcache \
    # php8-pecl-oauth \
    # php8-pecl-lzf \
    # php8-pecl-mailparse \
    # php8-pecl-mcrypt \
    # php8-pecl-ast \
    && touch /var/log/php-fpm-access.log /var/log/php-fpm-error.log \
    && ln -sf /dev/stdout /var/log/php-fpm-access.log \
    && ln -sf /dev/stderr /var/log/php-fpm-error.log

ENTRYPOINT ["entrypoint-exec", "php-fpm8"]
