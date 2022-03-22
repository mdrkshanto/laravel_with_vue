# Laravel With Vue
### Configuration Details of Laravel with Vue

***Install Laravel Globally:***
`````js
composer global require laravel/installer
`````

*Create Project:*
````js
laravel new 'Project Name'
````
****

##### Install Packages

***Laravel Auth Packages***
````js
composer require laravel/breeze --dev
php artisan breeze:install
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
````