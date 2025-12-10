---
layout: default
title: Benjamin Okoronkwo - Projects
permalink: /projects/
---

<h1 class="text-center mb-4">My Projects</h1>

<div class="gallery-container">
<div class="project-gallery">
    {% assign sorted_projects = site.projects | sort: "date" | reverse %}

    {% assign school_projects = sorted_projects | where: "project_type", "school" %}
    {% assign personal_projects = sorted_projects | where: "project_type", "personal" %}
    {% assign other_projects = sorted_projects | where_exp: "p", "p.project_type == nil or p.project_type == ''" %}

    {% if personal_projects.size > 0 %}
      <h2>Personal Projects</h2>
      {% for project in personal_projects %}
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
    {% endif %}

    {% if school_projects.size > 0 %}
      <h2>School Projects</h2>
      {% for project in school_projects %}
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
    {% endif %}

    {% if other_projects.size > 0 %}
      <h2>Other Projects</h2>
      {% for project in other_projects %}
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
    {% endif %}
</div>
</div>