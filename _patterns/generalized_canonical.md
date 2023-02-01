---
family: BN
title: "Generalized Canonical"
icon_name: generalized_canonical_ico.png
---

**Version:** 1.0.0

**Pattern language family:** BN

**Modeling phase:**

    2. The conceptualization phase of a system of interest
    3. The technical implementation
    4. QA/QC

**Modeling step:**

    5. Choice of how model structure and parameter values to be determined
    7. Identification of model structure and parameters' values
    9. Quantification of uncertainty

**Problem:**
Increased complexity of a node (increased number of parameters) due to being the child of several nodes. This happens when a variable has several possible causes. In this case the number of parameters for the node representing a variable $y$ that has $N$ parents:

$$T_y = S_{y} \cdot \prod_{i=1}^{N} S_{x_i}$$

Where:

$T_y:$ number of parameters to define for the node representing $y$

$S_y:$ The number of states for the variable $y$

$S_{x_i}:$ The number of states for the $ith$ parent $x_i$ of the variable $y$

***

**Solution:**
The solution for this problem is to do the following:

Describe the variable $y$ using a *NoisyOR* function with the parameters assigned to each parent $x_i$ representing the probability that this parent alone will cause the respective state of $y$. Then for each state of $y$ define a leak factor $l$ representing the probability that a latent variable (other than the parents defined in the model) is causing this respective state of $y$.

Applying this solution will reduce the BN complexity as the number of parameters for the node representing the variable $y$ will be reduced to:

$$T_y = S_y \cdot \Sigma_{i=1}^{N} {S_{x_i}} + S_y$$

***

**Structure:**
The structure for this solution is as follows:

<p align= "center">
<img src="./images/NOR.png" style="width:70%">
</p>
<b>Fig.1</b> The model structure when node $y$ is defined as a *NoisyOR* node.

***

**Constraints:**

The constraints for this solution are as follows:

- Each of parent variables should has a probability $p_i$ of being sufficient to produce the effect in the absence of all other parents.
- The parent variables are independent.

***

**Related patterns:**
NA

***

**Design choice and model quality:**

- 2.F

***

**Resources:**

- Henrion, M. (2013). Practical issues in constructing a Bayes' belief network. arXiv preprint arXiv:1304.2725.
- Dıez, F. J., & Druzdzel, M. J. (2006). Canonical probabilistic models for knowledge engineering. UNED, Madrid, Spain, Technical Report CISIAD-06-01.
- Hossain, N. U. I., Jaradat, R., Hosseini, S., Marufuzzaman, M., & Buchanan, R. K. (2019). A framework for modeling and assessing system resilience using a Bayesian network: A case study of an interdependent electrical infrastructure system. International Journal of Critical Infrastructure Protection, 25, 62-83.
- Magrini, A., Luciani, D., & Stefanini, F. M. (2016). A Generalization of the Noisy-MAX Parameterization for Biomedical Applications. DISIA Working Paper 2016/06, University of Florence, Italy.
