---
title: Sort
---

# 🔃 Sorting

{% include features.html %}

## 🔢 Sorting (`sort[]`)

The **sortable** feature allows clients to specify the order in which results are returned by one or more fields. This helps improve data presentation on the frontend.

---

### ⬆️ Ascending Order

<div style="display: flex; gap: 2rem; align-items: flex-start;">

<div style="flex: 1;">
<strong>Request</strong>

<pre><code>GET /api/users?sort[name]</code></pre>

<sup>Where <ins>name</ins> is the field to be targeted for sorting in ascending order.</sup>

---

<details open class="sup">
<summary><strong>Query Parameters</strong></summary>

| Name | Type  | Description                                    |
|------|-------|------------------------------------------------|
| sort | array | **Key** - Target field.<br>**Value** - *blank* |

</details>
</div>

<div style="flex: 1;">
<strong>Response</strong>

<pre><code>[
  {
    "id": 86,
    "name": "Arch Kessler",
    "email": "nitzsche.hellen@example.com",
    ...
  },
  {
    "id": 52,
    "name": "Aylin Runolfsson",
    "email": "schmeler.harry@example.net",
    ...
  },
  {
    "id": 1,
    "name": "Benjamin Heidenreich",
    "email": "quinton42@example.net",
    ...
  }
]
</code></pre>
</div>

</div>

---

### ⬇️ Descending Order

<div style="display: flex; gap: 2rem; align-items: flex-start;">

<div style="flex: 1;">
<strong>Request</strong>

<pre><code>GET /api/users?sort[id]=-</code></pre>

<sup>Where <ins>id</ins> is the field to be targeted and <ins>\-</ins> is the indicator that data should be in descending order.
Other accepted indicators: <ins>d</ins>, <ins>des</ins>, <ins>desc</ins>, <ins>descending</ins>.</sup>

<details open class="sup">
<summary><strong>Query Parameters</strong></summary>

| Name  | Type  | Description                                                   |
|-------|-------|---------------------------------------------------------------|
| sort  | array | **Key** - Target field.<br>**Value** - <ins>-</ins> or <ins>d</ins> or <ins>des</ins> or <ins>desc</ins> or <ins>descending</ins> |
</details>
</div>

<div style="flex: 1;">
<strong>Response</strong>

<pre><code>[
  {
    "id": 101,
    "name": "Test User",
    "email": "test@example.com",
    ...
  },
  {
    "id": 100,
    "name": "Cayla Ankunding MD",
    "email": "joey.mohr@example.com",
    ...
  },
  {
    "id": 99,
    "name": "Jan Ferry",
    "email": "sarmstrong@example.net",
    ...
  }
]
</code></pre>
</div>

</div>

---
