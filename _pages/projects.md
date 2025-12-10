---
layout: default
title: Benjamin Okoronkwo - Projects
permalink: /projects/
---

<h1 class="text-center mb-4">My Projects</h1>

<div class="gallery-container">
<div class="project-gallery">
    {% assign sorted_projects = site.projects | sort: "date" | reverse %}
    {% for project in sorted_projects %}
      <div class="gallery-item">
        {% if project.redirect_to %}
          <a href="{{ project.redirect_to }}" target="_blank">
        {% else %}
          <a href="{{ project.url | relative_url }}">
        {% endif %}
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
            <p>{{ project.title}}</p>
          </a>
      </div>
    {% endfor %}
</div>
</div>