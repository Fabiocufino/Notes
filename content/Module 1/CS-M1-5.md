# How do multiple factors and their combinations influence a process?

---
### Outline of Topics

1. **Modeling processes with multiple influencing random factors**: How multiple random variables can be used to describe complex systems.
2. **Multivariate Random Variables**: Joint, marginal, and conditional probability distributions.
3. **Transformations of Random Variables**: Techniques for deriving distributions of functions of random variables.

---

## Introduction to Multivariate Random Variables

When dealing with systems influenced by more than one random factor, we use multivariate random variables. Instead of analyzing each variable in isolation, multivariate analysis examines their combined behavior.

### Example: Weather Forecasting Model

Consider a model predicting weather in a coastal city. In this case, two observable random variables could define the daily conditions:

- \( X \): Daily maximum temperature in degrees Celsius (°C).
- \( Y \): Relative humidity percentage (%).

Our question: **What is the probability of observing a particular combination of temperature and humidity?**

Since both \( X \) and \( Y \) influence weather conditions, we cannot consider them independently. Instead, we use a **Joint Probability Distribution** to describe the likelihood of specific combinations of temperature and humidity.

##### Joint Probability Distribution

For two random variables \( X \) and \( Y \), the **joint probability distribution** \( f(X, Y) \) quantifies the probability of simultaneously observing particular values of both \( X \) and \( Y \). For instance, if \( f(25, 80) \) represents the probability of a 25°C day with 80% humidity, then we can formally express this as:
$$
P(A \cap B) = \iint f(x, y) \, dx \, dy
$$

##### Marginal Distribution

The **marginal distribution** focuses on the probability of observing values of one variable while ignoring the influence of the other. For example, to find the probability of a specific temperature regardless of humidity, we integrate over all possible values of \( Y \):
$$
P(A) = \int f(x, y) \, dy = f(x)
$$

![[Pasted image 20241105122038.png|500]]

#### Conditional Distribution

If we want to know the probability of humidity \( Y \) given a fixed temperature \( X \), we use the **conditional distribution**:
$$
P(B|A) = \frac{P(A \cap B)}{P(A)} \Rightarrow f_{Y|X}(y|x) = \frac{f(x, y)}{f(x)}
$$
This ratio normalizes the joint probability to ensure that probabilities sum up to one over the conditional distribution's domain.
![[Pasted image 20241105122253.png|250]]
![[Pasted image 20241105122314.png|400]]

---
## Multivariate Moments

Multivariate moments extend the concept of moments (like mean and variance) to cases involving two or more random variables. These moments help quantify the joint behavior of variables.

### Mixed Moments

For two random variables \( X \) and \( Y \) with means \( \mu_X \) and \( \mu_Y \), respectively, **mixed moments** of order \( (m, n) \) are defined as:
$$
V_{m,n} = E[(X - \mu_X)^m (Y - \mu_Y)^n]
$$

Most used is: **Covariance**

The **covariance** between \( X \) and \( Y \), a commonly used mixed moment, measures how much \( X \) and \( Y \) vary together:
$$
\text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)] = E[XY] - E[X]E[Y]
$$
If $\text{Cov}(X, Y) > 0$ , \( X \) and \( Y \) tend to increase together; if  $\text{Cov}(X, Y) < 0$, one increases as the other decreases.

### Correlation Coefficient

The **correlation coefficient** \( \rho \) standardizes covariance to a value between -1 and 1, representing the strength and direction of a linear relationship:
$$
\rho = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y}
$$
- \( \rho = 1 \): Perfect positive correlation
- \( \rho = -1 \): Perfect negative correlation
- \( \rho = 0 \): No linear correlation

![[Pasted image 20241105122435.png]]

### Covariance Matrix

In the multivariate context, we use a **covariance matrix** to summarize the variances and covariances of a set of random variables. For a vector $\mathbf{X} = (X_1, X_2, \ldots, X_n)$:
- Diagonal elements represent variances, i.e., $V_{ii} = \text{Var}(X_i)$ 
- Off-diagonal elements represent covariances, i.e., $V_{ij} = \text{Cov}(X_i, X_j)$

![[Pasted image 20241105122501.png|700]]

- Example ![[Pasted image 20241106220523.png|600]]
## Multivariate Gaussian Distribution

One important example of multivariate distributions is the **multivariate Gaussian (normal) distribution**. Suppose $\mathbf{X} = (X_1, X_2, \ldots, X_n)$  consists of i.i.d. normal variables, each with mean $\mu$ and variance $\sigma^2$. Then $\mathbf{X}$  has a **multivariate Gaussian distribution**:
$$
\mathbf{X} \sim \mathcal{N}(\mu, V)
$$
where:
- $\mu$ is the vector of means for each variable.
- $V$ is the covariance matrix.

The probability density function (pdf) for a multivariate normal is:
$$
f(\mathbf{X} = \mathbf{x}; \mu, V) = \frac{1}{(2 \pi)^{n/2} |V|^{1/2}} e^{-\frac{1}{2} (\mathbf{x} - \mu)^T V^{-1} (\mathbf{x} - \mu)}
$$
where |$V$|  is the determinant of $V$

![[Pasted image 20241105122735.png|600]]

### Functions of Random Variables

Transforming random variables often yields new variables with their own distributions. Suppose $Y = g(X)$, where  $g$  is a function of $X$. The pdf of $Y$ is given by:
$$
f_Y(y) = f_X(x) \Big| \frac{dx}{dy} \Big| \quad \text{where } x = g^{-1}(y)
$$
- Example ![[Pasted image 20241106220502.png|600]]
What if the transformation is **not monotonic**? i.e. what if not unique inverse?
![[Pasted image 20241106220610.png|600]]

