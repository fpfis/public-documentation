---
date: 2018-22-05T10:21:05+02:00
title: Flavors
weight: 5
--- 

## Image flavors

### Base

The image contains PHP and Apache, no additional services are running.

All subsequent development images are base on this image.

```bash
$ docker pull fpfis/httpd-php:5.6
$ docker pull fpfis/httpd-php:7.1
$ docker pull fpfis/httpd-php:7.2
```


### Full image

Based on the base image.

Additional components have been added for convenience :

 - Java
 - OCI
 
```bash
$ docker pull fpfis/httpd-php-full:5.6
$ docker pull fpfis/httpd-php-full:7.1
$ docker pull fpfis/httpd-php-full:7.2
```

### Development image

Based on the full image, various dev services and packages are also included :

 - Composer
 - Git, Patch & co
 - Xdebug for debugging
 - Blackfire for profiling
 
```bash
$ docker pull fpfis/httpd-php-dev:5.6
$ docker pull fpfis/httpd-php-dev:7.1
$ docker pull fpfis/httpd-php-dev:7.2
```

