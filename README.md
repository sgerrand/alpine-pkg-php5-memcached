# alpine-pkg-php5-memcached

[![CircleCI](https://img.shields.io/circleci/project/sgerrand/alpine-pkg-php5-memcached/master.svg)](https://circleci.com/gh/sgerrand/alpine-pkg-php5-memcached)

This is the [PHP driver for Memcached][php-memcached] as a Alpine Linux package.

## Releases

See the [releases page](https://github.com/sgerrand/alpine-pkg-php5-memcached/releases) for the latest
download links.

## Installing

The current installation method for these packages is to pull them in using
`wget` or `curl` and install the local file with `apk`:

    apk --no-cache add ca-certificates
    wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-php5-memcached/master/sgerrand.rsa.pub
    wget https://github.com/sgerrand/alpine-pkg-php5-memcached/releases/download/2.2.0-r0/php5-memcached-2.2.0-r0.apk
    apk add php5-memcached-2.2.0-r0.apk

[php-memcached]: https://pecl.php.net/memcached
