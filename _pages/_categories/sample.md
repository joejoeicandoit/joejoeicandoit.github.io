---
title: "Jekyll / Github Blog 만들기"
layout: archive
permalink: categories/blog
author_profile: true
sidebar_main: true
---

<!-- 공백이 포함되어 있는 카테고리 이름의 경우 site.categories['a b c'] 식으로 기술 -->

***

{% assign posts = site.categories.Blog %}
{% for post in posts %} {% incloude archive-single2.html type=page.entries_layout %} {% endfor %}