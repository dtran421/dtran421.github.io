---
layout: page
permalink: /repositories/
title: repositories
description: These are some projects that I've worked on in the past.
nav: true
nav_order: 4
---

{% if site.data.repositories.github_users %}

## GitHub Profile

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}

{% for user in site.data.repositories.github_users %}

{% if site.data.repositories.github_users.size > 1 %}

<h4>{{ user }}</h4>
{% endif %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
</div>

---

{% endfor %}
{% endif %}
{% endif %}

{% if site.data.repositories.github_repos %}

## GitHub Repositories

{% for repo_group in site.data.repositories.github_repos %}

<h4>{{  repo_group.name  }}</h4>

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center mb-4">
    {% for repo in repo_group.repos %}
      {% include repository/repo.liquid repository=repo %}
    {% endfor %}
</div>

{% endfor %}

{% endif %}
