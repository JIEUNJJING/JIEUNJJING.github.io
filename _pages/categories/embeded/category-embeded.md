---
title: "Embeded Record"
layout: archive
permalink: /categories/embeded
author_profile: true
sidebar_category: true
---

{% assign posts = site.categories.embeded %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
