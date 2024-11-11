
# Statistical inference: estimators and information

---
### Outline

- How can we learn from data?
- Estimators
- Maximum Likelihood

---

### How can we learn from data?

Statistical inference, or «learning», is the process of extracting knowledge about a phenomenon from its own data.

- What is the distribution of the data? And what are its properties?
- Typically, we cannot observe the whole population (limited time, resources, or process not fully observable).
- We resort to a «sample» instead and only observe limited evidence/data.

Derived questions:

- How to derive properties or models based on partial information?
- How to quantify uncertainty?
- How to test hypotheses and make predictions?

---
### Parametric vs non-parametric inference

There are several approaches to statistical inference, depending on assumptions. A key distinction is between parametric and non-parametric inference.

**Parametric**  
We assume the process is described by a function with a finite set of parameters:

$$ X \sim \mathcal{F}(x; \theta), \mathcal{F} = f(x; \theta): \theta \in \Theta $$

Where:
- $\mathcal{F}$ is a family of functions parametrized by $\theta$.
- $\theta$ is the fixed (there is a true value that describes it, is not random) but unknown (vector of) parameters.
- $\Theta$ is the parameter space, i.e., all allowed values for $\theta$.

Goal: Inference about distribution parameters $\theta$.  
- More powerful if assumptions hold  :)
- Incorrect if assumptions are violated  :(

**Non-parametric**  
We do not assume a specific functional form for $\mathcal{F}$. It is modelled by a non-finite number of parameters.
This means that  $\mathcal{F}$ is modelled by a non-finite number of parameters
- we do not make assumptions on $\mathcal{F}$
- $\mathcal{F}$ has no parameter

It's more flexible and we allow a more number of parameters. 

**Goal**: inference about data characteristics, e.g. median as central tendency
- More flexible, robust to outliers/deviations :)
- More complex and less powerful than valid parametric alternatives :(

![[Pasted image 20241007145327.png|350]]
 
### Parametric vs non-parametric inference: example

**Measuring the speed of sound in air:**  
We take 50 measurements under identical conditions.

- **Parametric**  
  Assume measurements follow a Gaussian distribution:  
  $$ X \sim \mathcal{F}(x; \theta) = f(x; \mu, \sigma) = \frac{1}{\sigma \sqrt{2 \pi}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}: \mu \in \mathbb{R}, \sigma > 0 $$

  Estimate the parameters $\mu$, $\sigma$. Inference is based on $N(\mu, \sigma)$.

- **Non-parametric**  
  No assumption on underlying distribution $\mathcal{F}$. Use median and interquartile range (IQR) for central tendency and spread.
  - Use median as measure of central tendency
  - Use interquartile (IQR) range for spread -> our description depends on summary statistics of observed data: median and IQR

---

### Parameters of interest vs nuisance parameters

Imagine we know that we can describe the distribution F with a set of parameters, now more than 1:  $X \sim \mathcal{F}(x; \theta = \{\alpha, \beta\})$

In all the parameters we chose parameters in which we are interested in and others that we think are not that interesting.
- $\alpha$: parameters of interest (e.g., $\mu$).
- $\beta$: **nuisance parameters** (e.g., $\sigma$), which determine the shape of $f(x; \mu, \sigma)$ but are not of interest.

**Example:**
![[Pasted image 20241007150035.png|600]]

### From population to sample 
![[Pasted image 20241007151631.png|250]]

Typically we cannot observe the whole population: Hence we resort to sampling

• *Population*: entire group of individuals/entities under study
	– Often too large/impractical to observe
	– E.g. all electrons in the universe, all possible decays
	– Population quantities are referred to with Greek letters: 𝜃, 𝜇, 𝜎

• *Sample*: subset of the population
	– Useful to make inference without observing all population
	– E.g. electrons revealed in a specific experiment
	– Sample quantities are referred to with Latin letters: 𝑥̅, $s^2$
	– Must be representative of the population -> different sampling methods ensure different properties (not covered here)

• *Statistical units*: individual elements of the population/sample
	– Basic entities on which measurements/observations are made
	– E.g. single electron


**Inference is about retrieving information about the population starting from a sample**

### Statistical inference: sub-problems

1. Estimating parameters (point estimates, interval estimation).
	- I know the model and I want to estimate its parameters
1. Hypothesis testing.
	- Compare two models/hypotheses
1. Goodness-of-fit.
	- Measure how well a model/hypothesis fit the data (a model VS all the others)
### Data statistics and estimators

How do we estimate our parameters of interest, 𝜽?

We define a statistic as a generic function of data:  $t = t(\vec{X}) = t(X_1, \dots, X_n)$.  
- Examples:  
  Parameters of interest: expected value ($\mu$), variance ($\sigma^2$).  
  Related statistics: sample mean ($\bar{X}$), sample variance ($s^2$).

- **How do we choose good statistics as estimators?**

### Bias and precision

We are conducting a statistic and we are conducting some inference assuming that x is distributed in a F distribution.


**Bias:** The bias of a statistic $t(X)$ as an estimator for $\theta$ is:

$$ B(t(X)) = E(t(X)) - \theta $$

- The bias measures how close, on average, the statistic is to the true parameter value: Measures the accuracy of the statistic.
- Ideally, we would like the bias to be as low as possible
- A statistic with 0 bias is called unbiased estimator of 𝜽

**Precision:** The precision of a statistic $t(X)$ is:

$$ \text{precision}(t(X)) = \frac{1}{V_{\theta}[t(X)]} $$
- The precision measures the **dispersion** of the statistic around its expected value.
- Measures the variability of the statistic.
- A statistic with highest precision is called efficient estimator of 𝜽:
$$V_{\theta}[t(X)] \leq V_{\theta}[t^*(X)] $$ for any $t^*$.

### Accuracy vs precision

- **Accuracy**: How close the estimator is to the true value.
- **Precision**: How variable the estimator is.

![[Pasted image 20241007154827.png|400]]

---
### Mean Squared Error (MSE)

A measure of the quality of an estimator is given by the MSE:

$$ MSE(t(X)) = E_{\theta}\left[ (t(X) - \theta)^2 \right] = V(t(X)) + B(t(X))^2 $$

- Trade-off between bias and variance.
![[Pasted image 20241007155322.png|700]]

![[Pasted image 20241110171144.png|600]]

### Consistency and sufficiency
Let $X \sim \mathcal{F}(x; \theta), \, \mathcal{F}(f(x; \theta): \theta \in \Theta)$ and $t(X)$ be a statistic. The statistics $t(X)$ could have the property of

**Consistency:** A statistic $t(X)$ is consistent if:

$$ t(X) \to \theta, \quad \text{as} \ n \to \infty $$

**Sufficiency:** A statistic $t(X)$ is sufficient for $\theta$ if:

$$ P(X | t(X), \theta) = P(X | t(X)) $$
- all information about 𝜽 is already contained in 𝑡(X)
	- it embeds all useful information for the parameters of interest

**Summary of data statistics properties**

Let $X \sim \mathcal{F}(x; \theta), \, \mathcal{F}(f(x; \theta): \theta \in \Theta)$ and $t(X)$ be a statistic. Then $t(X)$ will be good as an estimator for $\theta$ when it satisfies the following properties:

- **Unbiasedness**: On average, does the statistic hit the true parameter value?  
  $E(t(X)) = \theta$

  - In practice, we want low bias (ideally 0), which means low systematic error: $b = E(t(X)) - \theta$

- **Efficiency**: How much does it vary around the true value?  
  $V(t(X)) \leq V(t^*(X))$, for any $t^*$

  - In practice, we want as little variability around $\theta$ as possible.

- **Consistency**: Does the statistic converge to the true value as the sample size increases?  
  $t(X) \to \theta$, that is:  
  $\lim_{n \to \infty} P(|t(X) - \theta| < \epsilon) = 1$

  - For $n \to \infty$, we have that the estimator converges to a fixed value equal to the true parameter (i.e., zero variance).

- **Sufficiency**: Does it embed all useful information for the parameters of interest?  
  $P(X | t(X), \theta) = P(X | t(X)) \, \forall \, \theta$

  - This means that all information about $\theta$ is already contained in $t(X)$.

---
---


## Point estimation

# Point Estimation

Imagine we know that $X \sim \mathcal{F}(x; \theta)$, $\mathcal{F}\{f(x; \theta): \theta \in \Theta \}$. Point estimation revolves around providing a single "best guess" for a quantity of interest.

- Parameter of a distribution $\mathcal{F}$
- The whole distribution, e.g., cdf/pdf of $\mathcal{F}$
- A regression function  $r(X)$ assuming that  $X \sim \mathcal{F}$
- A prediction of a future value $X$

Notes:
- By convention, we denote our estimate as $\hat{\theta}$ 
- $\theta$ is unknown but fixed
- However, $\hat{\theta}$ is a random variable as it depends on data

How can we provide a point estimate for a parameter \( \theta \)?
- Method of moments
- Maximum likelihood

### Method of Moments

# Method of Moments

Let $X \sim \mathcal{F}(x; \theta)$ , $\mathcal{F}\{f(x; \theta): \theta \in \Theta \}$, where $\theta = \{\theta_1, \dots, \theta_K\}$ is a $K$-dimensional vector of parameters. Then, the method of moments estimator $\hat{\theta}_n$ can be derived as follows:

- Define the $j$-th moment  $\alpha_j$, $1 \leq j \leq K$ as $\alpha_j = \alpha_j(\theta) = E_\theta \left[ X^j \right] = \int x^j dF_\theta(x)$
- The corresponding sample moment  $\hat{\alpha}_j$ will be: $\hat{\alpha}_j = \frac{1}{n} \sum_i X_i^j$
- Then $\hat{\theta}_n$  is defined as:
  $$
  \alpha_1(\hat{\theta}_n) = \hat{\alpha}_1
  $$
  $$
  \alpha_2(\hat{\theta}_n) = \hat{\alpha}_2
  $$
  $$
  \dots
  $$
  $$
  \alpha_K(\hat{\theta}_n) = \hat{\alpha}_K
  $$

- System of $K$ equations with $K$ unknowns
  - In practice, we estimate each moment by its sample version

**Example**:
Let $X_1, \dots, X_n \sim \text{Bernoulli}(p)$.
Then: $\alpha_1 = E(X_1) = p$ and $\hat{\alpha}_1 = \frac{1}{n} \sum_i X_i$.
Therefore: $\hat{p}_n = \frac{1}{n} \sum_i X_i$


---

### Likelihood function and Maximum Likelihood 

# Likelihood Function

Let $X \sim \mathcal{F}(x; \theta)$, $\mathcal{F}\{f(x; \theta): \theta \in \Theta \}$, where $\theta = \{\theta_1, \dots, \theta_K\}$ is a $K$-dimensional vector of parameters.  
Given a random vector $\mathbf{X} = \{X_1, \dots, X_n\}$ of i.i.d. random variables, we can write the joint density as:

$$
P(\mathbf{X}) = f(\mathbf{X}; \theta) = \prod_{i=1}^n f(X_i; \theta)
$$

Then, the likelihood function is defined as:

$$
L_n(\theta; \mathbf{X}) = \prod_{i=1}^n f(X_i; \theta)
$$

- Nothing but the joint density as a function of the parameter $\theta$ instead of the data $\mathbf{X}$
  - $L_n: \Theta \rightarrow [0, \infty)$
- The likelihood is *not* a density function $\rightarrow$ in general, does not integrate to 1
- Describes how likely it is to observe given data $\mathbf{X}$ under $\mathcal{F}$ depending on a specific parametrization $\theta$
  - degree of agreement between observed data and $\mathcal{F}$ parametrization by $\theta$


The method of **maximum likelihood** provides estimates that maximize the likelihood of the observed data:
$$
\hat{\theta}_{MLE} = \arg \max_{\theta} L_n(\theta; \mathbf{X})
$$

- The basic assumption is that what we are observing is not rare  
  - it makes sense to estimate $\theta$ as the value that maximizes the agreement of data with the model
- Parameter estimates are retrieved through optimization of the likelihood function with respect to $\theta$
  - Derive with respect to $\theta$
  - Set equal to zero and check which zeros are maximum points

- By definition, for independent random variables the likelihood can be written as a product:
  $$L_n(\theta; X) = \prod_{i=1}^{n} f(X_i; \theta)$$

  - Taking the logarithm is convenient for differentiation  
    → we typically work on log-likelihood instead:
  $$\ell(\theta) = \log L_n(\theta; X) = \sum_{i=1}^{n} \log f(X_i; \theta)$$

  - Note that optimal point do not change!![[Pasted image 20241110172526.png|300]]

**Maximum Likelihood estimation**

More formally, let $X \sim F(x; \theta)$, $F(f(x; \theta): \theta \in \Theta )$, where $\theta = (\theta_1, ..., \theta_k)$ is a K-dimensional vector of parameters. The maximum likelihood estimator of $\theta$ is defined as:

$$\hat{\theta}_{MLE} = \underset{\theta}{\arg \max} L_n(\theta; X)$$

- In practice, to calculate $\hat{\theta}_{MLE}$ we can:
  - Compute the log-likelihood: $\ell(\theta) = \log L_n(\theta; X)$
  - Derive the log-likelihood: $S(\theta) = \frac{d \ell(\theta)}{d\theta}$  
    → $S(\theta)$ typically referred to as the *score function*
  - Set $S(\theta) = 0$ and solve for $\theta$ to find critical points
  - Check which critical points correspond to a maximum → second derivative negative at $\hat{\theta}_{MLE}$

**Example**:

Let $X_1, ..., X_n \sim IID$ Bernoulli$(p)$. Then:

$$L_n(p) = \prod_{i=1}^{n} p^{X_i} (1 - p)^{1 - X_i} = p^S (1 - p)^{n-S}, \text{ where } S = \sum_i X_i$$

$$\ell_n(p) = S \log p + (n - S) \log (1 - p)$$

$$S(p) = \frac{d \ell}{dp} = \frac{S}{p} - \frac{n - S}{1 - p} = S - Sp - np + Sp = S - n p$$

- Solve $S(p) = 0$ → $p = \frac{S}{n} = \frac{\sum_i X_i}{n}$

  (Note: $\frac{d^2 \ell(p)}{d p^2} = -n$ is always negative)


---
---

## **What is information in statistics?**

The concept of information in statistics is related to the «knowledge» one can derive from data.  
Example: you have performed an experiment and collected some data  
- What is the information data provide about the model?
- How to update knowledge in light of the new data?

In general, the above concept must hold some properties:
- Increase with the number of observations
- Related to the parameters of interest  
  - Also, non-related data should not increase information
- Should be related to precision → the larger the information, the better precision
- Also, data reduction typically would imply information loss  
  - How to go from raw data to high-level summaries (reconstruction) minimizing information loss?

→ We have two quantities with these properties: 
- Shannon information VS Fisher information

---

### Shannon Information

- Let $\xi$ be a discrete variable which can assume $k$ values with probability $p_i$ $(i = 1, ..., k)$.  
  If the outcome is $\xi_j$ the information is defined as:
$$I = \log_b \frac{1}{p_j} \quad (b \text{ arbitrary base})$$

  Rationale: the smaller $p_j$, the larger the information carried by the outcome is

- Shannon Entropy is the expectation value of $I$

  $$H_S = \sum_{i=1}^{k} p_i \log_b \frac{1}{p_i}$$

- With a proper choice of the base it coincides with the Boltzmann thermodynamic entropy  
  - Knowing the macrostate of the system (temperature) we can derive the information about the corresponding microstate

- Related to data compression

### Fisher Information
Here is the extracted text with equations placed between `$` symbols:


Let us first introduce the *Likelihood function*:

- It is the same function of the pdf itself, but now the variable $x$ is replaced by its outcome (the experiment is done!) and so it becomes a function of the parameter $\theta$

  $$\mathcal{L}(x; \theta) = f(\theta)$$

- If we now consider a set of $n$ independent and identically distributed (i.i.d.) variables $\mathbf{x}$ (e.g. repeated measurements of a given quantity), then

  $$\mathcal{L}(x; \theta) = f(x_1, \dots, x_n; \theta) = \prod_{i=1}^{n} f(x_i; \theta)$$

- $x \in \Omega_{\theta}$: $x$ domain can be a function of the parameters (e.g. estimate of the mass of a particle from decay product momenta. Their values range from zero to a maximum value $p^*$ which is a function of the mass itself!)

- Be careful: $\mathbf{x}$ is the $n$-component vector of measurements, but each measurement $x_i$ is an «event», and can be a multivariate quantity of dimension $d$ (e.g. energy, multiplicity, sphericity…)


- Let’s introduce the *score*:

  $$\nu = \frac{\partial}{\partial \theta} \ln \mathcal{L}(x; \theta)$$

- In the multi-parametric case → *gradient*

- Fisher Information is the variance of the score:

  $$I = V[\nu] = E[\nu^2] - (E[\nu])^2 = E[\nu^2]$$

  Since $E[\nu] = 0$ → simple to prove: remember that when you integrate to obtain the expectation value, the integration is in $dx$ (not $d\theta$!). To compute the expectation value is equivalent to compute $\nu(\theta)$ when the experiment is repeated an infinite number of times:

  $$E(\nu) = E\left[\frac{\partial \ln \mathcal{L}}{\partial \theta}\right] = \int \frac{\partial \ln \mathcal{L}}{\partial \theta} \mathcal{L} \, dx = \int \frac{1}{\mathcal{L}} \frac{\partial \mathcal{L}}{\partial \theta} \mathcal{L} \, dx = \frac{\partial}{\partial \theta} \int \mathcal{L} \, dx = \frac{\partial}{\partial \theta} 1 = 0$$

- Related to the LH behavior around the maximum (*curvature*)

