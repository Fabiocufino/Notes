# Popular discrete and continuous distributions

**Outline**
- How can we use R.V.s in practice?
- Examples of R.V.s: Uniform, Bernoulli, Binomial, Poisson, Exponential, Gaussian, Student’s t, chi squar
- More examples of R.V.s: Beta, Gamma, Breit-Wigner (Cauchy), Landau

## How do we use R.V.s for modelling real processes?
### 1. Uniform distribution: discrete
Example: detecting alpha particles emitted from a radioactive sample, assuming isotropic emissions![[Pasted image 20241104153214.png|300]]

-  We divide the space into 8 equal regions, each covered by a detector  
	  → in which region will we observe the next emitted particle?

- Cannot tell in advance: random process!  
- Each region has the same probability since isotropic

Mathematical formulation:  

-  $X$ is R.V. describing the region where the alpha particle is emitted  
- Sample space, S: {1, 2, 3, 4, 5, 6, 7, 8}
  → **countable**, so X is a discrete R.V.  

• **pmf**, $p(X=x) = \frac{1}{8}$ for all $x \in S$
• **cdf**, $F(X \leq x)$ ?  
  – $\lim_{x \to -\infty} F(x) = 0$  
  – $\lim_{x \to \infty} F(x) = 1$  
  – $F(x) = \frac{x}{8}$, $x \in S$

**Expected value:** 
$$
E(X) = 1 \cdot \frac{1}{8} + 2 \cdot \frac{1}{8} + \dots + 8 \cdot \frac{1}{8} = 4.5
$$Variance:
$$V(X) = \sum (x - E(X))^2 \cdot p(x) = 5.25$$
- Is there easier way? Yes: $$𝑉[𝑋] = 𝐸[X^2] − (𝐸(𝑋))^2$$

In general, the **discrete Uniform** distribution describes random processes with a **finite** number of outcomes, all equiprobable (e.g., fair die roll, randomly pick one out of n elements)

So $X \sim \text{Uniform}(a, b)$  and the sample space, S: $[a, b] = \{a, a+1, a+2, \dots, a+n-1\}$ 
	  → n elements from a to b, spaced by 1 unit  

Then 
- pmf, $p(X=x) = \frac{1}{n}$ for all $x \in S$
- cdf, $F(X \leq x)$:  
	  – 0, $x < a$  
	  – $\frac{x - a + 1}{b - a + 1}$ for $a \leq x \leq b$  
	  – 1, $x > b$

• Expected value: $E(X) = \frac{a + b}{2}$
• Variance: $V(X) = \frac{(b - a + 1)^2 - 1}{12}$
• Characteristic function: $\varphi(k) = \frac{e^{ika} (1 - e^{ik(b - a + 1)})}{(b - a + 1)(1 - e^{ik})}$

### 2. Uniform distribution: continuous
![[Pasted image 20241104153912.png|300]]
Now imagine we have a single detector covering all the space around the sample

We have that $X \sim \text{Uniform}(a, b)$  and the sample space, S: $[a, b]$
  → this time is the continuous interval! e.g. $[0, 2\pi]$  
-  pdf, $f(X=x) = \frac{1}{b - a}$ for $a \leq x \leq b$; 0 otherwise  
-  cdf, $F(X \leq x)$:  
	  – 0, $x < a$  
	  – $\frac{x - a}{b - a}$ for $a \leq x \leq b$  
	  – 1, $x > b$

• Expected value: $E(X) = \frac{a + b}{2}$
• Variance: $V(X) = \frac{(b - a)^2}{12}$
• Characteristic function: $\varphi(k) = \frac{e^{ika} (1 - e^{ik(b - a)})}{(b - a)(1 - e^{ik})}$


Examples:

---
### Bernoulli distribution

**Example**: a single coin flip

- Only two possible outcomes: heads or tails  
  → denoted by 1, "success", and 0, "failure", respectively
- We denote by \( p \) the probability of success, e.g., \( p = 0.3 \)

**Mathematical formulation**:
X is R.V. describing the outcome of a coin flip, $X \sim \text{Bern}(p)$  with  Sample space, S: $\{0, 1\}$

- pmf, $p(X=x)$: 
	- $p$ for $x = 1$ 
	- $(1 - p) = q$ for $x = 0$ 
-  cdf, $F(X \leq x)$:
	-  0, $x < 0$ 
	-  $1 - p$ for $0 \leq x \leq 1$ 
	-  1, $x > 1$ 

-  Expected value: $E(X) = p \cdot 1 + (1 - p) \cdot 0 = p$ 
-  Variance: $V(X) = p - p^2 = p(1 - p)$ 
-  Characteristic function: $\varphi(k) = 1 - p + p e^{ik}$

**When to use**: Use the Bernoulli distribution for experiments with only two possible outcomes (e.g., success/failure) where each trial is independent and has a fixed probability of success.

