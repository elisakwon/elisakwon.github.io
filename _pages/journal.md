---
title: "Elisa Kwon - Publications"
layout: gridlay
excerpt: "Elisa Kwon -- Publications."
sitemap: false
permalink: /publications/Journal
---

# Journal papers

Below is a list of my journal papers to date, published across academic journals focused on mechanical engineering design, AI, and design research. 

{% for myyear in site.data.years %}

{% assign yeartest = true %}
{% for publi in site.data.publist %}
  {% if publi.year %}{% else %}
   {% assign yeartest = false %}
  {% endif %}
{% endfor %}

{% if site.group_pub_by_year == true %}
  {% if yeartest == true %}
## {{ myyear.year }}
  {% endif %}
{% endif %}

{% for publi in site.data.publist %}

{% if publi.abbr == "Journal" %}

{% if publi.year == myyear.year %}

{% assign bibtest = false %}
{% if publi.url %}
{% assign bibfile = "/papers/" | append:  publi.url  | append: ".txt" %}
{% for file in site.static_files %}
  {% if file.path contains bibfile %}
   {% assign bibtest = true %}
  {% endif %}
{% endfor %}
{% endif %}

<div class="well-sm">
<ul class="flex-container">
<li class="flex-item1">
    {% if publi.abbr %}<a href="{{ site.url }}{{ site.baseurl }}/papers/{{ publi.abbr }}" target="_blank"><button class="btn-pdf">{{publi.abbr}}</button></a>{% endif %}
    {% if publi.image %}
       <img src="{{ site.url }}{{ site.baseurl }}/images/{{ publi.image }}" class="img-responsive" width="200%" style="float: left" />
    {% endif %}
</li> 
<li class="flex-item2">
  <strong> {{ publi.title }}</strong> <br />
  <em>{{ publi.authors }} </em><br />
  {{ publi.display }} {% if publi.year %}({{publi.year}}){% endif %}<br/>
  {% if publi.url %}<a href="{{ site.url }}{{ site.baseurl }}/papers/{{ publi.url }}.pdf" target="_blank"><button class="btn-pdf">PDF</button></a>{% endif %}
  {% if publi.doi %}<a href="http://dx.doi.org/{{ publi.doi }}" target="_blank"><button class="btn-doi">DOI</button></a> {% endif %}
  {% if publi.abstract %} <a data-toggle="collapse" href="#{{publi.url}}" class="btn-abstract" role="button" aria-expanded="false" aria-controls="{{publi.url}}">ABSTRACT</a>{% endif %}

{% if publi.abstract %}
<br/>
<div class="collapse" id="{{publi.url}}"><div class="well-abstract">
 {{publi.abstract}}
</div></div>
{% endif %}
  
  {% if bibtest == true %}
  <div class="collapse" id="{{publi.url}}2"><div class="well-bib">
  <iframe src='{{site.url}}{{site.baseurl}}/papers/{{publi.url}}.txt' scrolling='yes' width="100%" height="210" frameborder='0'></iframe>
  </div></div>
  {% endif %}

</li>
</ul>

</div>
{% endif %}
{% endif %}
{% endfor %}
{% endfor %}
