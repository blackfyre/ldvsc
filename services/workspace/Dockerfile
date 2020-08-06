# From official php image.
FROM php:7.4-cli-alpine
# Install the php zip extension.
RUN apk add --no-cache libzip-dev && docker-php-ext-configure zip && docker-php-ext-install zip
# Install php pcov pecl extension for super-fast coverage reports.
RUN apk add --no-cache g++ gcc make php7-dev zlib-dev && pecl install pcov && docker-php-ext-enable pcov
# Install common php extensions
RUN docker-php-ext-install mysqli pdo pdo_mysql
# Install composer for php deps.
RUN apk add --no-cache composer
# Install nodejs and npm for nodejs deps.
RUN apk add --no-cache nodejs npm yarn
# Install quality-of-life packages.
RUN apk add --no-cache bash curl git vim nano openssh
# Create a vscoder user group and user account.
RUN addgroup -g 1000 -S vscoder && adduser -u 1000 -S vscoder -G vscoder
# Copy the .bashrc file for vscoder.
COPY .bashrc /home/vscoder/.bashrc
# Install sudo exec
RUN apk add --no-cache sudo && echo '%wheel ALL=(ALL) NOPASSWD:ALL' > /etc/sudoers.d/wheel && adduser vscoder wheel
# Setup PHP for development
RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini
RUN sed -i 's/128M/2G/g' /usr/local/etc/php/php.ini
# Setup Locale
ENV MUSL_LOCALE_DEPS cmake make musl-dev gcc gettext-dev libintl 
ENV MUSL_LOCPATH /usr/share/i18n/locales/musl

RUN apk add --no-cache \
    $MUSL_LOCALE_DEPS \
    && wget https://gitlab.com/rilian-la-te/musl-locales/-/archive/master/musl-locales-master.zip \
    && unzip musl-locales-master.zip \
      && cd musl-locales-master \
      && cmake -DLOCALE_PROFILE=OFF -D CMAKE_INSTALL_PREFIX:PATH=/usr . && make && make install \
      && cd .. && rm -r musl-locales-master
# Run the workspace till we die.
CMD ["sleep", "infinity"]
