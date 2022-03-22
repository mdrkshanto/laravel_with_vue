# Laravel With Vue

### Configuration Details of Laravel with Vue

**_Install Laravel Globally:_**

```js
composer global require laravel/installer
```

_Create Project:_

```js
laravel new 'Project Name'
```

---

<h3>Install Packages</h3>
<h4>Laravel Auth Packages</h4>
<h6>Breeze Package</h6>
<ol>
<li>

```js
composer require laravel/breeze --dev
```

</li>
<li>

```cs
php artisan breeze:install
```

</li>
</ol>

#

<h6>Sanctum Package</h6>

<ol>
<li>

```js
composer require laravel/sanctum
```

</li>
<li>

```js
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
```

</li>
</ol>
<h6>Sanctum Configuration</h6>
<p>Add in <code>app/Http/Kernel.php</code> file.</p>


```php
'api' => [
    \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
    'throttle:api',
    \Illuminate\Routing\Middleware\SubstituteBindings::class,
],
```