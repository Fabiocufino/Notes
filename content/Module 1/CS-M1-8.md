
# Hypothesis testing

## Outline
- How to test hypotheses?
- Hypothesis testing
- Examples

## How do we test hypotheses?
Hypothesis testing allows us to make informed decisions about population parameters based on sample data.

- Structured approach to evaluating claims about a population under uncertainty.
- Involves two competing hypotheses:
  - Given assumption (typically current knowledge) **vs** alternative hypothesis (challenges the status quo).
  - alternative hypotesis
- Hypothesis testing resolves **whether data are compatible with a given assumption** based on the figure of merit we are considering.

**Notes:**
- We are not proving or falsifying hypotheses!
- We quantify the evidence against our starting assumptions.

---

## Hypothesis testing: key ingredients
In general, a statistical test is structured into 6 components:

1. **Null hypothesis (H₀):** the hypothesis we want to test (typically current knowledge, status quo).
   - Example: “The mean temperature of a star is 5000K.”
2. **Alternative hypothesis (H₁):** competing theory against H₀.
   - Example: “The mean temperature of a star is not 5000K.”
3. **Test Statistic (figure of merit):** summary of sample data used to assess H₀.
4. **Significance Level (α):** degree of confidence of our conclusions.
   - Common choices: 0.05, 0.01; in physics, 5$\sigma$.
5. **p-value (p):** the probability of observing the data (or something more extreme) if H₀ is true.
6. **Decision Rule:**
   - If p-value ≤ α → Reject H₀.
   - If p-value > α → Fail to reject H₀.

---

## Hypothesis testing: intuition
The frequentist approach can be summarized as:

**“Assume H₀ is true and look for evidence in the sample that contradicts this assumption.”**

Analogy: hypothesis testing is like a courtroom trial:
- H₀: The defendant is innocent.
- H₁: The defendant is guilty.
- If evidence is strong enough (low p-value), we reject H₀ (innocence).
- If evidence is weak (high p-value), we fail to reject H₀ (no conviction).

## Hypothesis testing: hypotheses
More formally, let $X$ describe a random process with probability distribution $f(X, \theta)$, where $\theta$ is unknown.

- Let $H_0$ be a null hypothesis about the value of $\theta$, e.g. $\theta = \theta_0$.
	– We are assuming that the true value of 𝜃 is a specific values 𝜃
	– This is the hypothesis we want to test
- Let $H_1$ be an alternative hypothesis about the parameter value.
  - Can be specific: $H_1$: $\theta = \theta_1$ (simple hypothesis).
  - Can be generic: $H_1$: $\theta \neq \theta_0$ or $\theta > \theta_0$ (composite hypothesis).
- Let $X = \{X_1, \dots, X_n\}$ represent $n$ IID realizations of the random variable $X$.
  
  
--- Hypothesis testing is about finding a decision rule to judge whether sample data $X$ are compatible with the null hypothesis.

---
## Hypothesis testing: decision rule

Ideally, we would base the decision on $P(H_0|X)$. However, this is not possible in a frequentist approach.

Alternatively, we can work on the likelihood $P(X|H_0)$. This means asking the question:
**“If $H_0$ is true, what is the probability to observe the sample data $X$?”**

**Rationale:** If sample data are very unlikely under $H_0$, then we question the validity of $H_0$.

In practice, we need two elements to apply this principle:
1. **Test statistic**, i.e., a characteristic of sample data we look at as a benchmark.
   - Must be based on sample data.
   - We must know how to compute $P(t(X)|H_0)$.
2. **Significance level ($\alpha$)**:
   - The minimum probability threshold we are willing to accept. Outcomes rarer than $\alpha$ will trigger the rejection of $H_0$.
   - Also called the **size of the test**.

The key is to choose a test statistic for which we know $P(t(X)|H_0)$.

When that is the case, hypothesis testing consists of two steps:

1. **Compute the p-value**:
- The p-value is the probability of observing outcomes at least as rare as the sample data (i.e., equally or more unlikely).

2. **Compare the p-value with the significance level ($\alpha$)**:
- If p-value $\leq \alpha$ $\rightarrow$ Reject $H_0$.
- If p-value $> \alpha$ $\rightarrow$ Fail to reject $H_0$.

**Decision rule**:

If what we observe is rarer than the significance level we are willing to tolerate, then reject the null hypothesis.

$\Rightarrow$ Statistically significant evidence against $H_0$.
![[Pasted image 20241014145626.png|400]]


## Hypothesis testing: example
Imagine you are playing heads or tails and after 10 trials, you only won once. You start to wonder whether the coin is fair.

**Model:**  
$X \sim Binomial(n, p)$  
**Null hypothesis:** $H_0: p = 0.5$  
**Alternative:** $H_1: p > 0.5$  

![[Pasted image 20241014150420.png|800]]![[Pasted image 20241014150454.png|600]]

 p − 𝑣𝑎𝑙𝑢𝑒 < 𝛼 : reject 𝐻 : the coin is unlikely to be fair based on observed data
![[Pasted image 20241014151804.png|400]]

---
## Hypothesis testing: rejection regions

Another (equivalent) way to look at hypothesis testing is in terms of **rejection regions** instead of p-values.

We can define a test by specifying a **critical region (RR)**:

- The critical region, also called the rejection region, includes all rare outcomes under $H_0$.
- The probability of the critical region is a small value $\alpha$ under $H_0$, i.e., $P(X \in RR | H_0) \leq \alpha$.

**Decision rule**:
If we observe an outcome belonging to the rejection region, then we reject $H_0$.

**Note**:
Typically, we can express a critical region in terms of a critical value, $k$:

$$ P(X \in RR | H_0) \leq \alpha \rightarrow P(X > k | H_0) \leq \alpha $$

- $k$ separates $\Omega \setminus RR | H_0$ from $RR$.
- It is not necessarily $X > k$! It can be $X < k$ depending on the use case.



![[Pasted image 20241014154114.png|300]]


Here is the text from **Slide 20** extracted exactly as per your specifications:


In general, there are many (potentially infinite) critical regions with the same significance level.

**How do we choose an appropriate rejection region?**
- The choice needs to take into account $H_0$ and $H_1$.
- **Place $RR_\alpha$ where outcomes are rare under $H_0$ but "common" under $H_1$:**
  - i.e., $P(X \in RR | H_0)$ is low but $P(X \in RR | H_1)$ is high.
  - This means $RR$ is in the tails of $f(X | H_0)$, but not for $f(X | H_1)$.


![[Pasted image 20241014154253.png|400]]


#### Rejection regions: example
Imagine you are testing a simple null hypothesis, $H_0: \theta = \theta_0$. The probability distribution of the data under $H_0$ is reported in the plot below. Graphically indicate the rejection region ($RR$) for each of the following alternative hypothesis scenarios:

- **$H_1$: $\theta = \theta_1 > \theta_0$**
	- This suggests rare outcomes under $H_0$, but “common” under $H_1$ are values in the right tail.

- **$H_2$: $\theta < \theta_0$**
	- Just the opposite situation $\rightarrow$ left tail.

- **And for $H_3$: $\theta \neq \theta_0$?**
	- $RR$ includes both tails, halving its size at each side to ensure a global significance level of $\alpha$.

$\Rightarrow$ $H_1$ and $H_2$ are called **one-sided alternatives**, while $H_3$ is called a **two-sided alternative**.
![[Pasted image 20241014155222.png|600]]
