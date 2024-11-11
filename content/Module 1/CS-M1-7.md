
# Statistical inference: estimation methods and information

**Outline**

- Estimation Methods: MoMs and MLE
- Information
- Examples

**Example of an estimator: sample mean**

Let $X_1, X_2, \ldots, X_n$ be a collection of IID R.V.s with expectation equal to $\mu$ and variance equal to $\sigma^2$. By the Law of Large Numbers, for the sample mean, $\bar{X} = \sum_{i=1}^n X_i$, it holds:

![[Pasted image 20241011095152.png|600]]

Hence, if we use $\bar{X}$ as an estimator for $\mu$, then:
- $\bar{X}$ is an unbiased estimator for $\mu$.
- $\bar{X}$ is also consistent as $\lim_{n \to \infty} V(\bar{X}) = 0$.

Note: In case of weighted events:  

![[Pasted image 20241011095215.png|600]]

We can interpret $n$ as the events we would need for the same statistical fluctuations as weighted events.


**Example of an estimator: sample variance**

Let $X_1, X_2, \ldots, X_n$ be a collection of IID R.V.s with expectation equal to $\mu$ and variance equal to $\sigma^2$. Then the sample variance will be:

$$S^2 = \frac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2$$

Can we use it to estimate the population variance, $\sigma^2$? What properties hold for $S^2$?

- How can we answer?
--> Check if the estimator is unbiased. 
![[Pasted image 20241011095356.png|700]]

---

### Slide 9
**Example of an estimator: sample variance**

Let $X_1, X_2, \ldots, X_n$ be a collection of IID R.V.s with expectation equal to $\mu$ and variance equal to $\sigma^2$. Then the sample variance will be:

$$S^2 = \frac{1}{n} \sum_{i=1}^n (X_i - \bar{X})^2$$

Can we use it to estimate the population variance, $\sigma^2$? What properties hold for $S^2$?

- First thing to check is whether $S^2$ is unbiased:  
  $E[S^2] = \sigma^2$

- $S^2$ is a biased estimator for $\sigma^2$:  
  $B(S^2) = E[S^2] - \sigma^2 = -\frac{\sigma^2}{n}$

- However, $S^2$ is asymptotically unbiased since $E[S^2] \to \sigma^2$ as $n \to \infty$.

- Alternatively, we can define a “correct” version, the corrected sample variance, $S = \frac{n}{n-1} S^2$:

$$E[S] = \sigma^2$$

- **$S$ is an unbiased estimator for $\sigma^2$!**

- It is possible to show that $S$ is also consistent.

- Importantly: for normally distributed data $(X)$, then:
![[Pasted image 20241011100807.png|300]]

**Example of an estimator: sample correlation**

Let $X$, $Y$ be two R.V.s. Then we can define the sample correlation coefficient estimator as $\hat{r} = \frac{\text{V}(X, Y)}{\sqrt{\text{S}(X) \cdot \text{S}(Y)}}$, where:

$$\text{V}(X, Y) = \frac{1}{n-1} \sum_{i=1}^n (X_i - \bar{X})(Y_i - \bar{Y})$$

- In other words, $\hat{\rho}$ is defined as the ratio between the sample covariance and the product of the sample standard deviations.

- Also, $\hat{r}$ can be rewritten as: 

$$\hat{r} = \frac{(\bar{XY})(\bar{X}\bar{Y})}{\sqrt{(\bar{X^2} - \bar{X}^2)(\bar{Y^2} - \bar{Y}^2)}}$$


**Properties:**

$$E[\hat{r}] = \rho - \frac{\rho(1 - \rho^2)}{2n} + O\left(\frac{1}{n}\right)$$

- $\hat{r}$ is a biased estimator of the population correlation coefficient, $\rho$.
- However, it is asymptotically unbiased.

---

**Point estimation**

Let $X \sim \mathcal{F}(x; \theta), \, \mathcal{F}(f(x; \theta): \theta \in \Theta)$. Point estimation revolves around providing a single "best guess" for a quantity of interest:

- Parameter of a distribution $\mathcal{F}$.
- The whole distribution, e.g., cdf/pdf of $\mathcal{F}$.
- A regression function $r(X)$ assuming that $X \sim \mathcal{F}$.
- A prediction of a future value $X$.

**Conventions:**
- By convention, we denote our estimate as $\hat{\theta}$.
- $\theta$ is unknown but fixed.
- However, $\hat{\theta}$ is a random variable as it depends on data.

**How can we provide a point estimate for a parameter $\theta$?**

