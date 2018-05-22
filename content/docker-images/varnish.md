---
date: 2018-22-05T10:21:05+02:00
title: Varnish
---

## Reference environment variables

`HTTP_PORT`
Port to listen to

`DEFAULT_BACKEND`
Backend to connect to

## Mouting VCL

VCL must be mounted in `/etc/varnish` and a `default.vcl` should be present.


## Example

```bash
docker run -ti --rm -e DEFAULT_BACKEND=172.16.10.1:8080 -v $(pwd)/varnish:/etc/varnish fpfis/varnish 
```