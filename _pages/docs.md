---
title: "Docs"
layout: archive
permalink: docs
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.docs %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}