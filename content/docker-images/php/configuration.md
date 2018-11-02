---
date: 2018-22-05T10:21:05+02:00
title: Configuration
weight: 10
--- 

## Runtime docker configuration

| env                        | Description                        |  Default          |
|----------------------------|------------------------------------|-------------------|
|`APACHE_ACCESS_LOG`         | Location of apache's access log    | `/proc/self/fd/1` |
|`APACHE_ERROR_LOG`          | Location of apache's error log     | `/proc/self/fd/2` |
|`DAEMON_GROUP`              | Group name to run the daemons with | `www-data`        |
|`DAEMON_USER`               | Username to run the daemons with   | `www-data`        |
|`DOCUMENT_ROOT`             | Document root                      | `/var/www/html`   |
|`SITE_PATH`                 | Site URL location (non-dev)        | `/`
|`FPM_MAX_CHILDREN`          | Max number of PHP processes        | `5`               |
|`FPM_MIN_CHILDREN`          | Min number of PHP processes        | `2`               |
|`HTTP_PORT`                 | Port to listen on                  | `8080`            |
|`PHP_MAX_EXECUTION_TIME`    | PHP max execution time             | `30`              |
|`PHP_MAX_INPUT_TIME`        | PHP max input time                 | `30`              |
|`PHP_MEMORY_LIMIT`          | PHP memory limit                   | `512M`            |
|`SMTP_SERVER`               | SMTP server to use                 | empty
|`SMTP_PORT  `               | SMTP port   to use                 | `25`
|`SMTP_FROM`                 | SMTP From to use                   | empty
|`SMTP_USERNAME`             | Username to use for SMTP auth      | empty
|`SMTP_PASSWORD`             | Password to use for SMTP auth      | empty



## With docker-compose

Eg, if you have an app with a `web` folder that should be the document root :

```yaml
services:
  web:
    image: fpfis/httpd-php-dev:5.6
    environment:
     - DOCUMENT_ROOT=/app/web
    volumes:
     - .:/app
```
