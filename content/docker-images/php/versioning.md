---
date: 2018-22-05T10:21:05+02:00
title: Versioning
weight: 5
--- 

## Upstream tags

Both `fpfis/httpd-php` and `fpfis/httpd-php-dev` are based on the latest PHP docker images.

We follow upstream version for tagging.

## Tagging rational

| tag            | type   | build                       | environment                               |
|----------------|--------|-----------------------------|-------------------------------------------|
| 5.6            | alpha  | push on release/5.6         | acceptance/playground/testing/development |
| 5.6.36         | beta   | tag from release/5.6        | selective/edge cases/regression testing   |
| production-5.6 | stable | merge tag on production/5.6 | production                                |
| 7.1            | alpha  | push on release/7.1         | acceptance/playground/testing/development |
| 7.1.2          | beta   | tag from release/7.1        | selective/edge cases/regression testing   |
| production-7.1 | stable | merge tag on production/7.1 | production                                |


 - Alpha: versions are always the latest build of our docker images, they should be used for testing and ensure no issue are found at the infrastructure level before the image hits the production servers.
 - Beta: version are tagged version that are considered stable and can be used to target the pre-prod version or older version for regression testing.
 - Stable: Is merged everytime the last tag is considered stable, and should be used in production.
 