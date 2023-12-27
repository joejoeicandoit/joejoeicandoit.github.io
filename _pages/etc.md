---
layout: archive
permalink: etc
#title: "끄적끄적"
author_profile: true
sidebar:
  nav: "saidebar-category"
---

{% assign posts = site.categories.etc %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}