FROM ihneo/php:7.4-cli-alpine

# git client
RUN apk add --update --no-cache git

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --1 --filename=composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --2 --filename=composer2
