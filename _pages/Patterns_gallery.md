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
         <span>{{- p.title -}}
    {%- endfor -%}
  {%- endfor -%}
</div>
</div>

## Using the gallery approach

<h3 class="gallery-header crimson">Patterns Catalogue></h3>
<div class="gallery container">
  {%- assign pats_fams = site.patterns | group_by: 'family' | sort: "size" -%}
  {%- for fam in pats_fams -%}
    <div class="gallery category">
      <h3>{{- fam.name | append: " patterns" -}}</h3>
      <div class="gallery item">
        {%- assign patterns = fam.items -%}
        {%- for pattern in patterns -%}
          {%- assign pattern_name = pattern.path | split: '/' | last -%}
          {%- assign icon_file = pattern.icon_path | append: pattern.icon_name -%}
          <img class="p_icon" src="{{- icon_file | relative_url -}}" alt="{{- pattern.title -}}">
          <a href="{{- pattern.url | relative_url -}}"><p class="gallery_item_title">{{- pattern.title-}}</p></a>
        {%- endfor -%}
      </div>
    </div>
  {%- endfor -%}
</div>
