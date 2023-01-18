---
title: Resources
order: "9"
---

This page will show the resource, e.g. the paper, the patterns writing paper like PLOP, how to reference this work, etc.

Here is a new line added to the resourced file.

## Test collection pages links

<ul>
{%- for pat in site.patterns -%}
<li><a href="{{- pat.url | relative_url -}}">{{- pat.title -}}</a></li>
{%- endfor -%}
</ul>
