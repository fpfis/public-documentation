---
date: 2018-22-05T10:21:05+02:00
title: iTopApi
--- 
iTopApi PHP is an helper class to use and query the [iTop](https://wiki.openitop.org/doku.php) API from your PHP scripts.


## Usage

### API documentation

See the [generated documentation](/libs/namespaces/iTopApi.html).

### Installation

```
composer require ec-europa/itopapi
```

## Examples


### Getting data

```php
require 'vendor/autoload.php';

$iTopAPI = new \iTopApi\ITopClient( 'http://localhost/itop', 'itopUser', 'iTopPassword' );

//disable SSL checks ?
//$iTopAPI->setCertificateCheck(false);

$query = sprintf("SELECT Servers WHERE environment = '%s'",'development');

$serversRequest = $iTopAPI->coreGet("Servers",$query);

$servers = $serverRequest['objects'];
```

### Creating data

```php
require 'vendor/autoload.php';

$iTopAPI = new \iTopApi\ITopClient( 'http://localhost/itop', 'itopUser', 'iTopPassword' );

//disable SSL checks ?
//$iTopAPI->setCertificateCheck(false);

$request = $iTopAPI->coreCreate("Servers",array(
  'hostname' => 'localhost',
  'memory' => 2048,
  'cpu' => 4,
  'location' => 'dc1'
));

```



### Updating data

```php
require 'vendor/autoload.php';

$iTopAPI = new \iTopApi\ITopClient( 'http://localhost/itop', 'itopUser', 'iTopPassword' );

//disable SSL checks ?
//$iTopAPI->setCertificateCheck(false);

$request = $iTopAPI->coreUpdate("Servers",array(
  'hostname' => 'localhost'
),array(
  'memory' => 1024
));

```

### Using object oriented

```php
require 'vendor/autoload.php';

$iTopAPI = new \iTopApi\ITopClient( 'http://localhost/itop', 'itopUser', 'iTopPassword' );

//disable SSL checks ?
//$iTopAPI->setCertificateCheck(false);


/**
 * Query and iterate 
 */

$servers = $iTopAPI->getObjects("Server",
  array(
    'name' => 'server001'
  )
);

foreach($servers as $server) {
  echo $server->name.' is '.$server->status_friendlyname;
  $server->name = 'server001-eu';
  $server->save();
}


/**
 * Deletes a new server : 
 */
if($server->status_friendlyname == 'decommissioning')
  $server->delete();
  
  
/**
 * Creates a new server : 
 */
$server = $iTopClient->getNewObject('Server');

$server->name = 'server002';
$server->status_friendlyname = 'deployed';
$server->save();

```

[![Build Status](https://drone.fpfis.eu/api/badges/ec-europa/iTopApi/status.svg?branch=master)](https://drone.fpfis.eu/ec-europa/iTopApi)
