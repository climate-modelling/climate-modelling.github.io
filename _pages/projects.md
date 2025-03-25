---
title: " "
layout: posts
permalink: /projects/
entries_layout: grid
classes: wide
---

# Projects

Samples of published and ongoing projects by the Climate Analytics Lab. Sort them by computational or Earth Science tags.

{% case site.tag_archive.type %}
  {% when "liquid" %}
    {% assign path_type = "#" %}
  {% when "jekyll-archives" %}
    {% assign path_type = nil %}
{% endcase %}

<p class="page__taxonomy">
  <span itemprop="keywords">
  {% for tag in site.tags %}
    <a href="{{  tag[0] | slugify | prepend: path_type | prepend: site.tag_archive.path | relative_url }}" class="page__taxonomy-item p-category" rel="tag">{{ tag[0] }}</a>{% unless forloop.last %}<span class="sep">, </span>{% endunless %}
  {% endfor %}
  </span>
</p>

<!-- Coming soon! -->