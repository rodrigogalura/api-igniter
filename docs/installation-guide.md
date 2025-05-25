---
title: Installation Guide
level: 1
order: 1
---

# 📦 Installation Guide

Follow these 3 easy steps to install and set up **Api Igniter** in your Laravel project.

## 🧰 Requirements

- PHP 8.2 or 8.3
- Laravel 10 or higher

---
<br>

## 📦 Step 1: Install via Composer

```bash
composer require rgalura/api-igniter
```

<br>

## ⚙️ Step 2: Setup

Use the <ins>ApiIgniter</ins> core trait along with any specific features you want to enable:

```php
...

use RGalura\ApiIgniter\{
    ApiIgniter, // Core
    Projectable,
    Searchable,
    # Sortable, Filterable, InFilterable, BetweenFilterable, Expandable
};

class User extends Authenticatable
{
    use ApiIgniter;
    use Projectable;
    use Searchable;
    // ...
}
```

Then, register a route that returns your model using the <ins>**send()**</ins> method:

```php
use App\Models\User;
use Illuminate\Support\Facades\Route;

Route::get('/api/users', function () {
    return User::send();
});
```

<br>

## 🧪 Step 3: Try It Out

Open your browser or an API client like Postman and try this example request:

<!-- ```

```

✅ This should return a list of users with the Dr prefix in their names, and only the id, name, and email fields in the response.

---
<br> -->

<div style="display: flex; gap: 2rem; align-items: flex-start;" class="req-res">

<div style="flex: 1;" class="highlight">
<strong>Request</strong>

<pre class="highlight"><code>GET /api/users?fields=id,name,email&search[name]=Dr*</code></pre>

</div>

<div style="flex: 1;">
<strong>Response</strong>

<pre><code>[
  { "id": 1, "name": "Dr Foo", "email": ... },
  { "id": 2, "name": "Dr Bar", "email": ... },
  { "id": 3, "name": "Dr Baz", "email": ... }
]
</code></pre>
</div>

</div>

<br>

## 🧭 Next Steps

Now that you’re up and running, explore more features in the [API Reference]({{ "/docs/api-reference.html" | relative_url }}).
