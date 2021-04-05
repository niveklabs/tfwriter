---
layout: default
title: Terraform Providers
tags: [ plugin, terraform, provider ]
---
# Terraform Providers

<p>Select a provider</p>

{% assign groups = "A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z" | split: "," %}
{% for group in groups %}
<h3>{{ group }}</h3>
<ul>
{% assign plugins = site.data.plugins | sort %}
{% for plugin in plugins %}
{% assign resource = plugin[1] %}
{% if group == resource.attributes.name | slice: 0 | upcase %}
  <li>
    <a href="/{{ resource.attributes.name }}/{{ resource.attributes.name }}.html">
      {{ resource.attributes.name }} 
    </a> (v{{ resource.attributes.version }})
  </li>
{% endif %}
{% endfor %}
</ul>
{% endfor %}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
