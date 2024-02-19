---
title: "Jekyll"
layout: archive
permalink: jekyll
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.jekyll %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}