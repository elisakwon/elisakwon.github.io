---
title: "News"
layout: textlay
excerpt: "Elisa Kwon - news updates"
sitemap: false
permalink: /allnews.html
---

# News

{% for article in site.data.news %}
<b>{{ article.date }}</b> <br>
{{ article.headline | markdownify}}
{% endfor %}
