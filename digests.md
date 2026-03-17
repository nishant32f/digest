---
layout: page
title: All Digests
permalink: /digests/
---

{% assign digests_by_month = site.digests | reverse | group_by_exp: "d", "d.date | date: '%B %Y'" %}

{% for month in digests_by_month %}
## {{ month.name }}

{% for digest in month.items %}
- [{{ digest.title }}]({{ digest.url | relative_url }}) <small>{{ digest.date | date: "%b %d, %l:%M %p" }}</small>
{% endfor %}
{% endfor %}
