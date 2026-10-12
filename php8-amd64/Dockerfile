# buildkit bug workaround - https://github.com/moby/buildkit/issues/1368
FROM martinussuherman/alpine:3.24-amd64

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
    php84 \
    php84-fpm \
    # php84-apache2 \
    php84-bcmath \
    php84-bz2 \
    php84-calendar \
    php84-ctype \
    php84-curl \
    # php84-dba \
    php84-dom \
    php84-embed \
    # php84-enchant \
    # php84-exif \
    # php84-ffi \
    php84-fileinfo \
    # php84-ftp \
    php84-gd \
    php84-gettext \
    php84-gmp \
    php84-iconv \
    php84-intl \
    # php84-ldap \
    # php84-litespeed \
    php84-mbstring \
    php84-mysqli \
    php84-mysqlnd \
    # php84-odbc \
    php84-opcache \
    php84-openssl \
    # php84-pcntl \
    php84-pdo \
    # php84-pdo_dblib \
    php84-pdo_mysql \
    # php84-pdo_odbc \
    # php84-pdo_pgsql \
    php84-pdo_sqlite \
    # php84-pear \
    php84-pgsql \
    php84-phar \
    # php84-phpdbg \
    php84-posix \
    # php84-pspell \
    php84-session \
    # php84-shmop \
    php84-simplexml \
    # php84-snmp \
    php84-soap \
    php84-sockets \
    php84-sodium \
    php84-sqlite3 \
    # php84-sysvmsg \
    # php84-sysvsem \
    # php84-sysvshm \
    # php84-tidy \
    php84-tokenizer \
    php84-xml \
    php84-xmlreader \
    # php84-xmlwriter \
    # php84-xsl \
    php84-zip \
    # php84-pecl-imagick \
    # php84-pecl-igbinary \
    # php84-pecl-xdebug \
    # php84-pecl-mongodb \
    # php84-pecl-event \
    # php84-pecl-redis \
    # php84-pecl-apcu \
    # php84-pecl-maxminddb \
    # php84-pecl-timezonedb \
    # php84-pecl-memcached \
    # php84-pecl-vips \
    # php84-brotli \
    # php84-pecl-msgpack \
    # php84-pecl-xhprof \
    # php84-pecl-xhprof-assets \
    # php84-pecl-yaml \
    # php84-pecl-uploadprogress \
    # php84-pecl-uuid \
    # php84-pecl-memcache \
    # php84-pecl-oauth \
    # php84-pecl-lzf \
    # php84-pecl-mailparse \
    # php84-pecl-mcrypt \
    # php84-pecl-ast \
    && touch /var/log/php-fpm-access.log /var/log/php-fpm-error.log \
    && ln -sf /dev/stdout /var/log/php-fpm-access.log \
    && ln -sf /dev/stderr /var/log/php-fpm-error.log

ENTRYPOINT ["entrypoint-exec", "php-fpm84"]
