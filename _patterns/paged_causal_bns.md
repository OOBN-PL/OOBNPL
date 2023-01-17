--- 
layout: page
title: "BNs Causality"
--- 
 
**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:**

**Problem:**

- What are causal BNs?
- why are they important?
- How to ensure that the developed model bears a causal representation of the system?  

***

**Solution:**

Networks that represent all the dependencies in the system are **faithful** to the system. and a network that represents both the dependencies and independencies in the system is called a **perfect map** of the system.

A causal network is a network where the arcs between the variables identify direct causal relationships between such variables.

One of the main features of causal networks is that they are the simplest Bayesian networks capable of representing the probabilistic relationships in the variables included in the system.

Establishing a cause-effect relationship is conditional on the "universe" and/ or on the stakeholders' conjecture of the system.

In order to deal with causal BNs, we need to distinguish between *observations* and *Interventions*. Observations refer to passively measure the state of a set of variables in the domain of interest. Interventions, however, refer to deliberately changing the states of a set of variables from outside the system. Observations, may also be called evidence, are used for probabilistic updating of the network, and therefore are sufficient for prediction, but in order to understand and anticipate the impact of interventions on the system, a causal BN is needed.

Causal graphs satisfies the *causal Markov assumption*: given the values of a variable's immediate causes, this variable is independent of its earlier causes.

Learning a causal BN from data is a challenging task for the following reasons:

1. The existence of *equivalence classes*, where an *Equivalent class* is a set of networks that have the same skeleton, i.e. the configuration of undirected edges. An equivalent class can also be represented as a *partially  directed acyclic graph (PDAG)*, which is a directed acyclic graph with some undirected edges.

2. The possibility of the existence of hidden variables that are not included in the network, however it directly affects other variables in the network.

In order to account for the reason **1**, an intervention can be utilized. Consider the example shown in **Fig.1**. The two DAGs appearing in **Fig.1.1** both have the same likelihood scores, hence they are in the same equivalence class. A structure learning algorithm will either connect them with an undirected edge or will randomly assign a direction for the link between them, which is non-indicative of the causal relationship between them. In order to discover the causal relationship between the two variables an intervention is used. The intervention is applied to each of the variables while the other is monitored for change. If the intervention on $Y$ caused a change in $X$, as shown in **Fig.1.2**, then we can infer that $Y$ is a cause of $X$. If the intervention on $X$ caused no change in $Y$, as shown in **Fig.1.3**, then we can infer that the link directed from $X$ to $Y$ is not causal.

<figure>
<img src="./images/causals.png" style="width:100%">

<figcaption align="center"><b>Fig.1:</b> The two BNs in <b>Fig.1.1</b> belong to the same equivalence class (appearing in grey at the top). <b>Fig.1.2</b> shows that an intervention on <I>Y</I> will induce a change in <I>X</I>, <b>Fig.1.3</b> shows that an intervention on <I>X</I> will have no impact on <I>Y</I>, hence <I>Y</I> is a cause of <I>X</I>.</figcaption>
</figure>

Accounting for reason **2** is more challenging and require that we have an input from a stakeholder or an expert.

Additionally, not all structure learning algorithms are built as causal discovery algorithms, due to the relatively high computational cost of the latter, therefore the user needs to ensure that the underlying structure learning algorithm is capable of learning causal networks. Causal discovery algorithms include *IC, PC, K2, BDe/BGe, GES, and CaMML*.

***

**Structure**
The structure for this solution is as follows:

***

**Constraints**

The constraints for this solution are as follows:

***

**Related patterns:**

- BN augmented structure
- Making things happen

***

**Design choice and model quality:**

- 1.R
- 1.U
- 2.U

***

**Resources:**

- Alameddine, I., Cha, Y., & Reckhow, K. H. (2011). [An evaluation of automated structure learning with Bayesian networks: an application to estuarine chlorophyll dynamics](https://www.sciencedirect.com/science/article/pii/S1364815210002355). Environmental Modelling & Software, 26(2), 163-172.

- Korb, K. B., & Nicholson, A. E. (2008). The causal interpretation of Bayesian networks. In Innovations in Bayesian Networks (pp. 83-116). Springer, Berlin, Heidelberg.

- Husmeier, D. (2005). [Introduction to learning Bayesian networks from data](https://www.bioss.ac.uk/people/dirk/papers/sbb_bnets.pdf). In Probabilistic modeling in bioinformatics and medical informatics (pp. 17-57). Springer, London.
