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

## Show icon names and file names

<div>
<ul>
{%- for item in site.patterns -%}
{%- assign icf = item.icon_path | append: item.icon_name -%}
<li>{{- item.file.basename -}} : {{- icf -}}</li>
{%- endfor -%}
</ul>
</div>

## Patterns with icons

<div>
  {%- assign pats_fams = site.patterns | group_by: 'family' | sort: "size" | reverse -%}
  {%- for fam in pats_fams -%}
  <h3>{{- fam.name | append: " patterns" -}}</h3>
<div class = "picon_container>
    {%- assign pats = fam.items -%}
    {%- for p in pats -%}
      {%- assign icon_file = p.icon_path | append: p.icon_name -%}
        {%- if icon_file.file.exists -%}
         <img src="{{- icon_file | relative_url -}}" alt="{{- p.data.name -}} icon" class="p_icon">
        {%- else -%}
          {%- assign def_icon = "images/picons/default_icon.png" -%}
        <img src="{{- def_icon | relative_url -}}" alt="{{- p.data.name -}} icon" class="p_icon">
          {%- endif -%}
        <p>{{- p.title -}}</p>
    {%- endfor -%}

</div>
  {%- endfor -%}
</div>
