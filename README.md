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



<p>
<p>
<h3>Install Packages</h3>
<h4>Laravel Auth Packages</h4>
<h6>Breeze Package</h6>
<ol>
<li>

````js
composer require laravel/breeze --dev
````
</li>
<li>

````js
php artisan breeze:install
````
</li>
</ol>
</p>
<hr/>

***Sanctum Package***
````js
composer require laravel/sanctum
````
````js
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
````

***Configure Sanctum Package***
````js
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
````
</p>


