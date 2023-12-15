---
layout: archive
permalink: etc
title: "Etc"
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.etc %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}