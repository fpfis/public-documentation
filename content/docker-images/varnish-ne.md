---
date: 2018-22-05T10:21:05+02:00
title: NextEuropa Varnish
weight: 20
--- 

## Image

The image is named `fpfis/varnish-ne:4.1`.

It is based on `fpfis/varnish` and as such inherits all configuration options 
from the [fpfis/varnish](../varnish/)  image.

The NextEuropa VCL is included and includes the purging mechanism.

## Supported version

 - 4.1  

## Running

```bash
docker run -p 8086:8086 -ti --rm -e YAML_CONF=/yaml.conf -v $(pwd)/config.yaml:/config.yaml fpfis/varnish-ne:4.1 
```

[![Build Status](https://drone.fpfis.eu/api/badges/ec-europa/nexteuropa-vcl/status.svg?branch=release/0.1.1)](https://drone.fpfis.eu/ec-europa/nexteuropa-vcl)
[![Docker Image](https://images.microbadger.com/badges/image/fpfis/varnish-ne:4.1.svg)](https://microbadger.com/images/fpfis/varnish-ne:4.1)
