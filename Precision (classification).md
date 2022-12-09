In statistical classification, the *precision* of a classifier over a class is
the ratio between the number of times that class got predicted correctly and the
number of times that class got predicted. Namely,

$$ \text{precision}(x) = \frac{N_\text{correctly predicted}(x)}{N_\text{predicted}(x)}, $$

where $x$ is the class being predicted.

Typically, this appears in binary classification, where we want to compare the
number of true positives against the number of true *and* false positives.

See also [[Recall (classification)]], [[Accuracy (classification)]] and
[[F-score]].
