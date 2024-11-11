
# Random variables

**Outline**

- Random variables
- Examples of univariate distributions
- Moments and characteristic function

---

**How to describe random phenomena?**

---

## **Random variables**

A random variable is a mathematical object that maps a numerical value to each outcome of a random process:

- A R.V. $X$ is composed of a probability triplet:
  - Sample space, $S$: set of all possible outcomes
  - Event space, $E$: set of all events, i.e., all subsets of $S$
  - Measurable function, $P$: maps each event to its probability

- Example:
  - R.V. $X$ represents the random process of rolling dice
  - Sample space: $S = \{1, 2, 3, 4, 5, 6\}$
  - Event space: $E = \{\{1\}, \{2\}, ..., \{1, 2\}, \{1,3\}, ...\}$
  - Probability function, $P: F \to \mathbb{R}$ that associates to each event its probability $\rightarrow$ distribution

**Notation**  
![[Pasted image 20241001114440.png|600]]

Two types of R.V.s depending on the sample space:
![[Pasted image 20241001114527.png|700]]
###  **Cumulative distribution properties**

The cumulative distribution has several important properties:

- Non-decreasing
- Right-continuous
  - Step function for discrete R.V.s
  - May be a step function also in the continuous case

$$\lim_{x \to -\infty} F(x) = 0, \lim_{x \to \infty} F(x) = 1$$
![[Pasted image 20241001114546.png|400]]

For continuous R.V.s, given constants $a,b$ such that $a < b$:

$$F(b) - F(a) = P(a < X \leq b) = \int_a^b f(x) dx$$

**Note**: in practice, we can use $<$ and $\leq$ indistinguishably, as adding a point to the integral does not affect the result.  
A similar result holds for discrete R.V.s, but more attention needs to be paid to inequalities.
![[Pasted image 20241001114602.png|400]]


**Examples of DISCRETE random variable distributions**
![[Pasted image 20241001114613.png|500]]

**Examples of CONTINUOUS random variable distributions**
![[Pasted image 20241001114637.png|500]]

---
---
## **How to summarize a distribution?**

- Distributions enclose all information about a random variable.
- However, sometimes we do not need all that information.
- Can we retrieve some synthetic measure of relevant features?
  - Central tendency
  - Spread
  - Symmetry
  - Behavior in the tails
  - Also useful for quantitative comparisons

---
### Summary statistics: Central tendency and spread

Two useful properties often used are:

- **Expected value,** $\mu$:
  - Discrete:  
    $$E[X] = \sum x \cdot p(x)$$
  - Continuous:  
    $$E[x] = \int_{-\infty}^{\infty} x f(x) dx$$
  - $E$ is a linear operator called **expectation**.
    → weighted sum (or integral), with probability (or probability density) as weight  
    → measures central tendency of the distribution

- **Variance,** $\sigma^2$:
  - Discrete:  
    $$V[X] = \sum (x - \mu)^2 \cdot p(x)$$
  - Continuous:  
    $$V[X] = \int_{-\infty}^{\infty} (x - \mu)^2 f(x) dx$$
  - **Variance** measures spread around the expectation.
####  **Expectation operator properties**

The expectation is a linear operator, which implies several properties:

- $E[aX] = a E[X]$ where $a$ is a constant value.
- $E[X + Y] = E[X] + E[Y]$
	  - This is true irrespectively of whether $X,Y$ are independent.
	
- If $X \perp Y$, then  $E[XY] = E[X] E[Y]$
  - However, $E[XY] = E[X] E[Y] \not\Rightarrow X \perp Y$
  
- $V[X] = E[X^2] - (E[X])^2$

![[Pasted image 20241001115115.png|700]]
with the red highlight being constant, so replaceable with $\mu$.


---

### Moments of a distribution:

In general, we can look at moments as summary statistics. For a continuous R.V. $X$, the moment of order $m$ about $c$ is defined as:
$$\mu_m = E[(X - c)^m] \equiv \int_{-\infty}^{\infty} (x - c)^m f(x) dx$$  
  where $c$ is a constant value.
- For a discrete R.V. $X$, just replace the integral with a sum and the pdf with a pmf.

- **Raw (initial) moments** → $c = 0$:  
  $$\mu_m = E[X^m]$$

  - The order $1$ (m = 1) moment is the expected value:  
    $$\mu = E[X]$$  
    → central tendency of a distribution

- **Central moments** → $c = \mu$:  
  $$\mu_m = E[(X - \mu)^m]$$

  - The order $2$ (m = 2) moment is the variance:  
    $$\sigma^2 = V[X]$$  
    → spread around $\mu$

- **Standardized moments** → $c = \mu$:  
  $$\mu_m = \frac{E[(X - \mu)^m]}{\sigma^m}$$

  - The order $3$ (m = 3) moment is the skewness → measures lopsidedness.
  - The order $4$ (m = 4) moment is the kurtosis → measures tail heaviness.

---

**Exercise**

Consider a continuous random variable $X$ and two constants, $\alpha, \beta$. Starting from the definition of expected value, show that:

- $E[\alpha X + \beta] = \alpha E[X] + \beta$
- $V[\alpha X + \beta] = \alpha^2 V[X]$

---

### Characteristic functions

The characteristic function $\phi_X(k)$ of an r.v. $X$ is defined as the expectation value of $e^{ikX}$ (similar to the Fourier transform of $X$):

$$\phi_X(k) = E[e^{ikX}] = \int_{-\infty}^{\infty} e^{ikx} f(x) dx$$

- Useful for finding moments and deriving properties of sums of R.V.s.
- For well-behaved cases (true in practice), the characteristic function is equivalent to the pdf and vice versa, i.e., given one, you can, in principle, find the other.

---

**Moments from the characteristic function**

Given a random variable $Z$, we can derive the moments from its characteristic function. To find the m-th moment:
![[Pasted image 20241001115417.png|700]]

→ From the characteristic function, we can derive moments even without an explicit formula for the pdf.

---

**Exercise**

- $X$ and $Y$ are two independent random variables, and $Z = X + Y$ is derived as their sum. Prove that the characteristic function $\phi_Z(k)$ is the product $\phi_Z(k) = \phi_X(k)\phi_Y(k)$.
- Does this hold for a general linear combination of independent random variables?  
  i.e., if $Z = \sum a_j X_j$, then $\phi_Z(k) = \prod \phi_{X_j}(a_j k)$.