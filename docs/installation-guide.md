---
title: Installation Guide
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
namespace App\Models;

use Illuminate\Foundation\Auth\User as Authenticatable;

class User extends Authenticatable
{
    use \RGalura\ApiIgniter\ApiIgniter;
    use \RGalura\ApiIgniter\Projectable;
    use \RGalura\ApiIgniter\Searchable;
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

```http
GET /api/users?fields=id,name,email&search[name]=Dr*
```

✅ This should return a list of users with the Dr prefix in their names, and only the id, name, and email fields in the response.

---
<br>

## 🧭 Next Steps

Now that you’re up and running, explore more features in the [API Reference](https://rodrigogalura.github.io/api-igniter/docs/api-reference.html):

🌪️ Filtering

🌪️ In Filtering

🌪️ Between Filtering

🔃 Sorting

🔗 Expanding Relations

📄 Pagination

🧩 ~~Field Projection~~

🔍 ~~Searching~~
