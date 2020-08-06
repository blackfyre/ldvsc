FROM php:7.4-fpm-alpine
RUN addgroup -g 1000 vscoder && addgroup www-data vscoder
RUN adduser -u 1000 -S vscoder -G vscoder
# COPY overrides.ini /etc/php/7.4/fpm/conf.d/99-overrides.ini
