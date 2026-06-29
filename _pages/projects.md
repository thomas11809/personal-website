---
title: "Projects"
layout: archive
permalink: /projects/
author_profile: true
---

Selected side projects spanning startups, media art, and applied AI — each post is a hands-on retrospective / case study.

{% assign project_categories = "Start-up,Media Art" | split: "," %}
{% for category in project_categories %}
  {% assign posts = site.categories[category] %}
  {% if posts %}
## {{ category }}
{% for post in posts %}{% include archive-single.html post=post %}{% endfor %}
  {% endif %}
{% endfor %}
