---
date: 2018-22-05T10:21:05+02:00
title: Configuration
weight: 10
--- 

## Environment variables

Use the following environment variable to configure the image :

`DOCUMENT_ROOT`
Path to document root ( default /var/www/html )

`XDEBUG`
Enable/Disable Xdebug ( default on )

## With docker-compose

Eg, if you have an app with a `web` folder that should be the document root :

```yaml
services:
  web:
    image: fpfis/php56-dev:latest
    environment:
     - DOCUMENT_ROOT=/app/web
    volumes:
     - .:/app
```

{{% notice info %}}
**About ${DOCUMENT_ROOT}** : The image will first try to create the directory using the parent's permissions if it's missing.
{{% /notice %}}