---
layout: archive
permalink: /authors/
title: "Posts by Authors"
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/unsplash-image-21.jpg
  cta_label: "Read More"
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
excerpt: "作者/文章索引"
author_profile: true
---


{% include group-by-array collection=site.posts field="author" %}

{% for authorName in group_names offset:1 %}
  [{{ authorName }}](#{{ authorName }}){: .btn .btn--success .btn--large}
  {% assign posts = group_items[forloop.index] %}
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
