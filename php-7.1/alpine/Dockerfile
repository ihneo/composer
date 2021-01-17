FROM ihneo/php:7.1-cli-alpine

# git client
RUN apk add --update --no-cache git

# composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --1 --filename=composer-1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --2 --filename=composer-2
RUN cd /usr/local/bin && ln -s composer-2 composer
