---
layout: page
title: Writing Samples
permalink: /writing-samples/
image: /assets/images/writing.jpg
description: "Unpublished writing samples that highlight how I translate complex research into accessible, compelling narratives."
show_tile: true
nav-menu: true
---

<!-- Post tiles (cards) -->
{% assign samples = site.posts
  | where_exp: "p", "p.categories contains 'writing-samples' or p.tags contains 'writing-samples'"
  | sort: "date" | reverse %}

<section class="tiles tiles--samples">
  {% for post in samples %}
  <article>
    <span class="image">
      <img src="{{ post.image | default: '/assets/images/sample-placeholder.jpg' | relative_url }}" alt="{{ post.title }}">
    </span>
    <header class="major">
      <h3><a href="{{ post.url | relative_url }}" class="link">{{ post.title }}</a></h3>
      <p>{{ post.excerpt | default: post.subtitle | default: '' | strip_html | truncate: 160 }}</p>
    </header>
  </article>
  {% endfor %}
</section>

{% if samples == empty %}
<p><em>Writing samples coming soon.</em></p>
{% endif %}
