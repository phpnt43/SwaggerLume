[![Build Status](https://travis-ci.org/DarkaOnLine/SwaggerLume.svg?branch=master)](https://travis-ci.org/DarkaOnLine/SwaggerLume)
[![Coverage Status](https://coveralls.io/repos/github/DarkaOnLine/SwaggerLume/badge.svg?branch=master)](https://coveralls.io/github/DarkaOnLine/SwaggerLume?branch=master)
[![Code Climate](https://codeclimate.com/repos/56a70d5ba9ee680070010a05/badges/40dbc66effc417734313/gpa.svg)](https://codeclimate.com/repos/56a70d5ba9ee680070010a05/feed)
[![StyleCI](https://styleci.io/repos/50113229/shield)](https://styleci.io/repos/50113229)
[![Total Downloads](https://poser.pugx.org/DarkaOnLine/swagger-lume/downloads.svg)](https://packagist.org/packages/DarkaOnLine/swagger-lume)

SwaggerLume
==========

Swagger 2.0 for Lumen 5

This package is a wrapper of [Swagger-php](https://github.com/zircote/swagger-php) and [swagger-ui](https://github.com/swagger-api/swagger-ui) adapted to work with Lumen 5.

Installation
============

 Lumen      | Swagger UI| OpenAPI Spec compatibility | L5-Swagger
:-----------|:----------|:---------------------------|:----------
 5.0 - 5.3  | 2.2       | 1.1, 1.2, 2.0              | ``` composer require "darkaonline/swagger-lume:~1.0" ```
 5.4.x      | 2.2       | 1.1, 1.2, 2.0              | ``` composer require "darkaonline/swagger-lume:~2.0" ```
 5.4.x      | 3         | 2.0                        | ``` composer require "darkaonline/swagger-lume:~3.0" ```
 5.5.x      | 3         | 2.0                        | ``` composer require "darkaonline/swagger-lume:5.5.*" ```


- Open your `bootstrap/app.php` file and: 

uncomment this line (around line 26) in `Create The Application` section:
```php
     $app->withFacades();
```

add this line before `Register Container Bindings` section:
```php
     $app->configure('swagger-lume');
```

add this line in `Register Service Providers` section:
```php
    $app->register(\SwaggerLume\ServiceProvider::class);
```


- Run `php artisan swagger-lume:publish-config` to publish configs (`config/swagger-lume.php`)
- Make configuration changes if needed 
- Run `php artisan swagger-lume:publish` to publish everything

Configuration
============
- Run `php artisan swagger-lume:publish-config` to publish configs (`config/swagger-lume.php`)
- Run `php artisan swagger-lume:publish-views` to publish views (`resources/views/vendor/swagger-lume`)
- Run `php artisan swagger-lume:publish` to publish everything
- Run `php artisan swagger-lume:generate` to generate docs

Changes in 3.0
============
- Swagger UI 3.
- Configuration changes.
- Assets dependency dropped. Now includes from composer package.
- [See migration from 2.0 to 3.0](#migrate-from-20-to-30-or-55)

Changes in 2.0
============
- Lumen 5.4 support
- Swagger UI 2.2.8

Migrate from 2.0 to 3.0 or 5.5
============
- Remove `config/swagger-lume.php` file (make a copy if needed)
- Remove `public/vendor/swagger-lume` directory
- Remove `resources/views/vendor/swagger-lume` directory
- Run `swagger-lume:publish` to publish new swagger-ui view and configuration
- Edit your `config/swagger-lume.php` file


Swagger-php
======================
The actual Swagger spec is beyond the scope of this package. All SwaggerLume does is package up swagger-php and swagger-ui in a Laravel-friendly fashion, and tries to make it easy to serve. For info on how to use swagger-php [look here](http://zircote.com/swagger-php/). For good examples of swagger-php in action [look here](https://github.com/zircote/swagger-php/tree/master/Examples/petstore.swagger.io).

## Support on Beerpay
Hey dude! Help me out for a couple of :beers:!

[![Beerpay](https://beerpay.io/DarkaOnLine/SwaggerLume/badge.svg?style=beer-square)](https://beerpay.io/DarkaOnLine/SwaggerLume)  [![Beerpay](https://beerpay.io/DarkaOnLine/SwaggerLume/make-wish.svg?style=flat-square)](https://beerpay.io/DarkaOnLine/SwaggerLume?focus=wish)
