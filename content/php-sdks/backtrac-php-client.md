---
date: 2018-22-05T10:21:05+02:00
title: Backtrac PHP client
--- 
This projects includes both a client library and a phing helper to trigger visual comparison.

## Usage

### API Documentation

See the [generated documentation](/libs/namespaces/EC.Utils.Backtrac.html)

### Installation

```sh
composer require ec-europa/backtrac-php-client:~0.1
```

## Examples

### Usage as library


```php
<?php
require_once __DIR__.'/../vendor/autoload.php';
$client = new \EC\Utils\Backtrac\Client(
    1,
    'aaaaaaaaaaaaaaa'
);

/**
 * Create a website object
 */
$website = new \EC\Utils\Backtrac\Website('test-site','http://ci-test.com');

/**
 * Set the new url for dev :
 */
$client->setDevWebsite($website);

/**
 * Compare prod a dev :
 */
$diffId = $client->compareEnvironments(
  \EC\Utils\Backtrac\Client::COMPARE_PROD_DEV
)->result->nid;

/**
 * Wait for the end of the diff and display result :
 */

var_dump(
  $client->waitForResults($diffId)
);

/**
 * Custom compare :
 */
var_dump(
    $client->customCompare(
        'my_diff',
        new \EC\Utils\Backtrac\Website('site_1','http://xxxx.yyy/zzz'),
        new \EC\Utils\Backtrac\Website('site_2', 'http://xxx.yyy/zzzzw')
    )
);
```

### Usage as Phing task

```xml
<?xml version="1.0" ?>

<project default="backtrac-compare-self" name="test" basedir=".">
    <!-- Import the phing tasks into your project. -->
    <import file="${project.basedir}/vendor/ec-europa/backtrac-php-client/phing/import.xml" />
    
    <!-- Example target to update a website url for an environment. -->
    <target name="backtrac-update-url">
        <backtrac-set-url secure="true" environment="development" url="http://xyz.com" project_id="12" auth_token="xxxxxxxx" />
    </target>
 
    <!-- Example target for comparing different environments: prod and dev. -->
    <target name="backtrac-compare-prod-dev">
        <backtrac-compare secure="true" compare_mode="compare_prod_dev" project_id="12" check_results="true" auth_token="xxxxxxxx" />
    </target>

    <!-- Example target to take single snapshot: before deployment or build. -->
    <target name="backtrac-single-snapshot">
        <backtrac-compare secure="true" compare_mode="snapshot" environment="production" project_id="12" check_results="false" auth_token="xxxxxxxx" />
    </target>
    
    <!-- Example target for comparing environment to latest snapshot: after deployment or build. -->
    <target name="backtrac-compare-self">
        <backtrac-compare secure="true" compare_mode="compare_itself" environment="production" project_id="12" check_results="false" auth_token="xxxxxxxx" />
    </target>
</project>
```

[![Build Status](https://drone.fpfis.eu/api/badges/ec-europa/backtrac-php-client/status.svg?branch=master)](https://drone.fpfis.eu/ec-europa/backtrac-php-client)
