In statistical classification, the *recall* of a classification value is the
ratio between the number of times that value got predicted correctly and the
number of times that value appears in the training dataset.

$$ \text{recall}_x = \frac{N_\text{correctly predicted}(x)}{N(x)}, $$

where $x$ is the value being predicted.

Typically, this appears in binary classification, where we want to compare the
number of true positives against the number of positives. However, the precision
applies to any classification.

See also [[Precision (classification)]], [[Accuracy (classification)]] and
[[F1-score]].
