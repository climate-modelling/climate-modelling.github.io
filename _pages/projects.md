---
title: "Projects"
layout: posts
permalink: /projects/
entries_layout: grid
classes: wide
---

Samples of published and ongoing projects by the Climate Modelling Research Group.
These are also intended to give prospective students project ideas, particularly
have a look at those tagged ["OPEN"](https://climate-modelling.github.io/tags/#open)
but feel free to reach out with your own ideas too!

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
