---
date: 2018-22-05T10:21:05+02:00
title: Versioning
weight: 5
--- 

We follow upstream version for tagging.

## Tagging rational

| tag            | type   | build                       | environment                               |
|----------------|--------|-----------------------------|-------------------------------------------|
| x.x            | beta   | push on develop             | acceptance/playground/testing/development |
| 5.6.36(-1..xx) | stable | tag from develop            | selective/edge cases/regression testing   |
| 7.1.2(-1..xx)  | stable | tag from develop            | selective/edge cases/regression testing   |
| production-x.x | stable | merge from develop or tag   | production                                |


 - Alpha: versions are always the latest build of our docker images, they should be used for testing and ensure no issue are found at the infrastructure level before the image hits the production servers.
 - Beta: versions are tags that are considered stable and can be used to target the pre-prod version or older version for regression testing. A suffix is added when a fpfis release is done ( eg: 5.6.36-1, 5.6.36-2, ect ... )
 - Stable: Is merged every time the last tag is considered stable, and should be used in production.
 
