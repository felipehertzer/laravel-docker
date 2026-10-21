FROM php:8.6-rc-alpine3.23

# Install dependencies
RUN apk add --no-cache \
    bash \
    curl \
    freetype-dev \
    g++ \
    gcc \
    gcompat \
    git \
    icu-dev \
    icu-libs \
    libc-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    libwebp-dev \
    libxml2-dev \
    libzip-dev \
    make \
    mysql-client \
    nodejs \
    npm \
    oniguruma-dev \
    yarn \
    openssh-client \
    postgresql-dev \
    rsync \
    zlib-dev

# Install php extensions
# NOTE: PHP 8.6 images no longer ship pecl, so install-php-extensions does not
# support them yet (mlocati/docker-php-extension-installer#1125). Bundled
# extensions are installed directly; imagick, redis and xdebug have no 8.6
# compatible release yet and are therefore missing from this image for now.
RUN docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp && \
    docker-php-ext-install -j"$(nproc)" \
    bcmath \
    calendar \
    exif \
    gd \
    intl \
    mbstring \
    pcntl \
    pdo_mysql \
    pdo_pgsql \
    soap \
    zip

# Install Composer
COPY --from=composer:2 /usr/bin/composer /usr/local/bin/composer

# Add local and global vendor bin to PATH.
ENV PATH=./vendor/bin:/composer/vendor/bin:/root/.composer/vendor/bin:/usr/local/bin:$PATH

# Install PHP_CodeSniffer
RUN composer global require "squizlabs/php_codesniffer=*"

# Setup working directory
WORKDIR /var/www
