---
date: 2018-24-05T10:13:05+02:00
title: Packer
--- 

## Description

Packer is a tool by [Hashicorp](https://www.packer.io/) to automatically build 
machine images.

It supports Docker, Virtualbox, AWS EC2 and many more. 

## Image

Image is named `fpfis/packer` and based on Alpine.

## Configuration

No configuration is available for this image.

## Examples

### From CLI

```bash
docker run -v $(pwd):$(pwd) -w $(pwd) -ti --rm fpfis/packer
```

### From Drone

```yaml
pipeline:
  run-packer:
    image: fpfis/packer
```
___

[![Build Status](https://drone.fpfis.eu/api/badges/ec-europa/docker-fpfis/status.svg?branch=release/packer)](https://drone.fpfis.eu/ec-europa/docker-fpfis)
[![Docker Image](https://images.microbadger.com/badges/image/fpfis/packer.svg)](https://microbadger.com/images/fpfis/packer) 
