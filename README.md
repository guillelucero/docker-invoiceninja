Docker Invoice Ninja
====================

# Introduction

DockerFile for invoice ninja (https://www.invoiceninja.com/)

This image is based on `php:7` official version.

Official repository on https://github.com/moss-it/docker-invoiceninja

# Quick start

The easiest way to try this image is via docker compose :

```
db:
  image: mysql
  environment:
    MYSQL_DATABASE: ninja
    MYSQL_ROOT_PASSWORD: mdp

app:
  image: moss/invoiceninja:2.5.2.2
  links:
    - db:mysql
  ports:
    - 80:80
```

# Available variables


`DB_HOST`

Mysql database host; (Default: mysql)

`DB_DATABASE`

Database name; (Default: ninja)

`DB_USERNAME`

Database username; (Default: root)

`APP_KEY`

App secutiry key; (Default: SomeRandomString)

`LOG`


This image supports `single`, `daily`, `syslog` and `errorlog` logging modes,
following Laravel https://laravel.com/docs/5.2/errors#configuration. (**Default errorlog **)

`APP_DEBUG` 

For debug, set this to `1`. (Default 0)
