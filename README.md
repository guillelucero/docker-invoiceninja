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
  image: moss/invoiceninja:2.8
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

Database username; (Default: ninja)

`DB_PASSWORD`

Database password; (Default: ninja)

`APP_KEY`

App security key; (Default: SomeRandomString)

`LOG`


This image supports `single`, `daily`, `syslog` and `errorlog` logging modes,
following Laravel https://laravel.com/docs/5.2/errors#configuration. (**Default
errorlog **)

`APP_DEBUG` 

For debug, set this to `1`. (Default 0)

`TRUSTED_PROXIES`

Set the proxy network address to allow this image to be used behind a proxy
like nginx.

`MAIL_HOST`

SMPT HOST.

`MAIL_PORT`

STMP port (Default 587)

`MAIL_ENCRYPTION`

SMTP encryption protocol. (Default tls)

`MAIL_USERNAME`

SMTP username.

`MAIL_FROM_ADDRESS`

SMTP mail from address, in case of you are using a smtp alias.

`MAIL_FROM_NAME`

SMTP from Name.

`MAIL_PASSWORD`

STMP password.
