---
layout: page
title: Wiki
permalink: /wiki/
---

# Wiki Home

Welcome to our project wiki. Here you'll find documentation and guides.

## Recent Updates

{% assign wiki_pages = site.wiki | sort: 'date' | reverse %}
{% for page in wiki_pages limit:5 %}
- [{{ page.title }}]({{ page.url | relative_url }}) - {{ page.date | date: "%B %d, %Y" }}
{% endfor %}

## All Wiki Pages

{% assign wiki_pages = site.wiki | sort: 'title' %}
{% for page in wiki_pages %}
- [{{ page.title }}]({{ page.url | relative_url }})
{% endfor %}