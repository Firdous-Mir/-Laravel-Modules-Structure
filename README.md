# - Laravel Modules Structure
<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## Laravel Module

## Step 1 install Laravel
    laravel new Module


## Install Laravel Module Package:
      composer require nwidart/laravel-modules


## Create a Module:
     php artisan module:make <module-name>

## Register the Module:  'config/app.php'
    'providers' => [
    // Other Service Providers
    Nwidart\Modules\LaravelModulesServiceProvider::class,
    ],

    'aliases' => [
        // Other Aliases
        'Module' => Nwidart\Modules\Facades\Module::class,
    ],

### Also do changes in Composer.js
    "autoload": {
        "psr-4": {
            "App\\": "app/",
            "Modules\\": "modules/",  // add Modules here 
            "Database\\Factories\\": "database/factories/",
            "Database\\Seeders\\": "database/seeders/"
        }
    },


## Create a Controller:
     php artisan module:make-controller <module-name> <controller-name>

## Create a View:

     php artisan module:make-view <module-name> <view-name>

## Create a Route: Routes/web.php
     Route::get('/create',[LoginController::class,'create']);
