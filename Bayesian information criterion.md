---
title: Bayesian information criterion
tags:
    - statistics
---

The **Bayesian information criterion** (BIC) or **Schwarz information criterion** (SIC) is a criterion for model selection in a finite set of models. We prefer the model with the lowest BIC. Its general defenition is[^stat-learning]

$$ \text{BIC} = \log N\cdot d - 2\ \text{loglik} ,$$

where $N$ is the number of data points $d$ is the number of parameters estimated by the model and $\text{loglik}$ is the log of the maximized [[Likelihood function|likelihood function]].

[^stat-learning]: Hastie, T., Tibshirani, R., & Friedman, J. H. (2009). *The elements of statistical learning: data mining, inference, and prediction* (2nd ed). Springer.
