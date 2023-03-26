How to create laravel module

# Laravel Modules Structure
            app/
            bootstrap/
            config/
            database/
            Modules/
                |--- Blog/
                     |--- config/
                          |--- config.php
                     |--- database/
                          |--- migrations/
                          |--- seeds/
                               |--- BlogDatabaseSeeder.php
                     |--- Http/
                          |--- Controllers/
                          |--- Requests/
                     |--- Models/
                     |--- Providers/
                          |--- BlogServiceProvider.php
                     |--- resources/
                          |--- assets/
                          |--- lang/
                          |--- views/
                     |--- routes/
                          |--- web.php
                     |--- tests/
                     |--- composer.json
                     |--- module.json
                     |--- package.json
                     |--- start.php
                     |--- webpack.mix.js
                public/
                resources/
                routes/
                storage/
                tests/
                vendor/
                .env
                artisan
                composer.json
                composer.lock
                package.json
                phpunit.xml
                server.php
                webpack.mix.js
## Step 1 install Laravel
    laravel new Module


## Install Laravel Module Package:
      composer require nwidart/laravel-modules


## Create a Module:
     php artisan module:make <module-name>
     
## create multiple modules:
     php artisan module:make <module-name> <module-name> <module-name> <module-name>

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


## Create Migration
     php artisan module:make-migration <migration-name> <module-name>
     
## Create Model
     php artisan module:make-model <model-name> <module-name>
