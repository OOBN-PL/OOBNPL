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

<!-- ## Show icon names and file names

<div>
<ul>
{%- for item in site.patterns -%}
{%- assign icf = item.icon_path | append: item.icon_name -%}
{%- assign pf_name = item.path | split: '/' | last -%}
<li>{{- pf_name | append: ": " | append: icf -}}</li>
{%- endfor -%}
</ul>
</div> -->

## Patterns with icons

<div style="text-align:center; position:relative;">
<div style="margin:1em">
  {%- assign pats_fams = site.patterns | group_by: 'family' | sort: "size" | reverse -%}
  {%- for fam in pats_fams -%}
  <h3>{{- fam.name | append: " patterns" -}}</h3>
    {%- assign pats = fam.items -%}
    {%- for p in pats -%}
      {%- assign pat_name = p.path | split: '/' | last -%}
      {%- assign icon_file = p.icon_path | append: p.icon_name -%}
         <img src="{{- icon_file | relative_url -}}" alt="{{- p.title -}} icon" class="p_icon" style="position:absolute; top:0">
         <p style="position:relative;">{{- p.title -}}</p>
    {%- endfor -%}
  {%- endfor -%}
</div>
</div>
