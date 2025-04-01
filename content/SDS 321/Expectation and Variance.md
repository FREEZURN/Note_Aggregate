## Expectation
Expectation is average. The expectation of a discrete random variable $X$ is: 
$$E[g(X)] = \sum_{x} g(x) \times P(X = x)$$ 
If $g(X)$ has multiple terms, feel free to split each one into its own expectation. $E[C] = C$.
-# Moments are defined as the expectation of a random to some power. For example, $E[X^2]$ is the second moment of $X$.

Conditional expectation of a random variable given either an event or random variable simply changes the PMF portion of the summation to contain the same "given" statement. To find the general expectation of the random variable, use Total Expectation Theorem: $E[X] = \sum_i E[X | B_i] \times P(B_i)$. $B_i$ is from partitioning the sample space—essentially every "given" statement that can lead to $X$. If $X$ and $Y$ are independent, then $E[XY] = E[X] \times E[Y]$.

It is possible to find the expectation of distributions. There is some logic behind them, some more complex than simply plugging in values, but it is better to simply list the expectations out.
- Bernoulli: $p$
- Binomial: $np$
- Poisson: $\lambda$
- Geometric: $\frac{1}{p}$

Expectation of a continuous random variable is $E[g(X)] = \int_{-\infty}^{\infty} g(x) \times f_X(x)$. For the various distributions...
- Uniform: $\frac{a + b}{2}$. 
- Exponential: $\frac{1}{\lambda}$

## Variance
Variance measures spread. There are two forms of the equation: 
$$var(g(X)) = E[g^2(X)] - (E[g(X)])^2$$
$$var(g(X)) = E[(g(X) - E[g(X)])^2]$$
Standard deviation of $X$ is also a measure of spread, and it is calculated by the formula $\sigma_X = \sqrt{var(X)}$.

There's some properties to know about variance: $var(X + k) = var(X)$ and $var(aX) = a^2 \times var(X)$. If $X$ and $Y$ are independent, then $var(X \pm Y) = var(X) + var(Y)$. This may be extended to a larger number of random variables.

Like expectation, it is possible to get the variance of distributions.
- Bernoulli: $p(1 - p)$
- Binomial: $np(1 - p)$
- Poisson: $\lambda$
- Geometric: $\frac{1 - p}{p^2}$
- Exponential: $\frac{1}{\lambda^2}$