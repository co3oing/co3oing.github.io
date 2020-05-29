---
layout: default
title: Git
parent: Manual
has_children: true
nav_order: 1
---

<ul class="catalogue">
{% assign sorted = site.html_pages | sort: 'nav_order' | reverse %}
{% for page in sorted %}
{% if page.parent == "Git" %}
{% include post-list.html %}
{% endif %}
{% endfor %}
</ul>