---
#### Binomial distribution

**Example**: \( n \) coin flips

- \( n \) independent trials with binary outcomes: heads or tails
- Each flip has the same probability of success, \( p \)

**Mathematical formulation**:
X is R.V. describing the number of successes in n independent coin flips, $X \sim \text{Bin}(n, p)$ with  Sample space, S: $\{0, 1, \dots, n\}$ 
	→ countable, so X is a discrete R.V.

-  pmf, $p(X = k)$?
	-  Note: $X = \sum Y_i$, where $Y_i \sim \text{Bern}(p)$ 
	-  Recall that, if A ⊥ B then: $P(A \cap B) = P(A)P(B)$ 
	-  Recall that, if A, B disjoint: $P(A \cup B) = P(A) + P(B)$ 
	-  Can we derive $P(X = 0)$? And $P(X = 1)$? And $P(X = 2)$? And $P(X = k)$??

**Example**:  n  coin flips

- $n$ independent trials with binary outcomes: heads or tails
- Each flip has the same probability of success,  $p$

Mathematical formulation: 
X is R.V. describing the number of successes in n independent coin flips, $X \sim \text{Bin}(n, p)$ with Sample space, S: $\{0, 1, \dots, n\}$ 
	→ countable, so X is a discrete R.V. 

-  **pmf**, $$p(X = k) = \binom{n}{k} p^k (1 - p)^{n - k}$$
- **cdf**, regularized incomplete beta function
- Expexted value: $E[X] = np$
- Variance: $V[X] = np(1-p)$
- Characteristic Function: $\phi_X(k) = [1+p(e^{ik} - 1)]^n$ 

**When to use**: Use the Binomial distribution for a series of independent trials with two outcomes each (e.g., success/failure), where the probability of success is constant across trials, and you want to model the number of successes out of a fixed number of trials \( n \).

---
#### Poisson distribution

**Example**: Studying the decay of a radioactive isotope with a known average decay rate.

- We have a sample of radioactive material.
  - **Question**: How many decays will occur in the next minute?
- The process is random, so we cannot tell in advance.
- However, we know the average decay rate, denoted by \( \lambda \) (e.g., 5 decays per minute).

**Mathematical formulation**:
- $X$ is an R.V. representing the number of decays in the next minute, $X \sim \text{Poisson}(\lambda)$.
- Sample space, $S = \{0, 1, 2, 3, \dots\}$  
  - This is infinitely countable, so $X$ is a discrete R.V.

- **pmf**:  $$
  p(X = k) = \frac{\lambda^k e^{-\lambda}}{k!} \quad \text{for } k \in S
  $$
- **cdf**: Calculated using the regularized gamma function.
- **Characteristic function**:  
  $$
  \varphi(t) = e^{\lambda (e^{it} - 1)}
  $$

**When to use**: The Poisson distribution is suitable for modeling random counting processes where rare events occur at a known average rate (e.g., phone calls in an hour or accidents per day).



- In general, the Poisson distribution describes random counting processes of rare events at a known average rate.
- If $X \sim \text{Poisson}(\lambda)$, then:
  - $\lambda$ is the average count in the time interval, also called the **intensity**.

  - **Example**: Expressing \( \lambda \) as:
    $$
    \lambda = r \cdot t
    $$
    where $r$  is the event rate, and $t$ is the duration of the time interval.  
    Here, $\lambda$ remains constant over time.

- Sample space, $S = \mathbb{N} = \{0, 1, 2, \dots\}$
- **pmf**:
  $$
  p(X = k) = \frac{\lambda^k e^{-\lambda}}{k!} \quad \text{for } k \in S
  $$

- **Moments**:
  - **Expected value**: $E(X) = \lambda$.
  - **Variance**: $V(X) = \lambda$

---

#### Relationship between Poisson and Binomial distributions

Counting resembles repeated observations of whether an event has occurred (success) or not (failure).

- **Poisson**: models counting processes for rare events.
- **Binomial**: counts the number of successes in a series of independent trials.

To understand their relationship, consider:

- The Binomial distribution counts the number of successes in independent repeated trials:
  - \( p \): probability of success in a single trial.
  - \( n \): number of trials.


**Hint**: Try comparing the characteristic functions:

1. **Binomial characteristic function**:  
   $$
   \varphi_{\text{Bin}}(k) = \left[1 + p(e^{ik} - 1)\right]^n
   $$

2. **Poisson characteristic function**:  
   $$
   \varphi_{\text{Poisson}}(k) = e^{\lambda (e^{ik} - 1)}
   $$

By letting $p = \frac{\lambda}{n}$ and considering the limit as $n \to \infty$, the Binomial distribution approaches the Poisson distribution.




---

