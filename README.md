# PHP FPM Docker Container

This is an automatically built docker container for PHP FPM.

It includes PHP FPM configured to run on port 9000, a number of PHP extensions enabled
by default, and Composer for dependency management.

## Extensions enabled

* gd
* pdo
* pdo_pgsql
* opcache
* zip

_More exensions can be added on request_

## Mount points

| Purpose         | Path                                |
|-----------------|-------------------------------------|
| Site root       | `/var/www/docroot`                  |
| PHP config      | `/usr/local/etc/php/conf.d/php.ini` |
| Composer config | `/var/www/composer.json`            |
| Composer lock   | `/var/www/composer.lock`            |

The containers `WORKDIR` is set to `/var/www` so you can easily run Composer commands.

## Ports

The only port this container uses is 9000, it's typically used with an Nginx container
in the same docker network so forwarding the port through the host is not required.
