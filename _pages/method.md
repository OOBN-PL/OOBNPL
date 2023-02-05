---
title: Methodology
order: "01"
comments: true
---

A pattern language, in its essence, is the integration of two main components; a collection of patterns and a structure that connects these patterns in a unique arrangement. Here we describe the approach that was followed to determine both the PL structure and to compose the patterns included in it. The outcomes of the process described herein, i.e. the <span><a href="{{- site.baseurl -}}{%- link _pages/pl_structure.md -%}">PL structure</a></span> and the <span><a href="{{- site.baseurl -}}{%- link _pages/Patterns_gallery.md -%}">PL patterns</a></span> can be viewed in the respective pages.

The procedure that we followed to formalize the proposed OOBN PL is summarized in the following figure (**Fig.1**)

<a href="images/pages_imgs/PL_onto.png" onclick="window.open(this.href); return false;">
  <img src="images/pages_imgs/PL_onto.png" alt="image" class="page_img">
</a>
<b>Fig.1</b> The procedure followed to formalize the PL

Patterns are composed over three steps:

- *Pattern mining:* in this step the pattern content is gathered from a relevant source, such as expert knowledge or documented knowledge.
- *Pattern writing:* in this step the collected knowledge is documented according to a predefined pattern anatomy (the proposed OOBN PL uses <span><a href="{{- site.baseurl -}}{%- link _pages/Patterns_gallery.md-%}"><i>this pattern anatomy</i></a><span>).
- *Pattern symbolizing:* in this step the pattern is given a name and any necessary illustrations is added to the pattern so it can be easily understood.

The patterns comprising the proposed OOBN PL is quarried from documented knowledge in the domains of **Modeling**, **OOP**, and **BN**. These knowledge domains also inform the structure of the PL as we rely on renowned frameworks from these domains to link the patterns together properly. Because the ultimate goal of the OOBN PL is to enable its user to build a models that are able to tackle complex problems, the hierarchy is organized in a way that facilitate the use of a systemic approach that does not focus only on the technique used to develop the model, i.e. BN. Rather, Modeling best practices is utilized at the top level of the hierarchy, followed by software engineering practices that increases the efficiency of the model building process, and finally the patterns related to the modeling technique as shown in **Fig.2**.



<a href="images/pages_imgs/domains_hrcy.png" onclick="window.open(this.href); return false;">
  <img src="images/pages_imgs/domains_hrcy.png" alt="image" class="page_img">
</a>
<b>Fig.2</b> **a.** The OOBN PL hierarchy and the families of patterns comprising it; **b.** The arrangement of the knowledge domains informing the patterns comprising the OOBN PL; **c.** The families of the patterns comprising the OOBN PL

In order to achieve a "complete design", the patterns are mapped to the tasks that a modeller needs to follow so she/he can develop a full OOBN model that is able to handle a non-trivial problem. This also makes the PL more understandable, navigable, and easier to extend. Although finding a comprehensive map that describes the model development process is an impossible task due to the wide range of the models' applications, relying on a highly acknowledged framework that is designed to cover the widest range of models will suffice. In this work, the frameworks described by <span class="intxt_ref">Hamilton et al., 2015<sup><a href="#ref_ham15" id="hamilton15">1</a></sup></span>, <span class="intxt_ref"> Arnold, 2016<sup><a href="#ref_arno15" id="arnold15">2</a></sup></span>, and <span class="intxt_ref">Jakeman et al., 2006<sup><a href="#ref_jak06" id="jakman5">3</a></sup></span>.

<section id="refs" class="refs_section">
    <h4 class="refs_title">References</h4>
        <ol>
            <li id="ref_ham15">Hamilton, S. H., ElSawah, S., Guillaume, J. H., Jakeman, A. J. and Pierce, S. A. (2015), ‘Integrated assessment and modelling: overview and synthesis of salient dimensions’. <i>Environmental Modelling & Software</i>, 64, 215–229.<a href="#hamilton15">↩</a></li>
            <li id="ref_arno15">Arnold, T. (2016), ‘Modelling for reproducibility, transparency, and continuous learning: Revisiting Jakeman’s 10 steps’. <i>International Congress on Environmental Modelling and Software</i><a href="#arnold15">↩</a></li>
            <li id="ref_jak06">Jakeman, A. J., Letcher, R. A. and Norton, J. P. (2006), ‘Ten iterative steps in development and evaluation of environmental models’. <i>Environmental Modelling & Software</i>, 21(5), 602–614.<a href="#jakman06">↩</a></li>
        </ol>
</section>