In general, let X be a R.V. with probability function 𝑓 𝑥 and let 𝑌 = 𝑔(𝑋) be its transformation. Assuming g() is invertible (but the inverse is not necessarily unique), the probability function of Y can be derived in 3 steps:
![[Pasted image 20241106220725.png|600]]
- Example![[Pasted image 20241106220813.png|600]]
# Functions of Many Random Variables

Let $\mathbf{X} = (X_1, X_2, \dots, X_n)$ be a random vector with a known joint probability density function $f_{\mathbf{X}}(\mathbf{x})$. Let $\mathbf{Y} = g(\mathbf{X})$ be a new random vector where each component of $\mathbf{Y} = (Y_1, Y_2, \dots, Y_m)$ is a function of $\mathbf{X}$.

- Then the pdf of $\mathbf{Y}$ can be expressed as:
  $$
  f_{\mathbf{Y}}(\mathbf{y}) = f_{\mathbf{X}}(\mathbf{x}) \, \left| \det \frac{d\mathbf{x}}{d\mathbf{y}} \right|
  $$
  where
  - $\mathbf{x} = g^{-1}(\mathbf{y})$ is the inverse transformation (assuming it exists)
  - $\frac{d\mathbf{x}}{d\mathbf{y}}$ is the Jacobian matrix of partial derivatives
  - we take the determinant of the Jacobian.

#### Examples

Let $X$, $Y$ be two random variables with a known joint probability density function $f_{X,Y}(x, y)$. Let $Z = X + Y$ be a new random variable. What is the distribution of $Z$?

- In general:
  $$
  f_Z(z) = \int f_{X,Y}(x, z - x) \, dx
  $$
- However, if $X$ and $Y$ are independent, we can further decompose:
  $$
  f_Z(z) = \int f_X(x) f_Y(z - x) \, dx
  $$
  that is the convolution formula.

---
---
## Error Propagation

Let $X$ be a random variable representing the measurement of a physical quantity, and let $Y = g(X)$ be its transformation. Suppose $V(X)$ is known, which quantifies the error on the measurement of $X$. What is the variance (error) of $Y$?

In principle, we could compute the variance of $g(X)$ analytically by exploiting the definition. However, this is often impractical:
  - We may not know the distribution of $X$
  - Calculation could be too complex for direct computation.

Alternatively, we can use the error propagation formula for approximating $V(Y)$:
- Use first-order Taylor series expansion of $g(X)$ around $E(X) = \mu$
    $$
    g(X) \approx g(\mu) + g'(\mu) \, (X - \mu)
    $$
- Then:
    $$
    V(Y) = E\left[g'(\mu)^2 \, (X - \mu)^2\right] = g'(\mu)^2 V(X)
    $$
  - This means the variance of $Y$ is proportional to the variance of $X$, scaled by the square of the derivative of $g(X)$ computed at $\mu$.

In general, if $\mathbf{X} = (X_1, X_2, \dots, X_n)$ and $\mathbf{Y} = g(\mathbf{X})$, then:
  $$
  V(Y) = \left( \frac{d g}{d X_1} \right)^2 V(X_1) + \dots + \left( \frac{d g}{d X_n} \right)^2 V(X_n) + 2 \sum_{i \neq j} \frac{d g}{d X_i} \frac{d g}{d X_j} \, \text{Cov}(X_i, X_j)
  $$
  - Note: no assumptions about the distributions of $X_i$.

**Limitations**

While convenient in practice, several assumptions must hold for error propagation to be effective:
- $g(X)$ is smooth and can be well-approximated by a linear expansion.
- Uncertainties in the random variable are relatively small, so higher-order terms in Taylor expansion can be neglected.
- Variances and covariances of $X$ are known (or can be estimated).

![[Pasted image 20241106221312.png|500]]


#### Examples
**Example 1**

Let $X_1$, $X_2$ be two random variables and define $Y = X_1 + X_2$ and $Z = X_1 X_2$.

- By applying error propagation formulas, we get:
  $$
  V(Y) = V(X_1) + V(X_2) + 2 \, \text{Cov}(X_1, X_2)
  $$
  $$
  V(Z) = \left( \frac{\partial Z}{\partial X_1} \right)^2 V(X_1) + \left( \frac{\partial Z}{\partial X_2} \right)^2 V(X_2) + 2 \frac{\partial Z}{\partial X_1} \frac{\partial Z}{\partial X_2} \, \text{Cov}(X_1, X_2)
  $$
- If $X_1$ and $X_2$ are uncorrelated:
  - Add errors quadratically for sum, $Y$ (or difference).
  - Add relative errors quadratically for product, $Z$ (or ratio).
  - Do not apply when correlations are present.

**Exercise**: Derive the formula for $V(Z)$.

If $\mu_{X_1} = E(X_1)$ and $\mu_{X_2} = E(X_2)$, the formula becomes:
$$
V(Z) = \mu_{X_2}^2 V(X_1) + \mu_{X_1}^2 V(X_2) + \mu_{X_1} \mu_{X_2} \, \text{Cov}(X_1, X_2)
$$

---
**Example 2**

Let $X_1$, $X_2$ be independent continuous $Uniform(0,1)$ random variables. Find the density of $Y = g(X_1, X_2) = X_1 + X_2 \cdot X_2$.

Solution: 
- Define the cumulative distribution function $F_Y(y)$: $$ F_Y(y) = P(Y \leq y) = P(g(X_1, X_2) \leq y) = P((x_1, x_2) : g(x_1, x_2) \leq y) = \int \int f_{X_1, X_2}(x_1, x_2) \, dx_1 \, dx_2 $$![[Pasted image 20241106221428.png|600]]