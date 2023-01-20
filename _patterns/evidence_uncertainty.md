---
family: BN
title: "Evidence uncertainty"
icon_name: evidence_uncertainty_ico.png
---

**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:** 3; 4; 5

**Modeling step:** 7; 9

**Problem:**

How to handle cases when there is uncertainty associated with evidence
or when evidence does not represent a direct observation? Setting an
evidence for a node in the network will result in the belief of this
node will be updated so it is $1$ for the state associated with the
evidence and $0$ for all the other states, which implies certainty about
the entered evidence. What happen in the cases when we are uncertain
about evidence, e.g. if the evidence has a certainty of $80\%$, or if we
wish to enter evidence as a probability distribution over the possible
states for that node.

***

**Solution:**

In the cases where this problem occur, we use *\"virtual evidence\"*
which means to adopt a new distribution over the node in question. This
is achieved by creating a *\"virtual node\"* that carries the
distribution of the evidence and passes it to the real node where we
wish to add the uncertain evidence.

***

**Structure**
The solution proposed by this pattern have the following structure in a
BN:

- Assume that we wish to enter uncertain evidence for the node **B**
    as we are only $80\%$ sure that it is **True**.

- We use virtual evidence by creating a virtual node $v$ whose CPT is
    the distribution over the states, i.e. **\[0.8 True, 0.2 False\]**,
    and it passes the message with the new evidence distribution to
    **B**.

<p align= "center">
<img src="./images/virvar.png" style="width:70%">
</p>
<b>Fig.1</b> Assigning virtual evidence to the node <b>B</b> that incorporates the uncertainty about the evidence.

***

**Constraints**

This solution works under the following conditions:

- The virtual evidence need to be a complete distribution, i.e.
    individual probabilities need to add up to $1$.

***

**Related patterns:**

- <span><a href="{{- site.baseurl -}}{%- link _patterns/making_things_happen.md -%}">Making things happen</a></span>

***

**Design choice and model quality:**

- 1.R
- 4.R

***

**Resources:**

- Korb, K. B., & Nicholson, A. E. (2010). Bayesian artificial intelligence. CRC press.
