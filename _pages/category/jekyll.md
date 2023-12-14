---
layout: archive
permalink: jekyll
title: "Jekyll"
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.jekyll %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}