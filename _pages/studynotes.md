---
layout: archive
title: "Study Notes"
permalink: /studynotes/
#collection: studynotes
#entries_layout: grid
author_profile: true
use_math: true
---

Welcome to my study notes! Here, you'll find a collection of technical references, derivations, and summaries spanning photonics, physics, mathematics, machine learning, computational electromagnetics, and other random topics.

These notes serve as both my personal knowledge base and a resource for others interested in similar topics. Please let me know if you find any errors or have any comments 😊

{% include base_path %}

{% assign notes = site.studynotes | sort: "date" | reverse %}

{% comment %}
  Get all study notes and sort them by topic, then title.
{% endcomment %}
{% assign notes = site.studynotes | sort: "title" %}
{% assign topics = notes | map: "topic" | uniq | sort %}

{% for t in topics %}
  <h2 id="{{ t | slugify }}" class="archive__subtitle">{{ t }}</h2>

  {% for post in notes %}
    {% if post.topic == t %}
      {% include archive-single.html %}
    {% endif %}
  {% endfor %}
{% endfor %}