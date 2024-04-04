---
layout: archive
title: "Review"
permalink: review
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.review %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}