--- 
family: BN
title: "BN augmented structure"
--- 
 
**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:** 2

**Modeling step:** 5

**Problem:**

Determining a BN structure can be a daunting task that is usually performed either through eliciting expert knowledge or by utilizing a structure learning algorithm along with the existing data about the variables included in the network. While the latter approach can be beneficial in many cases, it is not free of challenges. This pattern aims at solving the following problems related to learning a BN structure from data:

- How to handle the situations when learning the BN structure from data produces multiple equivalent BNs, i.e. Markov equivalent structures?

- How to incorporate experts knowledge and stakeholders perception about the system structure along with the existing data to produce a more accurate BN structure?

- How to convert cyclic structures, e.g. feedbak loops, into acyclic structures so they can be incorporated in BNs?

***

**Solution:**

Structure learning algorithms are not perfect, and a set of observations related to a system can be explained with a potentially infinite set of theories. Relying solely on Data to inform a BN structure can produce equivalent networks, i.e. networks that contain the same variables with different structures, however, they have the same joint distribution. Consider the example shown in **Fig.1**; Suppose that we wish to represent the relationship between three variables *SDGs (D)* (the achievement of SDGs if that can be measured through a single index), *Sustainability (S)*, and *Resilience (R)*. Learning the structure of such model from data (in a certain national context) can produce three equivalent BNs that are different in structure, however they share the same joint probability distribution. Expanding the joint probability of the three BN structures shown in **Fig.1**, we find that they have the same joint distribution: $$P(D,S,R) = P(R \vert D) P(S \vert D) P(D)$$  

<figure>
<img src="./images/eq_nets.png" style="width:100%">

<figcaption align="center"><b>Fig.1</b> Three networks representing different relationships between the variables: <i>SDGS (D)</i>, <i>Sustainability (S)</i>, and <i>Resilience (R)</i>.</figcaption>
</figure>

<!--- #commenting out the following block
<p align= "center">
<img src="./images/eq_nets.png" style="width:100%">
</p>
<p align= "center">
<b>Fig.1</b> Three networks representing different relationships between the variables: <i>SDGS (D)</i>, <i>Sustainability (S)</i>, and <i>Resilience (R)</i>.
</p>
--->

The solution for this problem depends on the *Likelihood equivalence* assumption, which states that data should not help in discriminating network structures that can be represented by the same joint distribution.

The knowledge / stakeholder perception is encoded in the model as a **prior network** that will be updated based on new structures obtained from the available data.

The creation and updating of a prior network is done through the following steps:

1. Obtain a prior network structure from stakeholder / knowledge base, let this be called $S_{sk}$ .

2. Use the available data to create $n$ different network structures each of which is created by applying the bootstrap technique as follows:

    a. First create $m$ networks by resampling the data $m$ times with replacement.

    b. Then choose the network with the structure that has the highest frequency.

    c. Apply steps *a* and *b* $n$ times to get the $n$ network options.

3. Obtain an updated network structure $S_{U}$ by comparing each of the $n$ learned network structures with the prior network structure $S_{sk}$ and asking the stakeholders to vote on which network is the most likely, i.e. checking if the learned structures will cause the stakeholders to update their beliefs.

***

**Structure**
The structure for this solution is as follows:

<figure>
<img src="./images/BN_aug.png" style="width:100%">

<figcaption align="center"><b>Fig.1</b> Steps of augmenting structure learning with stakeholder perception / knowledge base.</figcaption>
</figure>

***

**Constraints**

The constraints for this solution are as follows:

- The data used to learn the network structure is representative of the original distribution of the variables.

***

**Related patterns:**

- BNs causality
- OOBN polymorphism

***

**Design choice and model quality:**

- 1.R
- 1.F
- 2.U
- 2.F

***

**Resources:**

- Heckerman, D., Geiger, D., & Chickering, D. M. (1995). [Learning Bayesian networks: The combination of knowledge and statistical data](https://link.springer.com/article/10.1007/BF00994016). Machine learning, 20(3), 197-243.

- Alameddine, I., Cha, Y., & Reckhow, K. H. (2011). [An evaluation of automated structure learning with Bayesian networks: an application to estuarine chlorophyll dynamics](https://www.sciencedirect.com/science/article/pii/S1364815210002355). Environmental Modelling & Software, 26(2), 163-172.

- Requejo-Castro, D., Giné-Garriga, R., & Pérez-Foguet, A. (2020). [Data-driven Bayesian network modelling to explore the relationships between SDG 6 and the 2030 Agenda](https://www.sciencedirect.com/science/article/pii/S0048969719360103). Science of the total environment, 710, 136014.
