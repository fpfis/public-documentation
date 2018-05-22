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
$ docker pull fpfis/php56
$ docker pull fpfis/php71
```

### Development image

The image contains PHP and Apache. Various dev services and packages are also included :

 - [Shellinabox](shellinabox) for accessing the container's shell while running
 - Phpmyadmin for accessing MySQL databases
 - Mailhog for receiving mock emails
 - Xdebug for debugging
 - Blackfire for profiling
 
```bash
$ docker pull fpfis/php56-dev
$ docker pull fpfis/php71-dev
```

### Development full image

The image contains everything `fpfis/phpXX-dev` contains and adds the following :

 - Ruby
 - Compass
 - Sass
 
```bash
$ docker pull fpfis/php56-dev-full
$ docker pull fpfis/php71-dev-full
```
