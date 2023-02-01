---
family: BN
title: "Almost never"
icon_name: almost_never_ico.png
---

**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:**

    3. The technical implementation

**Modeling step:**

    7. Identification of model structure and parameters' values

**Problem:**

Assigning probabilities of *zero* as parameters to some variable's CPT. This can happen in the case when CPT values are filled manually and the modeller (or the expert) denote some events as impossible, or when CPTs are learned from discretized data and some intervals have occurrence frequency of zero. While some events can be logically impossible, assigning a *zero* probability to them, i.e. introducing a *zero* probability to the network, will negatively affect the model's diagnostic accuracy and increases its sensitivity to imprecision in other parameters numerical values.

***

**Solution:**

The solution depends on the method CPTs are formalized:

- In the case CPTs are elicited from domain experts:

    1. CPTs are formalized to reflect the domain knowledge, i.e. *zero*
        probabilities are assigned to impossible cases and probabilities
        of 1 are assigned to certain cases.

    2. All *zero* probabilities are substituted with a very small value
        $\varepsilon$, e.g. $\varepsilon = 0.00001$.

    3. Variables with the probability of 1, will now have the
        probability of $1-\varepsilon$.

- In the case CPTs are learned from data:

    1. In order to avoid *zeros* among the learned CPTs, methods like
        *learning with Dirichlet priors* can be utilized instead of
        *Maximum likelihood*.

Applying this solution will make the diagnostic accuracy of the BN becomes less sensitive to parameters inaccuracy.

***

**Structure:**
NA

***

**Constraints:**
NA

***

**Related patterns:**

- <span><a href="{{- site.baseurl -}}{%- link _patterns/oobn_polymorphism.md -%}">OOBN polymorphism</a></span>

***

**Design choice and model quality:**

- 2.F
- 3.F
- 4.U

***

**Resources:**

- Oniśko, A., & Druzdzel, M. J. (2013). Impact of precision of Bayesian network parameters on accuracy of medical diagnostic systems. Artificial intelligence in medicine, 57(3), 197-206.

- Marcot, B. G. (2017). Common quandaries and their practical solutions in Bayesian network modeling. Ecological Modelling, 358, 1-9.
