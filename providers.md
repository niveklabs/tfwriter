---
layout: default
title: Terraform Providers
tags: [ plugin, terraform, provider ]
---
# Terraform Providers

<ul>
{% for provider in site.data.plugins %}
  <li>
    <a href="/{{ provider.attributes.name }}/{{ provider.attributes.name }}.html">
      {{ provider.attributes.name }} ({{ provider.attributes.version }}) {{ provider.type }}
    </a>
  </li>
{% endfor %}
</ul>
