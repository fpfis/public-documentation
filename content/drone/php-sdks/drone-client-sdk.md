---
date: 2018-20-05T10:21:05+02:00
title: Drone Client PHP SDK 
weight: 15
---
{{% notice warning %}}
The client SDK is currently unstested an a work in progress
{{% /notice %}}

## Using with composer

```
$ composer require gboddin/php-drone-client
```

## Getting Started

Please follow the [installation procedure](#using-with-composer) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: accessToken
DroneClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// DroneClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');

$api_instance = new DroneClient\Api\BuildsApi();
$owner = "owner_example"; // string | owner of the repository
$name = "name_example"; // string | name of the repository

try {
    $result = $api_instance->reposOwnerNameBuildsGet($owner, $name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BuildsApi->reposOwnerNameBuildsGet: ', $e->getMessage(), PHP_EOL;
}

?>
```