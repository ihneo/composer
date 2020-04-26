FROM ihneo/php:7.1-cli-alpine

# git client
RUN apk add --update --no-cache git

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

