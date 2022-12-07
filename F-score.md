In statistical classification, the *F-score* is a measure of accuracy, based on
the [[Precision (classification)|precision]] and
[[Accuracy (classification)|accuracy]] of a classifier. It is defined by the
positive real factor $\beta$, as

$$
F_\beta = (1 + \beta^2) \cdot \frac{\text{precision} \cdot \text{recall}}{\text{(\beta^2 \cdot precision) + \text{recall}}.
$$

Typically, we consider the F1-score, which is the harmonic mean between the
[[Precision (classification)|precision]] and
[[Accuracy (classification)|accuracy]], namely

$$
F_1 = 2\frac{\text{precision}\cdot\text{recall}}{\text{precision} + \text{recall}}.
$$
