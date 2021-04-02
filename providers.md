---
layout: default
title: Terraform Providers
tags: plugin terraform provider
---
# Terraform Providers

[back](/)

<table>
  <tr>
    <th>Name</th>
    <th>Full Name <i>(Terraform 0.13 >)</i></th>
    <th>Tier</th>
  </tr>
{% for provider in site.data.providers %}
  {% if provider.attributes.tier == "official" %}
  <tr>
    <td>
      <a href="/{{ provider.attributes.name }}/{{ provider.attributes.name }}">
        {{ provider.attributes.name }}
      </a>
    </td> 
    <td>{{ provider.attributes.full-name }}</td>
    <td>{{ provider.attributes.tier }}</td>
  </tr>
  {% endif %}
{% endfor %}
</table>

<table>
  <tr>
    <th>Name</th>
    <th>Full Name <i>(Terraform 0.13 >)</i></th>
    <th>Tier</th>
  </tr>
{% for provider in site.data.providers %}
  {% if provider.attributes.tier == "partner" %}
  <tr>
    <td>
      <a href="/{{ provider.attributes.name }}/{{ provider.attributes.name }}">
        {{ provider.attributes.name }}
      </a>
    </td> 
    <td>{{ provider.attributes.full-name }}</td>
    <td>{{ provider.attributes.tier }}</td>
  </tr>
  {% endif %}
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