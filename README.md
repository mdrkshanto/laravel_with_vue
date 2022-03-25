<style>

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    border: none !important;
}
header{        
    margin-bottom: 3rem;
}
header h1{
    font-weight: bolder;
    font-size: 3rem;
}

</style>

<header style="border:none;">
    <h1  style="border:none;">Laravel With Vue</h1>
    <span>Configuration Details of Laravel with Vue</span>
</header>

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

<hr/>
<h2>Installing Dependency Packages with npm</h2>

```js
npm i jquery jquery-ui animate.css bootstrap bootstrap-icons vue vue-loader vue-router vuex vform vue-meta dotenv && npm i && npm run dev
```
