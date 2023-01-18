--- 
family: BN
title: "Cross validation"
icon_name: cross_validation_ico.png 
--- 
 
**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:** 4

**Modeling step:** 8; 10

**Problem:**

After the completion of model building, i.e. determining the network
structure and the CPTs of the variables included in the network, the BN
needs to be validated to ensure that the model is performing as intended
and that there is no semantic or syntactic issues with it. Part of
delivering the BN is to report its accuracy and to show that it exhibits
plausible behavior.

***

**Solution:**

In the cases where data is used to determine the model parameters, i.e.
the CPTs are learned from data, cross-validation can be used to test the
network performance and its accuracy. *K-fold* cross validation can be
used where data is broken into *k* equal size parts, then the BN is
trained, parameters learned in this case, using *k-1* parts of the data,
then tested using the last remaining part. This process is repeated for
*k* times with different random *k* selected for testing each run.

Applying this solution allow the accuracy of the network to be reported as the BN's error rate, e.g $ <7\%$

***

**Structure**

***

**Constraints**

This solution works under the following conditions:

- There is available data for the all the variables to use for testing
    the network performance.

***

**Related patterns:**

- OOBN polymorphism

***

**Design choice and model quality:**

- 4.F
- 1.R
- 4.R

***

**Resources:**

- Marcot, B. G. (2012). Metrics for evaluating performance and uncertainty of Bayesian network models. Ecological modelling, 230, 50-62.

- Boyce, M. S., Vernier, P. R., Nielsen, S. E., & Schmiegelow, F. K. (2002). Evaluating resource selection functions. Ecological modelling, 157(2-3), 281-300.

- Guillaume, J. H., El Sawah, S., Jakeman, A., & Kummu, M. (2015). Communicating uncertainty: design patterns for framing model results in scientific publications.
