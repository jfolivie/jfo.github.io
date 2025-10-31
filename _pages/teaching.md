---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

{% comment %}
This groups teaching posts by their 'category' field.
Each file in _teaching/ should include a line like:
category: "University" or category: "Workshop"
{% endcomment %}

{% assign teaching_categories = site.teaching | group_by: "category" %}

{% for category in teaching_categories %}
  <h2>{{ category.name }}</h2>
  {% for post in category.items %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}
