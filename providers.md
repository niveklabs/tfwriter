---
layout: default
title: Terraform Providers
tags: plugin terraform provider
---
# Terraform Providers

[back](/)

<table>
  <tr>
    <th></th>
    <th>Full Name</th>
    <th>Tier</th>
  </tr>
{% for provider in site.data.providers %}
  <tr>
    <td>
      <a href="/{{ provider.attributes.name }}/{{ provider.attributes.name }}">
        {{ provider.attributes.name }}
      </a>
    </td> 
    <td>{{ provider.attributes.full-name }}</td>
    <td>{{ provider.attributes.tier }}</td>
  </tr>
{% endfor %}
</table>

<!-- <ul>
{% for provider in site.data.providers %}
  <li>
    <a href="/{{ provider.attributes.name }}/{{ provider.attributes.name }}.html">
      {{ provider.attributes.name }}
    </a>
  </li>
{% endfor %}
</ul> -->