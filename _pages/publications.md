---
title: "Elisa Kwon - Publications"
layout: gridlay
excerpt: "Elisa Kwon -- Publications."
sitemap: false
permalink: /publications/
---

My research explores human behavior and cognition during the design process, especially when faciliated by AI-enabled systems. I am interested in answering how AI support for design can be effectively developed and employed, drawing on insights from empirical human subject studies and cognitive psychology and neuroscience.   

# Publications

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}">{{ publi.link.display }}</a>

{% endfor %}
