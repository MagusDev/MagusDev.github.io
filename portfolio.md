---
title: Portfolio
subtitle: Here are some of the projects I've done
---

{% for project in site.data.projects %}
  <div>
    <img src="{{ project.image_url }}" alt="{{ project.name }}"/>
    <h3><a href="{{ project.github_link }}">{{ project.name }}</a></h3>
    <p>{{ project.description }}</p>
  </div>
{% endfor %}
