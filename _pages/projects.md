---
layout: default
title: Benjamin Okoronkwo - Projects
permalink: /projects/
---

<h1 class="text-center mb-4">My Projects</h1>

<div class="gallery-container">
    {% assign sorted_projects = site.projects | sort: "date" | reverse %}

    {% comment %} Personal projects section: heading then list vertically {% endcomment %}
    {% assign printed = false %}
    <div class="project-section personal-projects">
      {% for project in sorted_projects %}
        {% if project.project_type == "personal" %}
          {% unless printed %}
            <h2>Personal Projects</h2>
            <div class="project-list">
            {% assign printed = true %}
          {% endunless %}
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
        {% endif %}
      {% endfor %}
      {% if printed %}</div>{% endif %}
    </div>

    {% comment %} School projects section: heading then list vertically {% endcomment %}
    {% assign printed = false %}
    <div class="project-section school-projects">
      {% for project in sorted_projects %}
        {% if project.project_type == "school" %}
          {% unless printed %}
            <h2>School Projects</h2>
            <div class="project-list">
            {% assign printed = true %}
          {% endunless %}
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
        {% endif %}
      {% endfor %}
      {% if printed %}</div>{% endif %}
    </div>

</div>