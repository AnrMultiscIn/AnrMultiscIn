---
title: "ANR - Highlights"
layout: gridlay
excerpt: "ANR -- Publications."
sitemap: false
permalink: /publications/
---


# Publications

## Group highlights

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 1 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="col">
{% endif %}

 <div class="well">
  <p><em>{{ publi.authors }}</em></p>
  <pubtit>{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="30%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
{% if publi.code %}
<p><strong><a href="{{ publi.code }}">{{ "[Source code]" }}</a></strong></p>
{% endif %}
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
 </div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>

<!--
## Full List

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}">{{ publi.link.display }}</a>

{% endfor %}
-->
