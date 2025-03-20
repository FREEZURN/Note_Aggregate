A random variable allows for the ability to model and predict the outcomes of an experiment. There are two types which specify the possible values of a random variable:
- [[#Discrete]]: Only specified values
- [[#Continuous]]: *Can be* uncountably infinite %% there CAN BE stuff in between %%
## Probability Mass Function
A PMF assigns probabilities to each value of a random variable $X$. It is commonly in the form $P(X = x)$, $x$ is a particular value. An important property to note is $\sum_{x} P(X = x) = 1$.
A Cumulative Distribution Function $F_{X}(x)$ is the sum of all probability masses up to $x$.
Joint PMFs are defined by the function $P(X = x, Y = y) = P(X = x \cap Y = y)$. It is possible to derive the PMFs of the individual random variables by summing over the other variable. For example, the marginal PMF of $X$ would be $\sum_y P(X = x, Y = y) = P(X = x)$. Joint CDFs $F_{X, Y}(x, y)$ also exist. This may be easily extended to more than two discrete random variables.
Conditional PMFs are defined as $P(X = x | Y = y) = \frac{P(X = x \cap Y = y)}{P(Y = y)}$. The multiplication rule works as one would expect. Extending the multiplication rule to three random variables gets $P(X = x \cap Y = y \cap Z = z) = P(X = x | Y = y \cap Z = z) \times P(Y = y | Z = z) \times P(Z = z)$. Random variables may be independent according to definitions one could expect. Additionally, functions of these random variables are independent too as long as they do not share random variables. Feel free to extend to even more random variables.
## Discrete
The **uniform distribution** describes an equal $P(X = x)$ for all $x$. 
A **Bernoulli** random variable $X \sim Ber(p)$, where $p$ is the probability of success, describes the probability of a success and failure. In other words, $P(X = 0) = 1 - p$ and $P(X = 1) = p$.
#### $x$ only has two possible values: $0$ or $1$.
The following three distributions build off Bermoulli. When interested in the number of successes there are in independent, finite number of trials, a **binomial** random variable $X \sim Bin(n, p)$ is used, where $n$ is the number of trials. The PMF is
$$ P(X = x) = \binom{n}{x} \times p^x \times (1 - p)^{n - x} $$
where $x$ is an integer defined on $[0, n]$. Skewness of the graph is determined by $p$:
- $p < \frac{1}{2}$: Skewed right
- $p = \frac{1}{2}$: Symmetric
- $p > \frac{1}{2}$: Skewed left

The **Poisson** random variable $X \sim Poi(\lambda)$ is like binomial but there must be a very large $n$, very small $p$, and a rate $\lambda$. Usually, $\lambda = np$. The PMF is
$$ P(X = x) = \frac{e^{-\lambda}\lambda^x}{x!} $$
A **geometric** random variable $X \sim Geo(p)$ is for the number of trials to see a success. The PMF is
$$ P(X = x) = (1 - p)^{k - 1} \times p $$
where $x$ is defined from 1 onward. Additionally,
- $P(X \geq x) = (1 - p)^{k - 1}$
- $P(X = a + b | X > a) = P(X = b)$, the memoryless property
## Continuous
The **probability density function** $f_X(x)$ is the continuous equivalent to the PMF. To find the probability of a particular $x$, plug it into the function. For the probability of an interval, take the definite integral. This interval does not care for whether the bounds are included. The property $\int_{-\infty}^{\infty} f_X(x)\; dx = 1$ must be satisfied to be a valid PDF. There is also the cumulative density function $F_X(x)$. It is simply defined as $\int_{-\infty}^{x} f_X(x)\; dx$. %%CDF must be defined along the entire domain%%
A continuous **uniform** random variable $X \sim Unif[a, b]$ has a piecewise PDF where on the domain $[a, b]$, $f_X(x) = C$. 