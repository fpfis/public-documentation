---
date: 2018-22-05T10:21:05+02:00
title: Redis
weight: 30
--- 

## Image

We recommend using the latest [Redis 4.0](https://hub.docker.com/_/redis/) image

## Configuration

See the [Docker Hub's page](https://hub.docker.com/_/redis/).

## Port

Redis is running on port `6379` by default.

## Example

```bash
docker run -p 6379:6379 -ti --rm redis
```