#### Exponential Distribution
- **Example**: Studying the decay of a radioactive isotope, known average rate.
  - What is the waiting time between successive decays?
  - We know: 5 decays per minute, on average ($\lambda$).
- **Mathematical formulation**:
  - $X$ is R.V. for the waiting time between successive decays, $X \sim Exp(\lambda)$.
  - Sample space, $S$: $[0, \infty)$.
    - $\Rightarrow$ uncountable, so $X$ continuous R.V.
  - **pdf**, $p(X= x) = \lambda e^{-\lambda x}$, $x \geq 0$.
  - **cdf**, $F(X \leq x) = 1 - e^{-\lambda x}$, $x \geq 0$.
  - **Characteristic function**: $\phi(t) = \frac{\lambda}{\lambda - i t}$.
  - **Expected value**: $E(X) = \frac{1}{\lambda}$
  - **Variance**: $V(X) = \frac{1}{\lambda^2}$

  - **Moments**: $E(X) = \frac{1}{\lambda}$, $V(X) = \frac{1}{\lambda^2}$.
  - **Characteristic function**: $\phi(t) = \frac{\lambda}{\lambda - i t}$.

**In general, the Exponential distribution** describes the waiting time between two events (e.g., decay time, arrival time of next customer in a queue, time to next call at call center).


---
---
### Lack of Memory
In general, lack of memory indicates that "the waiting time for the occurrence of an event does not depend on how long has passed up to now".
  - $\Rightarrow$ past does not influence the future.
- **More formally**:
  $$P(T > t + \Delta t | T > t) = P(T > \Delta t)$$
- In practice, this means that "the probability that the event takes longer than $t + \Delta t$ given that we already waited $t$ is the same as the probability that it takes longer than $\Delta t$ starting from 0".
  - $\Rightarrow$ i.e., the fact that we already waited $t$, does not change the probability of waiting another $\Delta t$ time.
- **The exponential distribution has this property $\Rightarrow$ Exponential is memoryless**.
- Imagine $T \sim Exponential(\lambda)$, then:
  $$P(T > t + \Delta t | T > t) = \frac{P(T > t + \Delta t \cap T > t)}{P(T > t)} = \frac{P(T > t + \Delta t)}{P(T > t)} = \frac{e^{-\lambda (t + \Delta t)}}{e^{-\lambda t}} = e^{-\lambda \Delta t}$$
- Note that:
  $$P(T > t) = 1 - F(t) = 1 - (1 - e^{-\lambda t}) = e^{-\lambda t}$$

- **Example**: Imagine our survival time is exponentially distributed. Then:
  $$P(T > 90 + 5 | T > 90) = P(T > 5)$$
  - $\Rightarrow$ Probability that a 90-year-old person survives 5 years is the same as a newborn!

---

#### Poisson and Exponential Relationship

**Poisson and Exponential distributions** model different aspects of the same process.

- On one side: counting event occurred in $\Delta t \rightarrow$ Poisson.
- On the other: waiting time between events $\rightarrow$ Exponential.
- So, are these R.V.s related?
- **Let** $T$ be the waiting time between two successive events.
- **Let** $N$ be the number of events occurring starting from $T = t$.
- What R.V. describes the waiting time $T$?
![[Pasted image 20241104162414.png|400]]

- We can work on the cdf:

$$F(t) = P(T \

leq t)$$

- Now, let us focus on the event $A = "$no event up to $T = \Delta t"$.
	- $P(A) = P(T > \Delta t) = 1 - F(\Delta t)$.
	- This also means that $N = 0$, so $P(A) = P(N = 0)$.
	- But $N$ is a counting process, with intensity $\lambda = r \Delta t$, so $N \sim Poisson(\lambda)$.
	- Hence:

$$P(A) = P(N = 0) = \frac{(\lambda \Delta t)^0}{0!} e^{-\lambda \Delta t} = e^{-\lambda \Delta t} = 1 - F(\Delta t)$$
	- $\Rightarrow F(\Delta t) = 1 - e^{-\lambda \Delta t} \Rightarrow$ Exponential cdf!
![[Pasted image 20241104162502.png|200]]
---

### Normal Distribution
- **Example**: Optical aberrations and lens defects.
  - We focus a beam of light through a lens that, due to imperfections, produces random deviations from the ideal focal point (\( \mu \)).
  - Deviations are symmetrical, i.e., they are equally likely to be to the left or right of the ideal focal point.
  - Small deviations are common, while large deviations are rare.
  - **Question**: What is the actual focal point’s position?
  
- **Mathematical Formulation**:
  - Let $X$  be the random variable for the position of the actual focal point.
  - **Sample Space**:  $S = (-\infty, \infty)$ , meaning $X$  is continuous.
  
- **Probability Density Function (pdf)**:
  - The distribution is bell-shaped and centered around \( \mu \), with the following pdf:
    $$
    f(X = x) = \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{(x - \mu)^2}{2 \sigma^2}}
    $$
    where $\mu$  is the mean, and $\sigma$  is the standard deviation.
  
