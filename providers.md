---
layout: default
title: Terraform Providers
tags: [ plugin, terraform, provider ]
---
# Terraform Providers

<ul>
{% for provider in site.data.plugins %}
{% assign resource = site.data.plugins[provider] %}
  <li>
    <a href="/{{ resource.attributes.name }}/{{ resource.attributes.name }}.html">
      {{ resource.attributes.name }} ({{ resource.attributes.version }})
    </a>
  </li>
{% endfor %}
</ul>
