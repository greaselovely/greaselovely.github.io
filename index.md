<!--/index.md-->
---
layout: default
---

<!-- Post -->
{% for post in site.posts %}
    <article class="post">
        <header>
            <div class="title">
                <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
                <p>{{ post.excerpt }}</p>
            </div>
            <div class="meta">
                <time class="published" datetime="{{ post.date | date: '%Y-%m-%d' }}">{{ post.date | date: "%B %d, %Y" }}</time>
                <a href="#" class="author"><span class="name">{{ post.author | default: site.author }}</span><img src="{{ site.baseurl }}/images/avatar.jpg" alt="" /></a>
            </div>
        </header>
        {% if post.image %}
            <a href="{{ post.url }}" class="image featured"><img src="{{ post.image }}" alt="" /></a>
        {% endif %}
        <p>{{ post.excerpt }}</p>
        <footer>
            <ul class="actions">
                <li><a href="{{ post.url }}" class="button large">Continue Reading</a></li>
            </ul>
            <ul class="stats">
                {% if post.categories %}
                    <li><a href="#">{{ post.categories | first }}</a></li>
                {% endif %}
                <!-- You can add more stats here if you want, like comments or likes -->
            </ul>
        </footer>
    </article>
{% endfor %}

<!-- Pagination -->
{% if paginator.total_pages > 1 %}
    <ul class="actions pagination">
        {% if paginator.previous_page %}
            <li><a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}" class="button large previous">Previous Page</a></li>
        {% else %}
            <li><a href="#" class="disabled button large previous">Previous Page</a></li>
        {% endif %}
        {% if paginator.next_page %}
            <li><a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}" class="button large next">Next Page</a></li>
        {% else %}
            <li><a href="#" class="disabled button large next">Next Page</a></li>
        {% endif %}
    </ul>
{% endif %}