---
layout: default
title: Terraform Providers
tags: [ plugin, terraform, provider ]
---
# Terraform Providers

<p>Select a provider</p>

<ul>
{% for plugin in site.data.plugins %}
{% assign resource = plugin[1] %}
  <li>
    <a href="/{{ resource.attributes.name }}/{{ resource.attributes.name }}.html">
      {{ resource.attributes.name }} 
    </a> (v{{ resource.attributes.version }})
  </li>
{% endfor %}
</ul>

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
