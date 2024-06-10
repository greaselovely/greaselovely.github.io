---
layout: default
---

<div class="jumbotron text-center">
    <h1>{{ site.title }}</h1>
    <p class="lead">{{ site.description }}</p>
</div>

<div class="list-group mb-4">
    {% for post in site.posts %}
        <a href="{{ post.url }}" class="list-group-item list-group-item-action">
            <h5 class="mb-1">{{ post.title }}</h5>
            <p class="mb-1">{{ post.excerpt }}</p>
        </a>
    {% endfor %}
</div>

<div class="text-center">
    <a href="/about/" class="btn btn-primary">About</a>
</div>
