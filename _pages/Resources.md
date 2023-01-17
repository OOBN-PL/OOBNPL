---
title: Resources
order: 3
---

This page will show the resource, e.g. the paper, the patterns writing paper like PLOP, how to reference this work, etc.

<div>
{%- for fam in site.data.patFam -%}
<h3>{{ fam.family }}</h3>
  {% for p in fam.patterns %}
  <li>{{ p }}</li>
  {%- endfor -%}
{%- endfor -%}
</div>
