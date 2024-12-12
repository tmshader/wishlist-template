* TOC
{:toc .bg-white .p-3 .border .border-2 .border-danger .rounded-4 .shadow}

<!-- TOC -->

{% for header in page.category_headers %}
---
{: .border .border-2 .border-warning .opacity-100 .rounded-pill}

## {{ header[1].header }} ##
{: .text-bg-success .rounded-4 .p-2 .shadow .mb-3 id="{{ header[1].id }}"}

{% assign categories = page.categories | where_exp: "category", "category.type == header[0]" %}
{% for category in categories %}

{% assign wishlist = page.wishlist | sort: "price" | where_exp: "wish", header[1].filter %}

{% if wishlist.size == 0 %}{% continue %}{% endif %}

<div class="rounded-4 shadow mb-4" markdown="1">

### {{ category.name }} ###
{: .text-bg-danger .rounded-top-4 .p-2 .mb-0 id="{{ category.id }}"}

<div class="p-3 border border-2 border-top-0 border-danger rounded-bottom-4 bg-white">

{% include wish.html %}

</div>
</div>

{% endfor %}
{% endfor %}