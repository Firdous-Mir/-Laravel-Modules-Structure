# - Laravel Modules Structure
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
     
## Create a Controller:
     php artisan module:make-controller  <controller-name> <module-name>

## Create a View:

     php artisan module:make-view <view-name> <module-name> 

## Create Migration
     php artisan module:make-migration <migration-name> <module-name>
     
## Create Model
     php artisan module:make-model <model-name> <module-name>
