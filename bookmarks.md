---
layout: page
title: Bookmarks
permalink: /bookmarks/
---

{% assign bookmarks_by_month = site.bookmarks | reverse | group_by_exp: "b", "b.date | date: '%B %Y'" %}

{% for month in bookmarks_by_month %}
## {{ month.name }}

{% for bm in month.items %}
- [{{ bm.title }}]({{ bm.url | relative_url }}) {% if bm.source_url %}([source]({{ bm.source_url }})){% endif %} <small>{{ bm.date | date: "%b %d" }}</small>
  {{ bm.summary | default: "" }}
{% endfor %}
{% endfor %}
