ARG PHP_VERSION

FROM "php:${PHP_VERSION}-apache-buster"

# https://xdebug.org/docs/compat#versions
RUN pecl install xdebug-3.0.4 \
    && docker-php-ext-enable xdebug

# GD Extension
RUN apt-get update -y && apt-get install -y \
  libpng-dev \
  libfreetype6-dev \
  libjpeg-dev \
  libxpm-dev \
  libxml2-dev \
  libxslt-dev \
  libmcrypt-dev \
  libwebp-dev
RUN docker-php-ext-configure gd \
    --with-freetype \
    --with-jpeg \
    --with-xpm \
    --with-webp
RUN docker-php-ext-install gd

RUN docker-php-ext-install -j$(nproc) \
    # iconv \
    # intl \
    # bcmath \
    # mbstring \
    # curl \
    # xsl \
    # soap \
    mysqli \
    # pdo \
    # pdo_mysql \
    # pdo_pgsql \
    # opcache \
    # zip \
    # calendar