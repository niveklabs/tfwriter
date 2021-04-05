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
      {{ resource.attributes.name }} ({{ resource.attributes.version }})
    </a>
  </li>
{% endfor %}
</ul>
