---
date: 2018-20-05T10:21:05+02:00
title: Drone Plugin PHP SDK 
weight: 15
---

Allows for creating PHP based plugins.

### Using with composer


```bash
$ composer require phpdrone/drone-plugin-sdk:~0.1
```

### Example

```php
<?php
require __DIR__."/vendor/autoload.php";

// Get the build :
$build = new \DronePluginSdk\Build();

// Get some settings :
var_dump($build->getPluginParameter('my_parameter'));
```

### Full example

See [the example included on Github](https://github.com/phpdrone/drone-plugin-sdk/tree/master/example)

### API documentation

See [the full API documentation](https://phpdrone.github.io/drone-plugin-sdk/)
