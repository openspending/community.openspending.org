---
title: Presentations
section: about
---

{% for spage in site.pages %}{% if spage.presentation %}
[{{ spage.title }}]({{ spage.url }})
{% endif %}{% endfor %}