- Method of moments (MoM).
- Maximum likelihood estimation (MLE).

---
### Slide 13
**Method of Moments (MoM)**

Let $X \sim \mathcal{F}(x; \theta), \, \mathcal{F}(f(x; \theta): \theta \in \Theta)$, where $\theta = \{\theta_1, \ldots, \theta_K\}$ is a $K$-dimensional vector of parameters. Then, the method of moments estimator $\hat{\theta}$ can be derived as follows:

- Define the $j$-th moment $\alpha_j$, $1 \leq j \leq K$ as $\alpha_j = \alpha_j(\theta) = E[X^j] = \int x^j \, dF(x)$.
- The corresponding sample moment $\hat{\alpha}_j$ will be:  
  $\hat{\alpha}_j = \frac{1}{n} \sum_{i=1}^n X_i^j$

- Then $\hat{\theta}$ is defined as:
  
$$\alpha_1(\hat{\theta}) = \hat{\alpha}_1$$
$$\alpha_2(\hat{\theta}) = \hat{\alpha}_2$$
$$\vdots$$
$$\alpha_K(\hat{\theta}) = \hat{\alpha}_K$$

- System of $K$ equations with $K$ unknowns.
- In practice, we estimate each moment by its sample version.

**Example:**

Let $X_1, \ldots, X_n \sim \text{Bernoulli}(p)$. Then:  
$\alpha_1 = E[X] = p$ and $\hat{\alpha}_1 = \frac{1}{n} \sum_{i=1}^n X_i$. Therefore:  
$p = \frac{1}{n} \sum_{i=1}^n X_i$

---

### Slide 14
**Method of Moments Estimators: properties**

In general, under very weak assumptions, we can derive the following properties:

- $\hat{\theta}$ estimators are typically biased.
- However, $\hat{\theta}$ yield consistent estimators.
- Also, asymptotically Normal:

$$\sqrt{n} (\hat{\theta} - \theta) \xrightarrow{d} N(0, \Sigma)$$

**Takeaways:**

- Fairly simple definition and feasible to compute in practice.
- Not always sufficient statistics.
- Not the best estimators.
  - Sometimes used as initialization for numeric approximation according to other methods.

---

### Slide 15
**Likelihood function**

Let $X \sim \mathcal{F}(x; \theta), \, \mathcal{F}(f(x; \theta): \theta \in \Theta)$, where $\theta = \{\theta_1, \ldots, \theta_K\}$ is a $K$-dimensional vector of parameters. Given a random vector $\mathbf{X} = (X_1, \ldots, X_n)$ of i.i.d. random variables, we can write the joint density as:

$$P(\mathbf{X}) = f(\mathbf{X}; \theta) = \prod_{i=1}^n f(X_i; \theta)$$

Then, the likelihood function is defined as:

$$\mathcal{L}(\theta; \mathbf{X}) = f(\mathbf{X}; \theta)$$

- The likelihood is just the joint density viewed as a function of the parameter $\theta$ rather than the data $\mathbf{X}$.
- $\mathcal{L}: \Theta \to [0, \infty)$.
- The likelihood is not a density function—generally, it does not integrate to 1.
- It describes how likely it is to observe given data $\mathbf{X}$ under $\mathcal{F}$ depending on a specific parametrization $\theta$.
  - Degree of agreement between observed data and $\mathcal{F}$ parametrized by $\theta$.

---

### Slide 16
**Maximum Likelihood**

IMPORTANT 

The method of maximum likelihood provides estimates that maximize the likelihood of the observed data:

$$\hat{\theta} = \arg\max_{\theta} \mathcal{L}(\theta; \mathbf{X})$$

- The basic assumption is that what we are observing is not **rare**. 
  - It makes sense to estimate $\theta$ as the value that maximizes the agreement of data with the model.

- Parameter estimates are retrieved through optimization of the likelihood function with respect to $\theta$:
  - Derive with respect to $\theta$.
  - Set equal to zero and check which zeros are maximum points.

- For independent random variables, the likelihood can be written as a product:
  
$$\mathcal{L}(\theta; \mathbf{X}) = \prod_{i=1}^n f(X_i; \theta)$$

- Taking the logarithm is convenient for differentiation, leading to the log-likelihood:

$$\ell(\theta) = \log \mathcal{L}(\theta; \mathbf{X}) = \sum_{i=1}^n \log f(X_i; \theta)$$

- Note that critical points do not change between $\ell(\theta)$ and $\mathcal{L}(\theta; \mathbf{X})$.



