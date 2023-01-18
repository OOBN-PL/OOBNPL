---
title: OOBN patterns
order: "5"
---

# Object-Oriented Bayesian Network Patterns

This page will show the patterns categorized based on their family and viewed as a gallery under each category.

<div>
{%- for fam in site.data.patFam -%}
<h3>{{ fam.family }}</h3>
  {% for p in fam.patterns %}
  <li>{{ p }}</li>
  {%- endfor -%}
{%- endfor -%}
</div>

{%- for p in site.patterns -%}
<h4><a href="{{ p.url }}">{{- p.title -}}</a></h4>
{%- endfor -%}
