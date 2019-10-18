# Exedra cheatsheet

### Installation
Through composer
```
composer require rosengate/exedra
```
Through boilerplate
```
git clone https://github.com/exedron/boilerplate project-name
```

### Setup
```php
<?php
require_once __DIR__ . '/vendor/autoload.php';

$app = new \Exedra\Application(__DIR__);

return $app;
```

### Providers
```
$app->provider->add(RoutellerProvider::class);
$app->provider->add(ConsoleProvider::class);
```