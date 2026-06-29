---
layout: archive
title: "Teaching"
permalink: /teaching/
author_profile: true
---

{% include base_path %}

{% assign teaching_posts = site.teaching | sort: "date" | reverse %}

<h2>Choisir une experience d'enseignement</h2>
<ul>
{% for post in teaching_posts %}
  <li>
    <a href="{{ post.url | relative_url }}">
      {% if post.period %}
        {{ post.period }}
      {% else %}
        {{ post.date | date: "%Y" }}
      {% endif %}
      - {{ post.title }}
    </a>
    {% if post.venue %}
      ({{ post.venue }})
    {% endif %}
  </li>
{% endfor %}
</ul>

<h2>GitHub Releases des cours</h2>
<ul>
  <li><a href="https://github.com/jfolivie/RessourcesEnseignements_JFO/releases">RessourcesEnseignements_JFO - Releases</a></li>
  <li><a href="https://github.com/jfolivie/RessourcesEnseignements_JFO">Depot des ressources de cours</a></li>
</ul>

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
