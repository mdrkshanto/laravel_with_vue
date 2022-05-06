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

<hr/>
<h2>Installing Dependency Packages with npm</h2>

```js
npm i jquery jquery-ui animate.css bootstrap bootstrap-icons vue vue-loader vue-router vuex vform vue-meta dotenv && npm i && npm run dev
```

<hr/>

<h2>Configurations:</h2>

<h5>Webpack Configure</h5>
<span>Add in <code>webpack.mix.js</code></span>

```js
const mix = require("laravel-mix");

mix
  .js("resources/js/app.js", "public/js")
  .vue()
  .postCss("resources/css/app.css", "public/css");
```

<h5>js Configure</h5>

<ol>
<li>
<span>Add in <code>resources\js\bootstrap.js</code></span>

```js
window._ = require("lodash");

try {
  window.$ = window.jquery = window.jQuery = require("jquery");
  window.bs5 = require("bootstrap/dist/js/bootstrap.bundle.min");
  window.Vue = require("vue");
  window.Vuex = require("vuex");
  window.VueRouter = require("vue-router");
  window.VueMeta = require("vue-meta");
} catch (error) {}
import Form from "vform";
window.Form = Form;
window.axios = require("axios");

window.axios.defaults.headers.common["X-Requested-With"] = "XMLHttpRequest";

/**
 * Echo exposes an expressive API for subscribing to channels and listening
 * for events that are broadcast by Laravel. Echo and event broadcasting
 * allows your team to easily build robust real-time web applications.
 */

// import Echo from 'laravel-echo';

// window.Pusher = require('pusher-js');

// window.Echo = new Echo({
//     broadcaster: 'pusher',
//     key: process.env.MIX_PUSHER_APP_KEY,
//     cluster: process.env.MIX_PUSHER_APP_CLUSTER,
//     forceTLS: true
// });
```

</li>

<li>
<span>Add in <code>resources\js\app.js</code></span>

```js
require("./bootstrap");
import storeData from "./storeData";
const store = Vuex.createStore(storeData);
import { routes } from "./routes";
const router = VueRouter.createRouter({
  history: VueRouter.createWebHistory(),
  routes,
});
router.beforeEach((to, from, next) => {
  document.title = "Shanto" + " | " + to.meta.title;
  next();
});
const app = Vue.createApp({});
app.component("Admin", require("../components/backEnd/master/index").default);
app.use(store);
app.use(router);
app.mount("#app");
```

</li>
</ol>

<h5>CSS Configure</h5>

```css
@import "bootstrap";
@import "bootstrap-icons";
@import "animate.css";
```

<hr>

<h3>Laravel Image Intervention Package</h3>

#

<h4>Installation:</h4>

```js
composer.phar require intervention/image
```

<h5>Configurations:</h5>

<p>After you have installed Intervention Image, open your Laravel config file <code>config/app.php</code> and add the following lines.</p>
<p>In the <code>$providers</code> array add the service providers for this package.</p>

```php
Intervention\Image\ImageServiceProvider::class,
```

<p>Add the facade of this package to the <code>$aliases</code> array.</p>

```php
'Image' => Intervention\Image\Facades\Image::class,
```

<h5>Publish configuration in Laravel:</h5>

```js
php artisan vendor:publish --provider="Intervention\Image\ImageServiceProviderLaravelRecent"
```