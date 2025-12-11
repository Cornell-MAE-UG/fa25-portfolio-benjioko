---
layout: default
title: Benjamin Okoronkwo - Projects
permalink: /projects/
---

<h1 class="text-center mb-4">My Projects</h1>

<div class="projects-wrapper">
  {% assign sorted_projects = site.projects | sort: "date" | reverse %}
  {% assign categories = "personal,club,coursework" | split: "," %}

  {% for cat in categories %}
    {% assign group = sorted_projects | where: "project_type", cat %}
    {% if group.size > 0 %}
      <section class="project-section">
        <h2 class="mt-5 mb-3">{{ cat | capitalize }} Projects</h2>

        <div class="gallery-container">
          <div class="project-gallery">
            {% for project in group %}
              <div class="gallery-item">
                {% if project.redirect_to %}
                  <a href="{{ project.redirect_to }}" target="_blank">
                {% else %}
                  <a href="{{ project.url | relative_url }}">
                {% endif %}
                    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
                    <p>{{ project.title }}</p>
                  </a>
              </div>
            {% endfor %}
          </div>
        </div>
      </section>
    {% endif %}
  {% endfor %}

  {% assign remaining_groups = sorted_projects | group_by: "project_type" %}

  {% for grp in remaining_groups %}
    {% unless categories contains grp.name %}
      <section class="project-section">
        <h2 class="mt-5 mb-3">{{ grp.name | capitalize }} Projects</h2>

        <div class="gallery-container">
          <div class="project-gallery">
            {% for project in grp.items %}
              <div class="gallery-item">
                {% if project.redirect_to %}
                  <a href="{{ project.redirect_to }}" target="_blank">
                {% else %}
                  <a href="{{ project.url | relative_url }}">
                {% endif %}
                    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
                    <p>{{ project.title }}</p>
                  </a>
              </div>
            {% endfor %}
          </div>
        </div>
      </section>
    {% endunless %}
  {% endfor %}
</div>