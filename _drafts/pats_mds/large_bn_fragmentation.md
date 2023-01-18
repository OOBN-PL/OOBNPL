--- 
family: OOP
title: "Large BN fragmentation"
--- 
 
**Version:** 1.0.0

**Pattern language family:** OOP

**Modeling phase:** 1; 2

**Modeling step:** 2; 3

**Problem:**
How to determine the composing network fragments of a BN representing a
complex system so the fragments are coherent with the OOP concepts of
abstraction and encapsulation.?

***

**Solution:**

The system represented by the large BN needs to be decomposed into functional sub-systems each of which can then be represented by a Bayesian network fragment (BNF). Each BNF represents an abstract sub-component of the large network, which is then instantiated so it becomes a small BN that is computationally sound and can be quarried. Determining the BNFs is achieved through variability and commonality analysis. Commonality analysis focuses on the system structure that is unlikely to change and gives the design its longevity, while variability analysis gives the design its fitness for purpose and represents the internal structure and probability distribution of each BNF.

Applying this pattern enables the modeler to decompose large networks into smaller BNs called BNF. Each abstract BNF encapsulates a common concept, and the instantiation of the BNFs defines implementation variations. This approach enables modelers to reinforce the component-based structure of the OOBN while conforming with the encapsulation and abstraction OOP concepts.

***

**Structure**

The solution proposed by this pattern have the following structure:

- Consider a large network that aims at modeling how energy policy
    affects SDG progress and resilience against disasters.

- First, we do functional decomposition for the large network to
    determine what are the structure that is unlikely to change. Here,
    the complex system is composed of three main subsystems: The energy
    policy, the SDG, and the resilience component. Each of the
    components can has multiple representations and resolutions.
    However, regardless these representations details, the three main
    components define the big picture of the problem under study. We
    first start by defining an abstract class (abstract BNF) for each
    component and then define the structure that links these classes
    together. As shown in **Fig.1**, the impacts of the energy policy
    on the SDG and resilience are represented by the solid arrows, while
    the dashed arrow represent an optional consideration of the impacts
    of SDG on resilience (this arrow can be reversed if we chose to
    consider the resilience impacts on SDG).

- The next step is to instantiate each of the abstract BNFs by
    creating a concrete BNF for each component. This entails defining
    the set of nodes $N$ representing the variables we choose to
    consider for the subsystems, the set of edges $E$ representing the
    relationships between the considered variables, and the CPT
    associated with each variable. The CPTs and structure of the
    concrete BNF can be learned from data. This step is related to
    variability analysis as different variations of each abstract BNF
    can be created and plugged into the OOBN to study different
    scenarios.

<p align= "center">
<img src="./images/Class_diagram2.png" style="width:50%">
</p>
<b>Fig.1</b> The abstract BNFs representing the main model components and their relationships (result of the functional decomposition).

- **Fig.2** shows the class diagram for each BNF instantiation, i.e.
    the creation of concrete BNFs. The concrete BNF inherits the concept
    or subsystem it should represent from the abstract BNF. The methods
    needed to create a BN, e.g. continues variable discretization and
    CPT learning, are defined in an abstract BN class, then the concrete
    BNF class can inherit such methods from the abstract BN class. This
    approach capitalizes on the concept of polymorphism, e.g. pattern
    *\"OOBN polymorphism\"*, as multiple implementation of the methods
    can be made available to the abstract BN class, and the concrete BNF
    class can make use of the most suitable implementation based on the
    model requirements.

<p align= "center">
<img src="./images/BNF_abs_conc.png" style="width:50%">
</p>
<b>Fig.2</b> The OOBN class inheritance diagram.

***

**Constraints**

***

**Related patterns:**

- OOBN polymorphism

***

**Design choice and model quality:**

- 1.U
- 2.R
- 2.F

***

**Resources:**

- Koller, D. and Pfeffer, A. (1997), Object-oriented bayesian networks, in ‘Proceedings of the Thirteenth conference on Uncertainty in artificial
intelligence’, pp. 302–313.

- Laskey, K. B., & Mahoney, S. M. (1997). Network fragments: Representing knowledge for constructing probabilistic models. arXiv preprint arXiv:1302.1557.

- Mahoney, S. M., & Laskey, K. B. (1996). Network engineering for complex belief networks. arXiv preprint arXiv:1302.3591.

- Neil, M., Fenton, N., & Nielson, L. (2000). Building large-scale Bayesian networks. The Knowledge Engineering Review, 15(3), 257-284.

- Shalloway, A., & Trott, J. R. (2005). Design patterns explained: A new perspective on object-oriented design, 2/E. Pearson Education India.

- Torti, L., Wuillemin, P. H., & Gonzales, C. (2010, September). Reinforcing the object-oriented aspect of probabilistic relational models. In PGM 2010-The Fifth European Workshop on Probabilistic Graphical Models (pp. 273-280).
