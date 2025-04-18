---
title: Projection
---

# 📘 Projection

{% include features.html %}

## 🧩 Projection (`fields`, `fields!`)

The **projectable** feature allows clients to include or exclude specific fields from the API response using query parameters. This helps optimize payload size and gives frontend consumers more control over the data they receive.

---

### ✅ Include Specific Fields

<div style="display: flex; gap: 2rem; align-items: flex-start;">

<div style="flex: 1;">
<strong>Request</strong>

<pre><code>GET {{host}}/api/users?fields=id,name,email
</code></pre>

<details open>
<summary><strong>Query Parameters</strong></summary>

| Name   | Type   | Description                                |
|--------|--------|--------------------------------------------|
| fields | string | Comma-separated list of fields to include. |
</details>

</div>

<div style="flex: 1;">
<strong>Response</strong>

<pre><code>[
  {
    "id": 1,
    "name": "Benjamin Heidenreich",
    "email": "quinton42@example.net"
  },
  {
    "id": 2,
    "name": "Jairo Armstrong",
    "email": "damian83@example.org"
  }
]
</code></pre>
</div>

</div>

---

### 🚫 Exclude Specific Fields

<div style="display: flex; gap: 2rem; align-items: flex-start;">

<div style="flex: 1;">
<strong>Request</strong>

<pre><code>GET {{host}}/api/users?fields!=created_at,updated_at
</code></pre>

<details open>
<summary><strong>Query Parameters</strong></summary>

| Name    | Type   | Description                                |
|---------|--------|--------------------------------------------|
| fields! | string | Comma-separated list of fields to exclude. |
</details>

</div>

<div style="flex: 1;">
<strong>Response</strong>

<pre><code>[
  {
    "id": 1,
    "name": "Benjamin Heidenreich",
    "email": "quinton42@example.net",
    "email_verified_at": "2025-04-17T01:19:49.000000Z"
  },
  {
    "id": 2,
    "name": "Jairo Armstrong",
    "email": "damian83@example.org",
    "email_verified_at": "2025-04-17T01:19:49.000000Z"
  }
]
</code></pre>
</div>

</div>

---
