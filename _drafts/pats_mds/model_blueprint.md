--- 
family: Mod
title: "Model Blueprint"
icon_name: model_blueprint_ico.png 
--- 
 
**Version:** 1.0.0

**Pattern language family:** Mod

**Modeling phase:** 1; 2; 4

**Modeling step:** 1; 2; 3; 10

**Problem:**

Modelers usually neglect documenting the underlying architecture and the main features of their models which negatively affect the models reusability, transparency, as well as decreasing the confidence in it.
***

**Solution:**

Clear documentation that describe the model and the choices made during the model design as well as a justification for these design choices needs to be provided as part of the model's technical documentation. Although there is no standard for model data documentation, a very important requirement for such documentation is that they written in a parsimonious manner, which means that they are as simple as possible yet they capture the key components and aspects of the model. The knowledge documented in the model blueprint is different than the scientific literature that describe how the model works and the algorithms used in it. The model documentation needs to be regularly updated, and in order to do that it is recommended that the documentation is kept separate from the published literature related to the model. To help modelers maintain an updated model documentation, the solution proposed in this pattern separate the data to be documented into three main types:

1. Data related to the model conceptualization.

2. Data related to the model development.

3. Data related to the model use.

It is expected that the contents of the model use section is the type that will be subjected to regular updates as it includes information about the model's runtime comments, performance, and scenarios. The specific data that should be reported for each of the above mentioned three types are shown in the structure section below.
***

**Structure**
The structure for this solution is as follows:

<p align= "center">
<img src="./images/Model_blueprint.png" style="width:70%">
</p>
<b>Fig.1</b> The contents of the model documentation and the phases they map to .

***

**Constraints**

The constraints for this solution are as follows:

***

**Related patterns:**

- BNFs linking
- Model assumptions statement
- Large BN fragmentation
- OOBN polymorphism
- Complexity control
- Generalized Canonical
- Making things happen

***

**Design choice and model quality:**

- 1.U
- 1.F
- 2.R
- 3.F

***

**Resources:**

- Scheller, R. M., Sturtevant, B. R., Gustafson, E. J., Ward, B. C., & Mladenoff, D. J. (2010). Increasing the reliability of ecological models using modern software engineering techniques. Frontiers in Ecology and the Environment, 8(5), 253-260.

- Badham, J., Elsawah, S., Guillaume, J. H., Hamilton, S. H., Hunt, R. J., Jakeman, A. J., ... & Bammer, G. (2019). Effective modeling for Integrated Water Resource Management: A guide to contextual practices by phases and steps and future opportunities. Environmental Modelling & Software, 116, 40-56

- Hamilton, S. H., Fu, B., Guillaume, J. H., Badham, J., Elsawah, S., Gober, P., ... & Zare, F. (2019). A framework for characterising and evaluating the effectiveness of environmental modelling. Environmental modelling & software, 118, 83-98.
