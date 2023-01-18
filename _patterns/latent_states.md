--- 
family: BN
title: "Latent states"
icon_name: latent_states_ico.png 
--- 
 
**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:** 2; 3

**Modeling step:** 6; 7

**Problem:**

Introducing new variables to the network, as a result of applying parent
divorcing, or if some variables' data have never been observed means
that these variables will cut the influence path between the input nodes
and the output nodes. Particularly in the case when the new nodes are
introduced through parent divorcing, these new nodes don't necessarily
represent a real variable that we can acquire data for, hence determine
its possible states.

***

**Solution:**

Apply statistical methods that can condense a group of observed
variables into a smaller group of latent variables. One of the methods
that can be used for this purpose is *Factor analysis (FA)*, which can
describe the relation between a set of observed variables in terms of a
smaller number of unobserved variables. In the case of latent variables
in a BN, each of them will be represented as an index that reflects the
performance of its parent variables. The following steps can be followed
to apply *FA* in a BN context:

- Determine the set of unparameterized parents for each latent
    variable.

- In order to proceed with FA, we need to choose the number of factors
    to keep, so a suitable solution is to choose *number of factors =
    number of parents -1*.

- Perform factorial axes rotation using a rotation algorithm, e.g.
    *Varimax rotation*.

- Factor loadings are then used to give weights to parameters. The
    weights represent the proportion of total unit variance of the
    parameter that is explained by the factor.

- Associate weights to parameters based on the ratio between the
    variance explained by the parameter to the total explained variable.

- Finally, the weights are used to aggregate the parents' data to
    assign a new value for the latent variable.

Applying this solution will result in new parameters will be acquired for the latent variables added to the network so they can be discretized and used for inference.

***

**Structure**

***

**Constraints**

This solution works under the following conditions:

- This solution can be applied if the parents of the latent variable
    are continues.

- The resulting parameters for the latent variable will be continues
    and will need to be discretized.

***

**Related patterns:**

- Complexity control

***

**Design choice and model quality:**

- 2.R
- 4.U

***

**Resources:**

- Holmes, D. E. (Ed.). (2008). Innovations in Bayesian networks: theory and applications (Vol. 156). Springer.

- Marcot, B. G. (2017). Common quandaries and their practical solutions in Bayesian network modeling. Ecological Modelling, 358, 1-9.

- Yong, A. G., & Pearce, S. (2013). A beginner’s guide to factor analysis: Focusing on exploratory factor analysis. Tutorials in quantitative methods for psychology, 9(2), 79-94.

- Tripathi, M., & Singal, S. K. (2019). Allocation of weights using factor analysis for development of a novel water quality index. Ecotoxicology and environmental safety, 183, 109510.

- Nardo, M., Saisana, M., Saltelli, A., Tarantola, S., Hoffman, A. and Giovannini, E. (2006), Handbook on constructing composite indicators:
Methodology and user guide OECD, Statistics Working Paper 158.
