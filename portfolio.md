---
title: Portfolio
subtitle: Here are some of the projects I've done
---

<table>
{% for project in site.data.projects %}
  {% if forloop.index0 | modulo:2 == 0 %}
  <tr>
  {% endif %}
    <td>
      <img src="{{ project.image_url }}" alt="{{ project.name }}"/><br>
      <a href="{{ project.github_link }}">{{ project.name }}</a><br>
      {{ project.description }}
    </td>
  {% if forloop.index0 | modulo:2 == 1 %}
  </tr>
  {% endif %}
{% endfor %}
</table>
