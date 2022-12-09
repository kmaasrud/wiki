In statistical classification, the *F-score* is a measure of accuracy, based on
the [[Precision (classification)|precision]] and
[[Accuracy (classification)|accuracy]] of a classifier. It is defined by the
positive real factor $\beta$, as

$$
F_\beta(x) = (1 + \beta^2) \cdot \frac{\text{precision}(x) \cdot \text{recall}(x)}{\left(\beta^2 \cdot \text{precision}(x)\right) + \text{recall}(x)},
$$

where $x$ is the class being classified.

Typically, we consider the F1-score, which is the harmonic mean between the
[[Precision (classification)|precision]] and
[[Accuracy (classification)|accuracy]], namely

$$
F_1(x) = 2\frac{\text{precision}(x)\cdot\text{recall}(x)}{\text{precision}(x) + \text{recall}(x)}.
$$