### Maximum Likelihood Estimators (MLE)

More formally, let $X \sim \mathcal{F}(x; \theta), \, \mathcal{F}(f(x; \theta): \theta \in \Theta)$, where $\theta = \{\theta_1, \ldots, \theta_K\}$ is a $K$-dimensional vector of parameters. The maximum likelihood estimator of $\theta$ is defined as:

$$\hat{\theta} = \arg\max_{\theta} \mathcal{L}(\theta; \mathbf{X})$$

- In practice, to calculate $\hat{\theta}$ we can:
  - Compute the log-likelihood: $\ell(\theta) = \log \mathcal{L}(\theta; \mathbf{X})$
  - Derive the log-likelihood: $S(\theta) = \frac{\partial \ell(\theta)}{\partial \theta}$
    - $S(\theta)$ is typically referred to as the score function.
  - Set $S(\theta) = 0$ and solve for $\theta$ to find critical points.
  - Check which critical points correspond to a maximum (second derivative negative at $\hat{\theta}$).

---
**Example:**  
Let $X_1, \ldots, X_n \sim \text{Bernoulli}(p)$. What is $\hat{p}$?

**Solution**
$$\mathcal{L}(p) = \prod_{i=1}^n p^{X_i} (1 - p)^{1 - X_i} = p^S (1 - p)^{n - S}, \, \text{where } S = \sum_{i=1}^n X_i$$

- $\ell(p) = S \log p + (n - S) \log (1 - p)$.
- $S(p) = \frac{\partial \ell}{\partial p} = \frac{S}{p} - \frac{n - S}{1 - p}$.
- Solve $S(p) = 0 \implies p = \frac{S}{n} = \frac{\sum_{i=1}^n X_i}{n}$.

(Note: $\frac{\partial^2 \ell}{\partial p^2} = -\frac{n}{p (1 - p)}$ is always negative.)

**Conclusion:**  
Same results for MoM and MLE estimators!  
$\Rightarrow$ Not always the case!

---

### Slide 20
**What is information in statistics?**

The concept of information in statistics is related to the "knowledge" one can derive from data.

**Example:** You have performed an experiment and collected some data:
- What is the information data provide about the model?

In general, the above concept must hold some properties:
- Increase with the number of observations.
- Related to the parameters of interest.
  - Non-related data should not increase information.
  - Should be related to precision $\Rightarrow$ the larger the information, the better the precision.

**In other words:** The amount of uncertainty reduced by an observation/experiment.

**Note:** Data reduction typically implies information loss.
$\Rightarrow$ How to go from raw data to high-level summaries (reconstruction) minimizing information loss?

---

### Slide 21
**Shannon entropy**

Shannon’s definition relates information to uncertainty.

Let $X$ be a random variable with $K$ possible outcomes $x_1, \ldots, x_K$, each with probability $p_i$. Then the information coming from observing an outcome $x_i$ is defined as:

$$I(x_i) = \log \left(\frac{1}{p_i}\right) = -\log p_i, \, \text{(base $b$ arbitrary)}$$

$\Rightarrow$ The smaller $p_i$, the higher the information.

Starting from the above definition, Shannon information associated to the random process $X$ is defined as its expected information:

$$H(X) = E[I] = - \sum_{i=1}^K p_i \log p_i \, \text{(also called entropy)}$$

**Intuition:** The greater the entropy, the higher the information we gain by observing the random process.

**Interpretation:** Can be seen as the average memory needed to encode a message.  
$\Rightarrow$ Related to data compression.

---

### Slide 22
**Fisher information**

Fisher’s definition links information to the knowledge a sample provides about an unknown parameter.

Let $\mathbf{X} = (X_1, \ldots, X_n)$ be a random vector representing a sample of $n$ observations, and let $\mathcal{L}(\theta; \mathbf{X})$ be the corresponding likelihood function depending on the parameter $\theta$. Then the information carried by the sample about $\theta$ is defined as:

$$I(\theta) = E\left[ \left( \frac{\partial \ell(\theta; \mathbf{X})}{\partial \theta} \right)^2 \right] = E\left[ \left( \frac{\partial}{\partial \theta} \log \mathcal{L}(\theta; \mathbf{X}) \right)^2 \right]$$

Under quite general regularity conditions, we have: $E\left[\frac{\partial \ell(\theta; \mathbf{X})}{\partial \theta}\right] = 0$.
Hence, $I(\theta) = \text{Var}\left(\frac{\partial \ell(\theta; \mathbf{X})}{\partial \theta}\right)$.

