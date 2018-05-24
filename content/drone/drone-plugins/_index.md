---
date: 2018-20-05T10:21:05+02:00
title: Drone plugins
---

## [Composer SA Checker](composer-sa-checker)

Checks your composer.lock file for known security advisories with Sensiolab's SA checker.

```yaml
pipeline:
  composer-sa-check:
    image: phpdrone/composer-sa-checker
#   lock_file: composer.lock
```

## [PHAR Composer](phar-composer)

Creates a standalone PHAR file from a composer project.

```yaml
pipeline:
  build-phar:
    image: phpdrone/phar-composer
    output: myapp.phar
```