- **Cumulative Distribution Function (cdf)**:
  - Starts at 0, gradually increases, accelerates at a point, then slowly approaches 1 as $x \rightarrow \infty$.
  - No closed-form solution, requires numerical computation.

- **Expected Value**:$$
  E(X) = \mu
  $$
- **Variance**:$$
  V(X) = \sigma^2
  $$
- **Characteristic Function**: $$  \phi(t) = e^{i \mu t - \frac{1}{2} \sigma^2 t^2}
  $$
###  General Properties of the Normal Distribution
- **Standard Normal Distribution**: Any normal distribution \( X \sim N(\mu, \sigma^2) \) can be transformed to the standard normal distribution \( Z \sim N(0, 1) \) by:
  $$
  Z = \frac{X - \mu}{\sigma}
  $$
  - This distribution has mean 0 and variance 1, useful for standard computations.
  
- **Probability Intervals**:
  - 68% of data falls within  $\pm 1\sigma$,
  - 95% within $\pm 2\sigma$,
  - 99.7% within $\pm 3\sigma$,
  - 99.99994266% within $\pm 5\sigma$ , setting a high threshold for new discoveries.

---

### Law of Large Numbers
- The **Law of Large Numbers** states that the average of independent and identically distributed (i.i.d.) random variables converges to the expected value as the sample size increases.

- Let \( $X_1, X_2, \dots, X_n$ \) be i.i.d. random variables:
  - $E(X_j) = \mu$ and $V(X_j) = \sigma^2$ for \( $j = 1, \dots, n$ \).
  - Define  $\bar{X}_n = \frac{1}{n} \sum_{j=1}^{n} X_j$ \).
  - As $n \to \infty$ , we have:
    $$
    \lim_{n \to \infty} E(\bar{X}_n) = \mu \quad \text{and} \quad \lim_{n \to \infty} V(\bar{X}_n) = 0
    $$
  - This implies $\bar{X}_n$ converges to $\mu$ as $n$ increases.

---
## Central Limit Theorem (CLT)
- The **Central Limit Theorem (CLT)** asserts that the sum or average of a large number of i.i.d. random variables follows a normal distribution, regardless of the original distribution.

#### Intuition
- A process influenced by many independent factors can be seen as the sum of those factors.
- With many factors, the distribution of the sum or average approaches a normal distribution.

#### Formal Statement
- Let $X_1, X_2, \dots, X_n$  be i.i.d. random variables with $E(X_j) = \mu$ and $V(X_j) = \sigma^2$.
  - Define $\bar{X}_n = \frac{1}{n} \sum_{j=1}^{n} X_j$.
  - The standardized form $Z = \frac{\bar{X}_n - \mu}{\sigma / \sqrt{n}}$ approaches $N(0,1)$ as $n \to \infty$.

![[Pasted image 20241105121351.png|500]]

---
### Chi-Squared Distribution 
- **Definition**: Chi-squared distribution describes a positive definite random variable, obtained as the sum of squared independent standard Gaussian.
  - **Applications**: Used in hypothesis testing and confidence intervals for variance.
  
- **Properties**:
  - $X \sim \chi^2(\nu)$, where $\nu$ is the degrees of freedom, representing the number of squared components.
  - **Sample Space**: $S = [0, \infty)$ 
- **Probability Density Function (pdf)**:
  $$
  f(X = x) = \frac{1}{2^{\nu / 2} \Gamma(\nu / 2)} x^{(\nu / 2) - 1} e^{-x / 2}
  $$

- **Expected Value**:$E(X) = \nu$
- **Variance**:$V(X) = 2\nu$

---

### t-Student Distribution
- **Definition**: Similar to the Gaussian distribution but with heavier tails, suitable for smaller sample sizes.
  - **Applications**: Used in hypothesis testing and confidence intervals for mean.
  
- **Properties**:
  - $X \sim t(\nu)$ , where $\nu$  is the degrees of freedom.
  - As $\nu \to \infty$ ,  $t$  approximates $N(0,1)$
  - **Sample Space**:  $S = (-\infty, \infty)$
  
- **Probability Density Function (pdf)**:
  $$
  f(X = x) = \frac{\Gamma\left(\frac{\nu + 1}{2}\right)}{\sqrt{\nu \pi} \, \Gamma\left(\frac{\nu}{2}\right)} \left(1 + \frac{x^2}{\nu}\right)^{-\frac{\nu + 1}{2}}
  $$

- **Expected Value**:  $E(X) = 0$ for $\nu > 1$ ; otherwise undefined.

- **Variance**: $V(X) = \frac{\nu}{\nu - 2}$  for $\nu > 2$ ; infinite for $1 < \nu \leq 2$ 
