---
date: 2018-20-05T10:21:05+02:00
title: Composer SA Checker
tags: [ composer, security ]
---

This plugin connects to Sensiolab Security Advisories, to check if your composer.lock
contains any reference to vulnerable components.

## Usage

```
pipeline:
  test-composer-deps:
    image: phpdrone/composer-sa-checker
#   lock_file: composer.lock
```

## Result

```
Security Report
===============

No known* vulnerabilities detected.

* Disclaimer: This checker can only detect vulnerabilities that are referenced
              in the SensioLabs security advisories database.

```
