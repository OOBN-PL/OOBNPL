---
title: Patterns
order: "05"
---

 Here you meet the building blocks of the OOBN PL, i.e. the patterns. First, the anatomy of each pattern is introduced; the anatomy reveals the sections composing the patterns and the information included in each of them. New patterns added to this OOBN PL need to follow the template provided in the anatomy and include the data it describes. Following the anatomy is the patterns catalogue, which lists all the patterns comprising the OOBN PL categorized by the family they belong to.

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
