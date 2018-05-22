---
date: 2018-22-05T10:21:05+02:00
title: PHP
--- 

## Introduction

For production's matching sake, the current FPFIS's Docker images are based on CentOS 6.

Two version are currently supported : `fpfis/php56` and `fpfis/php71`.

For more informations, consult the following topics :

{{% children  %}}


{{% notice info %}}
**About file permissions** : The server will use the UID and GID of the `${DOCUMENT_ROOT}` directory to run.
{{% /notice %}}
{{% notice warning %}}
**Image size** : Since the images are based on CentOS 6, the images can be quite big.
{{% /notice %}}