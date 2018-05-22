---
date: 2018-22-05T10:21:05+02:00
title: Varnish
--- 

## Image

Image is named `fpfis/varnish` and based on CentOS 6.

## Configuration

Use the following environment variable to configure the image :

`HTTP_PORT`
Port to listen to ( default 6080 )

`DEFAULT_BACKEND`
Backend to connect to ( default localhost:8080 )

## Mouting VCL volume

VCL must be mounted in `/etc/varnish` and a `default.vcl` should be present.

## Example

Assuming you have a working VCL with `default.vcl` in your local `varnish` folder :

```bash
docker run -p 6080:6080 -ti --rm -e DEFAULT_BACKEND=172.16.10.1:8080 -v $(pwd)/varnish:/etc/varnish fpfis/varnish 
```

___

[![Build Status](https://drone.fpfis.eu/api/badges/ec-europa/docker-fpfis/status.svg?branch=release/varnish)](https://drone.fpfis.eu/ec-europa/docker-fpfis)
[![Docker Image](https://images.microbadger.com/badges/image/fpfis/varnish.svg)](https://microbadger.com/images/fpfis/varnish) 