---
title: The OpenSpending Blog
layout: page
---

{% for post in site.categories.blog %}

## [{{ post.title }}]({{ post.url }})

{{ post.date | date_to_long_string }}

{% if post.authors %}
<div class="author">Written by
  <ul>
    {% for author in post.authors %}
    <li>{{ author }}</li>
    {% endfor %}
  </ul>
</div>
{% endif %}

{{ post.content | markdownify | strip_html | truncatewords: 45 }}
<br>
<a class="post-link" href="{{ post.url }}">Read More</a>

{% endfor %}
