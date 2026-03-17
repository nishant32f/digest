---
layout: home
title: Home
---

## Latest Digests

{% for digest in site.digests reversed limit:10 %}
### [{{ digest.title }}]({{ digest.url | relative_url }})
<small>{{ digest.date | date: "%B %d, %Y %l:%M %p" }} · {{ digest.categories | join: ", " }}</small>

{{ digest.excerpt }}

---
{% endfor %}

[All digests →](/digest/digests/)
