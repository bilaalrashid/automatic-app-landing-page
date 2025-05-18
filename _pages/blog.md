---
layout: page
title: Blog
include_in_header: false
include_in_footer: true
---

{% assign sorted_pages = site.pages | sort:date | reverse %}
{% for page in sorted_pages %}
  {% if page.path contains 'blog/' %}
  <article>
    <a href="{{ page.url | relative_url }}">
      <h1>{{ page.title }}</h1>
      <p class="subtitle">{{ page.description }}</p>
      <p>Read more...</p>
    </a>
  </article>
  {% endif %}
{% endfor %}
