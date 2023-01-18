---
title: OOBN patterns
order: "5"
---



This page will show the patterns categorized based on their family and viewed as a gallery under each category.

<!-- <div>
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
-->

<div>
{%- for fam in site.data.patFam -%}
<h3>{{- fam.family | append: " patterns" -}}</h3>
  <ul>
  {%- for p in site.patterns -%}
    {%- if p.family == fam.family -%}
    <li>{{- p.title -}}</li>
    {%- endif -%}
  {%- endfor -%}
  </ul>
{%- endfor -%}
</div>

## Group the patterns based on family using the ```group_by``` filter

<div>
  {%- assign pats_fams = site.patterns | group_by: 'family' -%}
  {%- for fam in pats_fams -%}
  <h3>{{- fam.name | append: " patterns" -}}</h3>
  <ul>
    {%- assign pats = fam.items -%}
    {%- for p in pats -%}
    <li>{{- p.title -}}</li>
    {%- endfor -%}

  </ul>
  {%- endfor -%}
</div>
