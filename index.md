---
layout: index
---

{% for post in site.posts %}
    <article class="post">
        <header>
            <div class="title">
                <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
            </div>
            <div class="meta">
                <time class="published" datetime="{{ post.date | date: '%Y-%m-%d' }}">{{ post.date | date: "%B %d, %Y" }}</time>
                <a href="#" class="author"><span class="name">{{ post.author }}</span><img src="{{ site.baseurl }}/images/avatar.jpg" alt="" /></a>
            </div>
        </header>
        {{ post.excerpt  | markdownify }}
        <footer>
            <ul class="actions">
                <li><a href="{{ post.url | relative_url }}" class="button large">Continue Reading</a></li>
            </ul>
            <ul class="stats">
                {% for category in post.categories %}
                    <li><a href="#">{{ category }}</a></li>
                {% endfor %}
            </ul>
        </footer>
    </article>
{% endfor %}