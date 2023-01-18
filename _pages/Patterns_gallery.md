---
title: OOBN patterns
order: "5"
---



This page will show the patterns categorized based on their family and viewed as a gallery under each category.

## Group the patterns based on family using the ```group_by``` filter

<div>
  {%- assign pats_fams = site.patterns | group_by: 'family' | sort: "size" | reverse -%}
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
