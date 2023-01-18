---
title: OOBN patterns
order: "5"
---

# Object-Oriented Bayesian Network Patterns

This page will show the patterns categorized based on their family and viewed as a gallery under each category.

<div>
{%- for fam in site.data.patFam -%}
<h3>{{- fam.family -}}</h3>
  <ul>
  {%- for p in site.patterns -%}
    {%- if p.family == fam.family -%}
    <li><a href="{{ p.url | relative_url }}">{{- p.title -}}</a></li>
    {%- endif -%}
  {%- endfor -%}
  </ul>
{%- endfor -%}
</div>
