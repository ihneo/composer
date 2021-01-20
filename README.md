# COMPOSER
Composer Dockerfiles with  different versions of PHP (mainly for our needs)

## Example of Usage

Move to the folder containing the desired Dockerfile.

Build the image
```
docker build -t <dockertag> .
```

Create a shell script called `composer-php<version>.sh` with this content :
```
#!/bin/bash
docker run --rm --interactive --tty \
  --env COMPOSER_HOME=/tmp/composer/config \
  --env COMPOSER_CACHE_DIR=/tmp/composer/cache \
  --workdir /app \
  --volume $PWD:/app \
  --volume ${COMPOSER_HOME:-$HOME/.config/composer}:/tmp/composer/config \
  --volume ${COMPOSER_CACHE_DIR:-$HOME/.cache/composer}:/tmp/composer/cache \
  --user $(id -u):$(id -g) \
  <dockertag> composer "$@"
```

## Dockerhub
All images are available at : https://hub.docker.com/r/ihneo/composer

You can pull all images with the command :
```
docker pull ihneo/composer:<dockertag>
```

## Supported tags and respective `Dockerfile` links

-	[`php-7.1-alpine`](https://github.com/ihneo/composer/blob/master/php-7.1/alpine/Dockerfile)
-	[`php-7.2-alpine`](https://github.com/ihneo/composer/blob/master/php-7.2/alpine/Dockerfile)
-	[`php-7.3-alpine`](https://github.com/ihneo/composer/blob/master/php-7.3/alpine/Dockerfile)
-	[`php-7.4-alpine`](https://github.com/ihneo/composer/blob/master/php-7.4/alpine/Dockerfile)
-	[`php-8.0-alpine`, `latest`](https://github.com/ihneo/composer/blob/master/php-8.0/alpine/Dockerfile)

## Example of usage with the images available at Dockerhub
```
#!/bin/bash
docker run --rm --interactive --tty \
  --env COMPOSER_HOME=/tmp/composer/config \
  --env COMPOSER_CACHE_DIR=/tmp/composer/cache \
  --workdir /app \
  --volume $PWD:/app \
  --volume ${COMPOSER_HOME:-$HOME/.config/composer}:/tmp/composer/config \
  --volume ${COMPOSER_CACHE_DIR:-$HOME/.cache/composer}:/tmp/composer/cache \
  --user $(id -u):$(id -g) \
  ihneo/composer:<dockertag> composer "$@"
```

## Composer 1 or 2

To use composer in version 1, command is `composer`

To use composer in version 2, command is `composer2`