$\Rightarrow$ Fisher information is related to the variance of the score function.

In addition, if $\ell(\theta; \mathbf{X})$ is also twice differentiable with respect to $\theta$, then:

$$I(\theta) = -E\left[\frac{\partial^2 \ell(\theta; \mathbf{X})}{\partial \theta^2}\right]$$

$\Rightarrow$ Fisher information is also linked to the curvature of the likelihood.

**Intuition:** Likelihood sensitivity to the data, i.e., for larger curvature, slight changes in sample data radically alter our estimate $\Rightarrow$ data carry a lot of information about $\theta$.

![[Pasted image 20241011113702.png|600]]

---

### Slide 23
**Fisher information (continued)**

- Fisher information can be thought of as a measure of the amount of information that an observable random variable $X$ carries about an unknown parameter $\theta$ upon which the likelihood depends.
- If $\ell(\theta; X)$ is the log-likelihood function, then the Fisher information is defined as:

$$I(\theta) = -E\left[\frac{\partial^2 \ell(\theta; X)}{\partial \theta^2}\right]$$

**Properties:**
- Fisher information is non-negative.
- It plays a central role in the Cramér-Rao lower bound, which provides a lower bound for the variance of unbiased estimators.

**Intuition**: Higher Fisher information implies that the data provides more information about the parameter, resulting in a smaller variance of the estimator.

---

### Slide 24
**Cramér-Rao Theorem (also Rao-Cramér-Frechet or RCF bound)**

This theorem is a powerful tool that sets a lower bound for the variance of unbiased estimators for a parameter $\theta$.

- Let $\hat{\theta}$ be an unbiased estimator for a parameter $\theta$.
- Let $f(X, \theta)$ be the probability distribution of the data $X$.
- Then the Cramér-Rao theorem shows that:

$$\text{Var}(\hat{\theta}) \geq \frac{1}{I(\theta)}$$

$\Rightarrow$ The inverse of Fisher information is the lower bound for the variance of any unbiased estimator of $\theta$.

**Note**: This provides a reference setting for evaluating the efficiency of an estimator:

$$\text{efficiency}(\hat{\theta}) = \frac{I(\theta)}{\text{Var}(\hat{\theta})} \leq 1$$

- When $\text{efficiency}(\hat{\theta}) = 1$, then $\hat{\theta}$ is said to be an optimal estimator for $\theta$ (also known as the Minimum Variance Unbiased Estimator or MVUE).

---

### Slide 25
**Maximum Likelihood Estimators: properties**

Under fairly weak assumptions, MLE estimators have several nice properties:

- **Equivariance**: 
  - Let $\hat{\theta}$ be the MLE estimator for $\theta$, and let $g(\cdot)$ be a bijective transform (one-to-one).
  - Let $\gamma$ be a different parameterization such that $\gamma = g(\theta)$.
  - Then $\hat{\gamma} = g(\hat{\theta})$.
  - $\Rightarrow$ We can easily find MLE for transforms of the parameter $\theta$, e.g., useful when changing units, scale, or parametrization.

- **Consistency**: As the sample size increases, the MLE converges to the true parameter value.

- **Asymptotic efficiency**: Among all well-behaved estimators, the MLE has the smallest variance as $n \to \infty$.

- **Asymptotic Normality**: 

$$\sqrt{n}(\hat{\theta} - \theta) \xrightarrow{d} N(0, I(\theta)^{-1})$$

  - As the sample size increases, the MLE estimator distribution approaches a Gaussian centered around the true $\theta$.
  - Note: $I(\theta)$ is the Fisher information computed at the true value $\theta$ (often computed analytically).

- **“Often” a function of a sufficient statistic**.

**Takeaways**:  
In general, there are no optimal properties for finite samples (e.g., no guarantee MLE is unbiased!), but MLE is very appealing asymptotically.

---

### Slide 26
**BONUS: MLE song for «tuning parameters»**

A little bit of fun helps in remembering…

**MLE song!**  

He played the song in class -> Cringest moment in class
### Slide 27
**Examples of Maximum Likelihood Estimators for popular distributions**

**Exponential distribution: estimator for average number of events**

Let $X$ be a random variable that models the decay time of a radioactive nucleus, such that:

$$X \sim \text{Exp}(\lambda)$$

where $\lambda$ is the average number of decays per year.

- What is the MLE for $\lambda$?
- Is $\hat{\lambda}$ an unbiased estimator for $\lambda$?


---


# Examples of Maximum Likelihood estimators for popular distributions

- exercises for exam 