---
family: Mod
title: "Model assumptions statement"
icon_name: model_assumption_statement_ico.png
---

**Version:** 1.0.0

**Pattern language family:** Mod

**Modeling phase:** 1; 2

**Modeling step:** 1; 2; 3; 4

**Problem:**

In order to describe a complex system, a series of simplifying
assumptions need to be made by the modeler. In the case of OOBNs, these
assumptions will directly affect the relationships between the different
BNFs, the structure of each BNF, and the CPTs associated with each
variable. How can these effects be revealed and considered by the model
users?

***

**Solution:**

The relevant assumptions can be one of two cases:

1. The first case are assumptions related to the model
    conceptualization which mainly reflect the modeler's understanding
    of the system to be modeled; let them be called assumptions
    **Type-I**.

2. The second case include the assumptions made during translating the
    conceptual model into a computational model; let this type be called
    assumptions **Type-II**.

Any of the assumptions made during model development, whether they are
of **Type-I** or **Type-II**, should be explicitly stated as well as the
effects they will have on the BNFs structure, as well as any effects
they may have on the algorithms used for model inference.

Explicitly stating the model assumptions, particularly the ones that directly affect the model structure, contributes to clearly describing the thought process of the model developer and facilitates the modifying the model at later stages as well as testing these assumptions. For some domains, a set of assumptions will be repeated along different models and the model developer can benefit from the literature describing those common assumptions.

**Type-I** and **Type-II** assumptions are not to be confused with the statistical **Type I** and **Type II** errors (see [4] for more details about the statistical errors).

***

**Structure**
The solution proposed by this pattern have the following structure:

- In an OOBN **Type-I** will mainly affect the model structure on both
    BNFs level and variable level, consider the following examples:

- **Example 1:** Consider the same large network considered in the
    pattern *\"Large BN fragmentation\"*. Such network aims at modeling
    how energy policy affects SDG progress and resilience against
    disasters. As there is no agreement among experts on the
    relationship between sustainability (represented in this case by the
    SDG) and resilience, that relationship can take one of three
    forms; a) achieving the SDG will affect the resilience, b)
    resilience is needed in order to achieve the SDG, and c) there is no
    relationship between the two. According to these three forms, the
    model can have the three possible structures appearing in parts *a,
    b, and c* in **Fig.1**. As the structure will change
    based on the modeler's understanding, experience, or expert input,
    the assumption underlying the selected structure needs to explicitly
    stated.

<p align= "center">
<img src="./images/type1a_.png" style="width:80%">
</p>
<b>Fig.1</b> Structure of the network changing based on the model assumptions.

- **Example 2:** For the same model mentioned in example 1, when the
    modeler tries to instantiate the SDG BNF, he/she will be faced by a
    design choice about which variables to include in the concrete BNF
    and how these variables relate to each other. As there are different
    views in literature on how SDGs are interlinked together, this can
    result in different SDG BNF instantiations with different
    structures. For instance, **Fig.2** shows two structures
    based on two publications, (a) is driven from [1],
    and (b) is driven from [2]. As each BNF will yield
    different results when queried, the assumptions underlying each need
    to be explicitly stated

<p align= "center">
<img src="./images/bnf_assump_.png" style="width:70%">
</p>
<b>Fig.2</b> Two different views for the SDG BNF based on different understanding of the interlinkages between SDGs.

- **Example 3:** Clearly stating the model assumptions becomes very
    important in the cases where the model structure is inferred from
    data or when the model utilizes other systems' models that allow
    cyclic behavior such as system dynamics. The following figure shows
    part of the network developed in [3] where they
    attempted to explore the relationships between the targets
    underlying SDG 6 and the other targets included in the 2030 Agenda
    by learning a BN structure from the available data. The resulting
    structure, however, contained some undirected links, which indicates
    that the relationship between the variables linked by undirected
    links can possibly go in both directions. As this type of
    relationship is illegal in BNs, the modeler needs to decide a
    direction for the link. Such decision will be based on some
    assumptions that need to be explicitly stated.

<p align= "center">
<img src="./images/struct_learn_assump.png" style="width:70%">
</p>
<b>Fig.3</b> Undirected links resulting from structure learning algorithm in (a) need to be converted to directed links based on a set of assumption in (b).

- **Type-II** assumptions will mainly affect the algorithms and
    methods used for BNFs computations. For example, in the case of
    continues variable discretization, the chosen discretization method
    as well as the reasoning behind that choice needs to be clearly
    stated as this can have a considerable impact on the network
    performance and accuracy.

***

**Constraints**

***

**Related patterns:**

- OOBN polymorphism
- Large BN fragmentation
- BN augmented structure

***

**Design choice and model quality:**

- 1.R
- 4.U

***

**Resources:**

1. Zhang, Q., Prouty, C., Zimmerman, J. B., & Mihelcic, J. R. (2016). More than target 6.3: a systems approach to rethinking sustainable development goals in a resource-scarce world. Engineering, 2(4), 481-489.

2. Santika, W. G., Anisuzzaman, M., Bahri, P. A., Shafiullah, G. M., Rupf, G. V., & Urmee, T. (2019). From goals to joules: A quantitative approach of interlinkages between energy and the Sustainable Development Goals. Energy Research & Social Science, 50, 201-214.

3. Requejo-Castro, D., Giné-Garriga, R., & Pérez-Foguet, A. (2020). Data-driven Bayesian network modelling to explore the relationships between SDG 6 and the 2030 Agenda. Science of the total environment, 710, 136014.

4. Banerjee, A., Chitnis, U. B., Jadhav, S. L., Bhawalkar, J. S., & Chaudhury, S. (2009). Hypothesis testing, type I and type II errors. Industrial psychiatry journal, 18(2), 127.

5. Crout, N., Kokkonen, T., Jakeman, A. J., Norton, J. P., Newham, L. T. H., Anderson, R., ... & Whitfield, P. (2008). Chapter two good modelling practice. Developments in Integrated Environmental Assessment, 3, 15-31.
