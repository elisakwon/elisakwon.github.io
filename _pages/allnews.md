---
title: "News"
layout: textlay
excerpt: "Elisa Kwon - news updates"
sitemap: false
permalink: /allnews.html
---

# News

{% for article in site.data.news %}
<p><b>{{ article.date }}</b> <br>
<em>{{ article.headline | markdownify}}</em></p>
{% endfor %}
