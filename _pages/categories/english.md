---
layout: archive
permalink: english
title: "English"
author_profile: true
sidebar:
  nav: "saidebar-category"

---

{% assign posts = site.categories.english %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}