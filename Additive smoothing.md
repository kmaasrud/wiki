Additive smoothing, Lidstone-smoothing or Laplace-smoothing refers to a way of
smoothing categorical data. Given a set of categories $\{c\_1, c\_2, \dots,
c\_N\}$, we consider the smoothed probability as

$$ \hat P (c\_i) = \frac{N\_{c\_i} + k}{N + kC}, $$

where $C$ is the number of categories, $N$ is the size of the dataset and
$N\_{c\_i}$ is the count of category $c\_i$ in the dataset. $k > 0$ is here a
smoothing parameter.

Setting $k = 0$ does no smoothing and gives the regular empirical probability,
while $k = 1$ is often called *Laplace-smoothing*. Typically, a value between
$0$ and $1$ is chosen.

The method is often applied as a way of compensating for non-existing data in a
classification problem, e.g. when using a [[Naïve Bayes classifier]].
