---
title: Use cases
order: "1"
---

A user of this OOBN PL will fall under one of two categories:
<ol type="a">
    <li>A modeler who attempts to build an OOBN model.</li>
    <li>A pattern language composer who attempts to develope a pattern language related to models' building and modeling techniques</li>
</ol>

{%- assign ps = site.pages | sort_natural: "order" -%}
<ul>
{%- for p in ps -%}
{%- if p.order -%}
<li>{{- p.title -}}</li>
{%- endif -%}
{%- endfor -%}
</ul>
