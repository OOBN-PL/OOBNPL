---
title: Patterns Details
order: "05"
---



This page will show the patterns categorized based on their family and viewed as a gallery under each category.

## Pattern Anatomy

Each of the patterns has the following anatomy, this represents that template that needs to be filled for any additional patterns that will be added to the OOBN PL:

<div class="pattern_template" id="pAnatomyTable">
    {%- capture mdTable -%}{%- include pat_template_table.md -%}{%- endcapture -%}
    {{- mdTable | markdownify -}}
</div>

## Patterns Catalogue
<!-- <h3 class="gallery-header crimson">Patterns Catalogue</h3> -->
<div class="gallery container">
  {%- assign pats_fams = site.patterns | group_by: 'family' | sort: "size" -%}
  {%- for fam in pats_fams -%}
    <div class="gallery category">
      <span class= "fam_title"><h3>{{- fam.name | append: " patterns" -}}</h3></span>
      <div class="gallery item">
        {%- assign patterns = fam.items -%}
        {%- for pattern in patterns -%}
          {%- assign icon_file = pattern.icon_path | append: pattern.icon_name -%}
          <p><a href="{{- pattern.url | relative_url -}}"><img class="p_icon" src="{{- icon_file | relative_url -}}" alt="{{- pattern.title -}}">
          <span class="gallery_item_title">{{- pattern.title-}}</span></a></p>
        {%- endfor -%}
      </div>
    </div>
  {%- endfor -%}
</div>
