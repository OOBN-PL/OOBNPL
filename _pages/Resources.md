---
title: Resources
order: 3
---

This page will show the resource, e.g. the paper, the patterns writing paper like PLOP, how to reference this work, etc.

{%- for fam in site.data.patFam -%}
<h2>{{ fam.family }}</h2>
<ul>
  {% for p in fam.patterns %}
  {{ p }}
  {%- endfor -%}
</ul>
{%- endfor -%}
