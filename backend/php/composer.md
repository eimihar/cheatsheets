# Composer cheatsheet

## Command lines
credit : https://devhints.io/composer

### Updating packages
```
$ composer update
$ composer update --with-dependencies
$ composer update vendor/package
$ composer update vendor/*
$ composer update --lock
```

### Installing dependencies
```
composer install
composer install --dry-run
```

### Removing Packages
```
composer remove vendor/package
```

### Adding Packages
```
composer require vendor/package
composer require vendor/package --dev
```

## Schema
Just go here :
https://composer.json.jolicode.com/