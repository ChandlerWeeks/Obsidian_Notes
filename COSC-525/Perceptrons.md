A perceptron takes several binary inputs, $x_1, x_2, ...$ and produces a single binary output. 

![[Pasted image 20260227094447.png]]

In the example, $x_1, x_2$, and $x_3$ are the binary inputs (0 or 1). The output is determined by weights, $w_1, w_2, ...$, which are real numbers expressing the importance of the input to the binary output. 

The output is determined by the weighted sum $\sum_j w_j x_j$, compared against a *threshold value*.

We can modify the weights and thresholds to get different models for decision making. These aren't a complete model of human decision making, but can weigh up to make decisions using evidence. 

Sigmoid neurons are similar to perceptrons, but modified so that a small change in weights and biases only cause a small change in output. They take x_1, x_2, ... between 0 and 1, like 0.638. Like perceptrons, they have weights to nodes, and each node has an overall bias b. The output can be $\sigma (w * x + b)$, where $\sigma$ is called the *sigmoid function* defined as $\sigma(z) = \frac{1}{1+e^-z}$. 