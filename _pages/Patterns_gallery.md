---
title: OOBN patterns Catalogue
order: "5"
---



This page will show the patterns categorized based on their family and viewed as a gallery under each category.

<!-- <h3 class="gallery-header crimson">Patterns Catalogue</h3> -->
<div class="gallery container">
  {%- assign pats_fams = site.patterns | group_by: 'family' | sort: "size" -%}
  {%- for fam in pats_fams -%}
    <div class="gallery category">
      <h2>{{- fam.name | append: " patterns" -}}</h2>
      <div class="gallery item">
        {%- assign patterns = fam.items -%}
        {%- for pattern in patterns -%}
          {%- assign icon_file = pattern.icon_path | append: pattern.icon_name -%}
          <img class="p_icon" src="{{- icon_file | relative_url -}}" alt="{{- pattern.title -}}">
          <a href="{{- pattern.url | relative_url -}}"><p class="gallery_item_title">{{- pattern.title-}}</p></a>
        {%- endfor -%}
      </div>
    </div>
  {%- endfor -%}
</div>
