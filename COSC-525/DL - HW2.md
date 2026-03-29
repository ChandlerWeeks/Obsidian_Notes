Given that 

$$
J_p(a) = \sum_{i \epsilon ms}(-a^Ty)t
$$
We find the derivative of $J_p(a)$ with respect to a. 

$$
\nabla J_p(a) = \frac{\partial}{\partial a}\sum_{i \epsilon ms}(-a^Ty_i)t_i = \sum_{i \epsilon ms}(-y_it_i)
$$
Applying gradient descent we can determine that (note that c cancels the negative)

$$
a^{k+1} = a^k + \sum_{i \epsilon ms}(y_it_i)
$$

Subbing back in weights and biases, we get

$$
w^{k+1} = w^k + \sum_{i \epsilon ms}(y_it_i)
$$
$$
-w_0^{k+1} = -w_0^k + \sum_{i \epsilon ms}(t_i)
$$

Knowing that T - (-T) = 2, and that t is always the inverse of T for ms, we can derive that T=1/2 (T-z). We can drop the 1/2, since the direction is what matters, not the value. Therefore

$$
w^{k+1} = w^k + \sum_{ms}x(T-Z)
$$
$$
-w_0^{k+1} = -w_0^k + \sum_{ms}(T-Z)
$$
