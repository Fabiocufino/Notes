## Interpreting test results

Regarding the final decision of a test, there are some subtle nuances to bear in mind:

- Rejecting $H_0$ does not prove that $H_0$ is false, nor that $H_1$ is true
  - What it means is that we observed enough evidence against $H_0$ and in favour of $H_1$
  
- When $p - value > \alpha$ we do not “accept $H_0$,” instead we “fail to reject $H_0$”
  - Two scenarios:
    - Either $H_0$ is true
    - Or $H_0$ is false but the test has low power

- The p-value is not the probability of the hypothesis, i.e. not $P(H_0 | X)$
  - In fact, the probability of observed data under $H_0$: $P(X | H_0)$
  - Informally, this is a measure of evidence against $H_0$
  - Another interpretation: smallest significance at which the test rejects $H_0$

- Note: test result may be statistically significant, but not scientifically relevant
  - E.g. $\theta \neq \theta_0$ but very close $\rightarrow$ may be this does not impact significantly our current theory, $H_0$
![[Pasted image 20241018093936.png|250]]


## Type-I, Type-II errors

**Type-I errors:** reject $H_0$ when it is actually true
- By construction, this happens with probability $P(X \in RR_\alpha | H_0) \leq \alpha$
- This is called significance level, or size of the test
- Interpretation of $\alpha$: probability of erroneously rejecting $H_0$

**Type-II errors**: fail to reject $H_0$ when $H_1$ is true

- By construction, this happens with probability $P(X \in \Omega \setminus RR_\alpha | H_1) = \beta$
- $1 - \beta$ is called power of the test
- Interpretation of $1 - \beta$: probability of correctly rejecting a false null hypothesis when $H_1$ is true
![[Pasted image 20241018094109.png|500]]
### Uniformly Most Powerful test (UMP)

A test is said to be «Uniformly Most Powerful» if:

- It maximizes the power for all possible values of the alternative hypothesis
- For a fixed significance level $\alpha$

In other words, no matter what the true parameter value is under $H_1$, the UMP test gives the best chance of **rejecting** $H_0$.

This is equivalent to requiring a single critical region to ensure maximum power independently on the alternative hypothesis $\rightarrow$ model-independent test.

In HEP, we often try to construct a test such that:

- $H_0$: Standard Model (or “background only”)
- $\alpha$: probability of rejecting $H_0$ when true $\rightarrow$ false discovery rate (typically $5\sigma$)
- $H_1$: interesting alternative theory, e.g. SUSY, $Z'$, ...
- We would like high power with respect to any possible alternative new theory

Unfortunately, there is no guarantee in general to have a model-independent test $\rightarrow$ We select a critical region maximizing the power of a specific $H_1$


**Intuition Behind UMP Tests**

In brief, UMP tests can be summarized as follows:

- **Power of a test**
- The probability of rejecting $H_0$ when $H_1$ is true.
- Ideally, we want the power to be as large as possible because $\rightarrow$ this means our test is sensitive to detecting true differences.

- **Why is UMP desirable?**
- A UMP test guarantees that, regardless of what the true value of the parameter is under $H_1$, our test will have the highest chance of detecting the alternative hypothesis.

- **Competing tests, i.e.**
- Different tests can have different power properties
- A test might be powerful for one value of $H_1$ but not for others
- A UMP test, if it exists, ensures that no matter what value $H_1$ takes, it is the most powerful option.

## Neyman-Pearson Lemma
The Neyman-Pearson lemma provides an elegant way to find a UMP test for testing simple hypothesis

- Let $H_0, H_1$ be two simple hypotheses, i.e.:

$H_0: \theta = \theta_0$ vs. $H_1: \theta = \theta_1 \neq \theta_0$

- Let $t(X) = \frac{\mathcal{L}(\theta_1)}{\mathcal{L}(\theta_0)}$ be a test statistic defined as the ratio between the likelihoods under the two hypotheses, $\mathcal{L}(\theta | X, H_1)$ and $\mathcal{L}(\theta | X, H_0)$ respectively.

- For a fixed significance level $\alpha$, the Neyman-Pearson lemma shows that:

	- The decision rule: "reject $H_0$ when $t(X) > k$" is the UMP test, where $k$ is chosen such that $P_{\theta_0}(t(X) > k) = \alpha$

---

**Limitations:**

- UMP tests do not always exist! Neyman-Pearson lemma only holds for simple hypotheses
- What about composite hypotheses? i.e., one-sided or two-sided tests
- This result relies on assumptions about the underlying data distribution
- What if $\mathcal{L}(\theta)$ is incorrect, or if we do not know it?





### *Wald test*

Let $\theta$ be a scalar parameter and $\hat{\theta}$ be its estimate. Also, let $\hat{\sigma}$ be the estimated standard error of $\hat{\theta}$.  
Consider testing: $H_0: \theta = \theta_0$ versus $H_1: \theta \neq \theta_0$

- When $\hat{\theta}$ is Normal:

$$ \hat{\theta} \sim N(\theta_0, \sigma^2) \rightarrow \frac{\hat{\theta} - \theta_0}{\hat{\sigma}} \sim N(0, 1) $$

- Then we can define the Wald test as:
  - Choose test statistic $W = \frac{\hat{\theta} - \theta_0}{\hat{\sigma}}$
  - Choose critical value $k$ based on asymptotic normal distribution

$$ P_{\theta_0}(|W| > k) = \alpha \rightarrow P_{\theta_0}(|Z| > k) = \alpha \rightarrow
  \begin{cases} 
  P_{\theta_0}(Z > k) = \frac{\alpha}{2}, & \text{when } W > 0 \\ 
  P_{\theta_0}(Z < -k) = \frac{\alpha}{2}, & \text{when } W < 0 
  \end{cases} $$

- Hence, we set $k$ as the quantiles of a standard normal distribution $z_{\alpha / 2}$, i.e. threshold for which $P_{\theta_0}(Z > z_{\alpha / 2}) = \frac{\alpha}{2}$

- In other words: the critical point is the value for which the cdf of a standard normal returns $1 - \frac{\alpha}{2}$, i.e. $z_{\alpha / 2} = \Phi^{-1}\left(1 - \frac{\alpha}{2}\right)$

![[Pasted image 20241018095115.png|300]]![[Pasted image 20241018095228.png|600]]
![[Pasted image 20241018095314.png|700]]
Decision Rule: – If p-value ≤ α → Reject H₀ -> new discovery