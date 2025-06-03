FROM php:8.2-cli AS builder

WORKDIR /app

COPY . .
RUN composer install

FROM php:8.2-fpm-alpine

WORKDIR /app

COPY --from=builder /app .
COPY --from=builder /usr/local/bin/composer /usr/local/bin/composer

