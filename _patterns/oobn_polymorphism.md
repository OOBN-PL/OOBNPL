---
family: OOP
title: "OOBN polymorphism"
icon_name: oobn_polymorphism_ico.png
---

**Version:** 1.0.0

**Pattern language family:** OOP

**Modeling phase:**

    2. The conceptualization phase of a system of interest

**Modeling step:**

    4. Selection of model features and family
    5. Choice of how model structure and parameter values are to be determined
    6. Choice of estimation performance criteria and technique

**Problem:**

During the development of an OOBN model, how to change the
implementation method of a certain task based on changes in the context,
requirements, or model limitations?

***

**Solution:**

This problem can be solved using the OOP concept of polymorphism, which
refers to the ability of a certain function to have different
implementations based on changes in the context and requirements. This
can be achieved by creating a component that defines the basic behavior
of the function or the basic method to perform the considered task. Then
we define a decorator that wraps the different implementations of the
functions or the different methods that can be used to perform the
considered task. Based on the context, the main component can utilize
the different implementations or methods defined under the decorator.

Applying this pattern enables the modeler to utilize the prolific
algorithms and methods available to perform OOBN modeling tasks.
Additionally, it enables the OOBN to be adaptable to different contexts
which increases its reusability.

***

**Structure:**
The solution proposed by this pattern have the following structure:

- Consider the task of discretizing a continues variable in one of the
    Bayesian network fragments (BNF). There are actually different
    methods that can be used for discretization, each of which can be
    suitable for a certain context and can lead to the BNF providing
    different results. These methods belong to three main categories,
    which are: Manual, unsupervised, and supervised.

- As the below figure shows, we define a basic discretization
    component, then creates a \"Discretization-decorator\" that contains
    the different discretization families and the algorithms belong to
    each family.

<p align= "center">
<img src="./images/decorator.png" style="width:70%">
</p>
<b>Fig.1</b> Class diagram for the application of the decorator pattern.

***

**Constraints:**
NA

***

**Related patterns:**
NA

***

**Design choice and model quality:**

- 1.U
- 1.R

***

**Resources:**

- Issariyakul, T., & Hossain, E. (2012). A Review of the Polymorphism Concept in OOP. Introduction to Network Simulator NS2, 485-497.

- Samiullah, M., Hoang, T. X., Albrecht, D., Nicholson, A., & Korb, K. (2017, November). Ioobn: A Bayesian network modelling tool using object oriented Bayesian networks with inheritance. In 2017 IEEE 29th International Conference on Tools with Artificial Intelligence (ICTAI) (pp. 1218-1225). IEEE.

- Aly, E., Elsawah, S., & Ryan, M. J. (2022). Aligning the achievement of SDGs with long-term sustainability and resilience: An OOBN modelling approach. Environmental Modelling & Software, 150, 105360.
