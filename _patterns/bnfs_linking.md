--- 
family: OOP
title: "BNFs linking"
icon_name: bnfs_linking_ico.png 
--- 
 
**Version:** 1.0.0

**Pattern language family:** OOP

**Modeling phase:** 2

**Modeling step:** 3; 5

**Problem:**

How to achieve loose coupling between OOBN fragments and maintain high abstraction of each BNF?.

***

**Solution:**

The concept of *encapsulation* in OOP can be thought about as hiding
some entities data, implementation, design details, and instantiation
rules. This can increase the model components' reusability as well as
increasing the model's composability. Encapsulation in an OOBN entails
that each of the BNFs included in the model can be instantiated using a
different method, i.e. some using CPT and structure learning while
others utilize expert knowledge, or that a certain BNF class can have
different instantiations and each of the resulting BNFs can be plugged
into the model without having to do major changes to the other BNFs.

Two OOP design patterns can be combined together in order to achieve
encapsulation and loose coupling in OOBNs, namely: the Mediator pattern
and the Proxy pattern. Mediator is a pattern that is used to reduce the
dependencies between objects by restricting the communications between
them and only allows the communication to happen through a mediator,
thereby help in achieving loose coupling between objects. Proxy on the
other hand, is a pattern that control access to objects by providing a
substitute or a placeholder for them that only contains part of their
functionality. The proxy object provides an interface for an object that
is expensive to operate.

In an OOBN context, a mediator object is created for each couple of
interacting BNFs. That mediator object takes the origin-destination
mapping between the two BNFs as an input, this is an artifact that
defines which nodes in the first BNF are connected to which nodes in the
second BNF. For each of the origin and destination BNFs, a proxy BNF is
created which only contains the origin output nodes, and the destination
input nodes. The mediator object uses the proxy nodes to read the origin
output nodes and connect them to the destination input nodes and perform
any necessary forward or backward CPT updating. The simplified proxy
BNFs are far less complex than the original BNFs and exposes only the
output and input nodes which reinforces the BNFs encapsulation.

Applying this pattern enables the modeler to decompose large networks
into smaller BNs called BNF. Each abstract BNF encapsulates a common
concept, and the instantiation of the BNFs defines implementation
variations. This approach enables modelers to reinforce the
component-based structure of the OOBN while conforming with the
encapsulation and abstraction OOP concepts.

***

**Structure**
The solution proposed by this pattern have the following structure:

- Consider an OOBN composed of three BNFs; A, B, and C.

<p align= "center">
<img src="./images/3bnfs.png" style="width:20%">
</p>
<b>Fig.1</b> Three abstract BNFs representing the components and structure of the system to be modeled.

- First, we determine the input-output mapping that defines how each
    pair of BNFs are connected together. In this case we should have two
    mappings, one that connects BNFs A and B, and another connecting
    BNFs A and C.

- a mediator object is added to the OOBN for each link between each
    pair of BNFs, i.e. we should have two mediators; AB mediator and AC
    mediator.

- Additionally, a proxy BNF is created for each BNF in the OOBN. The
    proxy BNF is a simplified BN that contains only the relevant input
    or output nodes based on the OOBN structure. Here, BNF A proxy will
    contain the output nodes from BNF A. BNFs B and C proxies will
    contain the input nodes in B and C respectively as shown in the
    following figure.

<p align= "center">
<img src="./images/med_proxy.png" style="width:50%">
</p>
<b>Fig.2</b> Combining the Proxy and Mediator patterns to connect the BNFs.

- The Proxy BNF is created by copying the output/input nodes and their
    respective CPTs. If the prior CPT for the output/input nodes is
    available, this will be sufficient to perform the inference between
    the proxy BNFs, otherwise the proxy BNFs can make use of the Markov
    blanket for each output/input node to do the inference.

<p align= "center">
<img src="./images/proxyO1.png" style="width:60%">
</p>
<b>Fig.3</b> Implementation of the proxy pattern.

- The class diagram for the Mediator object and the proxy BNFs and
    their interactions appears in the figure below. The mediator uses
    the OD-matrix to connect each pair of BNFs and has the ability to
    get and pass the nodes CPT for inference.

- The BNF proxy stores the output/input nodes as well as their
    respective CPTs. It can update the CPTs for forward and backward
    inference. The proxy also contains methods to extract a node's
    Markov blanket, relevant sub-graph, and assign virtual evidence to a
    node.

<p align= "center">
<img src="./images/m_proxy.png" style="width:60%">
</p>
<b>Fig.4</b> Class diagram of the proposed solution.

***

**Constraints**

***

**Related patterns:**

- Evidence uncertainty
- OOBN polymorphism
- Large BN fragmentation

***

**Design choice and model quality:**

- 3.R
- 3.F

***

**Resources:**

- Shalloway, A., & Trott, J. R. (2005). Design patterns explained: A new perspective on object-oriented design, 2/E. Pearson Education India.

- Samiullah, M., Hoang, T. X., Albrecht, D., Nicholson, A., & Korb, K. (2017, November). Ioobn: A Bayesian network modelling tool using object oriented Bayesian networks with inheritance. In 2017 IEEE 29th International Conference on Tools with Artificial Intelligence (ICTAI) (pp. 1218-1225). IEEE.

- Getoor, L., Friedman, N., Koller, D., & Taskar, B. (2002). Learning probabilistic models of link structure. Journal of Machine Learning Research, 3(Dec), 679-707.

- Spalazzese, R., & Inverardi, P. (2010, August). Mediating connector patterns for components interoperability. In European Conference on Software Architecture (pp. 335-343). Springer, Berlin, Heidelberg.

- Wuillemin, P. H., & Torti, L. (2012). Structured probabilistic inference. International Journal of Approximate Reasoning, 53(7), 946-968.

- Bayer, F. M., Moffa, G., Beerenwinkel, N., & Kuipers, J. (2021). Marginalization in Bayesian Networks: Integrating Exact and Approximate Inference. arXiv preprint arXiv:2112.09217.
