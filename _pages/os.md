---
layout: archive
title: "OS"
permalink: os
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.os %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}