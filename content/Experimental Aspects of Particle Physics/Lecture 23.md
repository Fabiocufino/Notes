# Statistical methods: limit setting

Two important classes of statistical inference performed in high energy physics
1. Estimating and constraining parameters  
2. Testing one or multiple hypotheses

#### **1. Hypothesis Testing**

- **Goal**: Determine if the dataset is consistent with a given hypothesis by comparing the observed data to expectations under the hypothesis.

#### **Discovery of a New Particle** (Null Hypothesis)
  - Disprove the hypothesis that only Standard Model (SM) physics exists.
  - The hypothesis tested is the null hypothesis (no new particle).

#### **Exclusion of a New Signal Model**
  - Disprove the hypothesis that the observed results are compatible with the background (SM physics) plus a potential new signal.
  - This process sets **upper limits** on the cross-section (production rate) of the hypothesized new signal.

- **Estimation**: 
  - Calculate how likely it is that the combined signal and background fluctuated downwards to produce the number of observed events. This is done by setting exclusion limits using confidence levels, typically at 95% C.L.

Aim of the lecture is how to read these plots and to understand how they were produced
![[Pasted image 20240906165023.png|center|500]]

In high energy physics, hypothesis testing is used to determine whether experimental data are consistent with a given hypothesis.

The **null hypothesis ($H_0$)** represents the current accepted model, typically the Standard Model (SM) 
- What we consider to be True

For example, $H_0$ could state that there is no new particle or that a particle is a muon. This is often referred to as the **"background-only" hypothesis**.

The **alternative hypothesis ($H_1$)** proposes new physics or deviations from the SM, such as the existence of a new particle. 
- It is often called the **"signal-plus-background" hypothesis**.

The main goal is to determine if the null hypothesis can be rejected based on the data. If the observed data are significantly different from the expectations under $H_0$, we may reject $H_0$ and support $H_1$. This is done by calculating test statistics like $p$-values or $\chi^2$ and comparing them to confidence levels, usually set at 95%. If the data are consistent with $H_0$, we simply fail to reject it, but this does not necessarily mean $H_0$ is proven true.

Proof by contradiction
- We typically reject hypothesis or fail to reject a hypothesis
- We only do this with a certain level of confidence

## Test Statistics in Hypothesis Testing

The **test statistic** $t(\mathbf{x})$ is a crucial quantity in hypothesis testing, where $\mathbf{x}$ represents a set of $N$ measurements $\mathbf{x} = (x_1, x_2, ..., x_N)$. It is a function that helps to distinguish between two hypotheses by quantifying the agreement of the observed data with a given hypothesis.

Examples of test statistics include:
- In **counting experiments**, the test statistic may simply be the number of observed events.
- In other cases, it could be based on distributions, such as **invariant mass**, **transverse momentum**, or machine learning algorithm outputs.
- Popular statistical tools include $\chi^2$ or **Kolmogorov-Smirnov** tests.

The **probability density function (pdf)** of the test statistic under hypothesis $H$, $g(t|H)$, must be known for hypothesis testing. This is distinct from the pdf $f(x|H)$ for an observable under hypothesis $H$, and is necessary for conducting the test.

## Example: Counting experiments

In a counting experiment, the **test statistic** is the **number of observed events** ($t = N$). The slide describes a scenario where:

- The **expected number of background events** is $\nu_b = 1.3$.
- The **expected number of signal events** is $\nu_s = 2$.
  
Thus, the **total expected number of events** under the **signal-plus-background hypothesis** is $\nu = \nu_b + \nu_s = 3.3$, while under the **background-only hypothesis**, it remains $\nu_b = 1.3$.

The **probability density function (pdf)** of the test statistic is modelled using a **Poisson distribution**, which is appropriate for counting experiments:
$$
 g(t = N|H(\nu)) = \frac{\nu^N e^{-\nu}}{N!}
$$
This describes the likelihood of observing $N$ events given an expected number $ \nu $ under a given hypothesis $H(\nu)$.

The plot shows the Poisson-distributed probability for observing different event counts $N$, comparing the background-only hypothesis (blue, $\nu = 1.3$) and the signal-plus-background hypothesis (red, $\nu = 3.3$).
![[Pasted image 20240906170040.png|center|500]]

## Critical Region in Hypothesis Testing

The **critical region** is defined to make decisions about whether to reject the null hypothesis $H_0$ based on the observed value of the test statistic $t$. 

- The **critical region** is the set of values for which $H_0$ is rejected. If the observed value falls into this region, we conclude that the data are incompatible with $H_0$ and reject it.

- The **acceptance region** is the opposite, where we fail to reject $H_0$ if the observed value falls within it. This is not equivalent to accepting $H_0$ as true.

- It's important to define these regions **before** observing the data to avoid bias.

---
![[Pasted image 20240906170625.png|center|400]]

The **probability of rejecting $H_0$ while $H_0$ is true** is given by the integral:
  $$
  \int_{t_c}^{\infty} g(t|H_0) dt = \alpha
  $$
  
  where $g(t|H_0)$ is the probability density function of the test statistic under $H_0$ and $\alpha$ is the **significance level** (the probability of a Type I error, rejecting $H_0$ when it's actually true).

The **probability of rejecting $H_1$ while $H_1$ is true** (a Type II error) is:
  $$
  \int_{-\infty}^{t_c} g(t|H_1) dt = \beta
  $$

  where $g(t|H_1)$ is the probability density under the alternative hypothesis $H_1$. The **power of the test** is $ 1 - \beta $, representing the probability of correctly rejecting $H_0$ when $H_1$ is true.

- If $H_0$ and $H_1$ are well separated, $\beta$ will be small, meaning the test is more powerful.

#### Counting Experiment Example:
- In the example, $t_c = 4$ corresponds to $\alpha = 0.046$.
- A typical significance level might be $\alpha = 0.05$, but this isn't always possible with discrete event counts.
- If 4 or more events are observed, $H_0$ is rejected.

---
## Errors in Hypothesis Testing

In hypothesis testing, two types of errors can occur:

1. **Type I Error**: 
   - The null hypothesis ($H_0$) is rejected when it is actually true. 
   - This occurs with probability $\alpha$, the **significance level**
   - Example: Declaring a new discovery when there is none.

2. **Type II Error**:
   - The null hypothesis is not rejected when it is false, meaning $H_1$ is true.
   - This occurs with probability $\beta$.
   - Example: Failing to detect a new particle when it actually exists.

Both types of error are linked to the choice of the **critical region**. When designing an experiment, one must balance the risk of these errors, deciding whether reducing Type I or Type II error is more important. 

In **discovery scenarios**, $\alpha$ must be very small (typically around $0.05$ or smaller) to minimize the risk of claiming new physics from statistical fluctuations. 

For **exclusion scenarios**, where one wants to exclude new models, an $\alpha$ of around 5% is commonly used. 

The table illustrates the outcomes and error types depending on the truth of $H_0$ or $H_1$
![[Pasted image 20240906171216.png|center|500]]

---
## Choice of Test Statistics and Neyman-Pearson Lemma

The **Neyman-Pearson lemma** provides an optimal method to distinguish between two hypotheses, $H_0$ and $H_1$. The test statistic is based on the **likelihood ratio**:

$$
Q \equiv \lambda = \frac{L(x|H_1)}{L(x|H_0)}
$$
- This choice of test statistic minimizes **Type II error** for a given **Type I error**, meaning it's optimal for deciding between two hypotheses.
- It always requires defining an alternative hypothesis ($H_1$) to compare against the null hypothesis ($H_0$).

In practical applications, we use the **log-likelihood ratio** as the test statistic:
$$
t = -2 \ln Q
$$

#### Discovery:
- This test determines whether the data is compatible with the **background-only hypothesis** ($H_0$).
- If no new particle or signal is present, the data should only reflect background processes.
- The goal is to calculate how strongly we can reject $H_0$ using metrics like the **p-value** and the **significance** of the observation.

#### Upper Limits:
- In cases where no excess of events is observed, we estimate **how small the signal could be** to still be consistent with the data.
- Here, $H_0$ represents the hypothesis that there is background + some signal.
- The aim is to determine how small the signal strength ($S$) can be and still reject $H_0$ at a **95% confidence level (C.L.)**.

## Likelihood Used for Test Statistics

The **likelihood** for the **signal-plus-background** hypothesis is expressed as:

$$
L(x|H_1) = \prod_{i=1}^{N_{\text{bin}}} \frac{(\mu s_i + b_i)^{n_i}}{n_i!} e^{-(\mu s_i + b_i)}
$$

- **Counting analysis**: $N_{\text{bin}} = 1$, meaning there is one bin in the histogram (typically used when we count events).
- **Unbinned shape analysis**: $N_{\text{bin}} = \infty$, leading to parametric estimation over the entire distribution.

- The parameter $\mu$ is the **signal strength**, which serves as a scaling factor in relation to the model prediction. This helps quantify the presence of new physics (or lack thereof) by modifying the expected number of signal events.

Incorporating **systematic uncertainties** (typically modelled as Gaussian or log-normal distributions), the likelihood becomes:

$$
L(x|H_1) = \prod_{i=1}^{N_{\text{bin}}} \frac{(\mu s_i + b_i)^{n_i}}{n_i!} e^{-(\mu s_i + b_i)} \prod_k f_k(\theta_k)
$$

Here, $f_k(\theta_k)$ accounts for systematic uncertainties on parameters $\theta_k$. These uncertainties modify the likelihood by incorporating the possible variation in key measurements or model predictions due to experimental limitations or theoretical approximations.



At the LHC, when dealing with **nuisance parameters** (In statistics, a **nuisance parameter** is any parameter which is unspecified but which must be accounted for in the hypothesis testing of the parameters which are of interest.) , the **profile likelihood ratio** is used to account for uncertainties. The test statistic is defined as:

$$
t_{\mu} = -2 \ln \lambda(\mu) = -2 \ln \left( \frac{L(\mu, \hat{\theta}(\mu))}{L(\hat{\mu}, \hat{\theta})} \right)
$$
Where:
- $\hat{\mu}$ and $\hat{\theta}$ maximize the likelihood function by allowing all parameters to vary freely.
- $\hat{\theta}(\mu)$ maximizes the likelihood function while keeping $\mu$ fixed at a specific value.

The ratio compares the likelihood with a fixed signal strength $\mu$ against the maximum likelihood. This process involves performing two fits for each $t_{\mu}$: one when all parameters are free and one where $\mu$ is fixed. In the plots, we see examples of this for $\mu = 0$.

These histograms show the event counts as a function of mass in different Higgs decay channels, where the blue and red shaded regions indicate the signal and background contributions.


![[Pasted image 20240906171534.png|center|400]]

## How to get the probability density functions?

To obtain probability density functions for test statistics like $t_0$ or $t_1$, two main methods are used:

1. **Pseudoexperiments**:
   - You create new "data" from a nominal Monte Carlo (MC) simulation by drawing random numbers.
   - Then, the model is fit twice as described earlier, calculating $t_{\mu}$ each time.
   - This process is repeated many times to build up a distribution for $g(t|H)$.
   - This method is computationally expensive, requiring several tens of thousands of pseudo-experiments.

2. **Asymptotic Limits**:
   - For large datasets, asymptotic methods are used to approximate the probability density functions.
   - The probability density is often described by analytical functions, such as $\chi^2$ distributions.

### **p-value**

The local **p-value** is defined as the probability of the background-only model producing a fluctuation at least as large as the one observed in the data:
$$
p_0 = \int_{t_{\text{obs}}}^{\infty} g(t|H_0) dt
$$

- This value reflects the likelihood that the observed data could occur under the null hypothesis.
- It is important to note that **p-value** is not the probability that the hypothesis is true. Instead, it tells us how extreme the observed data is under the assumption of the null hypothesis.
  
Additionally, **p-values** should not be confused with the significance level ($\alpha$) used earlier in hypothesis testing. $\alpha$ is a predefined constant, while **p-value** depends directly on the data.

In the case of the previous counting experiment, if the observed value is $t_{\text{obs}} = 5$, the **p-value** is $p_0 = 0.012$.


### **Significance Levels**

To express the **p-value** in terms of significance levels, we calculate the **Z-value**, which is derived from the inverse cumulative distribution function (CDF) of a standard normal distribution (Gaussian):

$$
Z = \Phi^{-1}(1 - p)
$$

where:

$$
\Phi^{-1}(1 - p) = \int_Z^{\infty} \frac{1}{\sqrt{2\pi}} e^{-\frac{1}{2}t^2} dt = p
$$

- **$\Phi^{-1}$** is the inverse of the cumulative distribution function of a unit Gaussian.
  
#### **Interpretation of Z-value:**
- A **significance of 3$\sigma$** corresponds to a **p-value** of $p_0 = 1.3 \cdot 10^{-3}$, which is considered **evidence** for new physics.
- A **significance of 5$\sigma$** corresponds to a **p-value** of $p_0 = 2.87 \cdot 10^{-7}$, which is necessary for the **discovery** of a new particle.
![[Pasted image 20240906172302.png|center|300]]
In counting experiments, we can approximate the **Z-value** as:

$$
Z = \frac{S}{\sqrt{S + B}}
$$
where:
- **S** is the number of signal events.
- **B** is the number of background events.

This Z-value approximation helps in determining the significance of observed data in high-energy physics experiments.


## Now the aim of this lecture 
![[Pasted image 20240906172416.png|center|400]]
This plot from the **ATLAS experiment (2011-2012)** shows the **local $p_0$-value** as a function of the Higgs boson mass $m_H$ in the range of 110 to 150 GeV. The $p_0$ value is the probability of the background-only hypothesis producing an excess as large as or larger than the observed signal, often referred to as the **local p-value**.

### Key features and how they did this:

#### 1. **Observed and Expected $p_0$ Values:**
   - The solid black line represents the **observed $p_0$ value**, which is the probability that the background fluctuations would mimic the observed signal. 
   - The dashed black line shows the **expected $p_0$ value** under the assumption of no signal (Standard Model Higgs). This is the median expectation for background fluctuations, assuming no actual Higgs boson signal is present.
   - The **blue shaded band** represents the expected fluctuations within a $1\sigma$ (68%) confidence interval.

#### 2. **P-value and $\sigma$ levels:**
   - The $p_0$ values are plotted on a logarithmic scale on the vertical axis. The red horizontal lines indicate different **$\sigma$ levels**, corresponding to the **significance of the observation**:
     - $1\sigma$ corresponds to a $p_0$ value of approximately 0.32.
     - $3\sigma$ corresponds to $p_0 \approx 1.3 \times 10^{-3}$, indicating **evidence** for a new particle.
     - $5\sigma$ corresponds to $p_0 \approx 2.87 \times 10^{-7}$, the level of **discovery** in particle physics.

#### 3. **Discovery Peak:**
   - There is a significant dip in the observed $p_0$ value around **$m_H \approx 125$ GeV**. This corresponds to the observed Higgs-like excess in the data, where the local $p_0$ value drops below $10^{-5}$, which translates to a significance of more than **5$\sigma$**. This is consistent with the discovery of the Higgs boson at around 125 GeV.

#### 4. **Methodology:**
   - **Likelihood Ratio Test**: This result comes from a **profile likelihood ratio test** comparing the **signal-plus-background** hypothesis to the **background-only** hypothesis. 
     - The test statistic used is $t_\mu = -2 \ln \lambda(\mu)$, where $\lambda(\mu)$ is the ratio of the likelihood for the signal-plus-background model to the background-only model.
     - They compute the $t_\mu$ for different assumed Higgs masses $m_H$ and determine the $p_0$ value by integrating the distribution of $t_\mu$ under the background-only hypothesis, as shown in the previous slides.

#### 6. **Significance Interpretation:**
   - The $p_0$ value around $125$ GeV indicates a deviation from the background-only hypothesis that reaches the **discovery threshold** of $5\sigma$, confirming the existence of the Higgs boson in this mass range.

Thus, this plot represents a crucial step in the **discovery of the Higgs boson** at ATLAS. By analyzing data at 7 and 8 TeV, they identified a significant excess around 125 GeV, leading to the observation of the Higgs boson.

Achtung: don't trust the sigma blindly! in 2011 OPERA found a neutrino faster than the speed of light and it wasn't true (technical issues)

---

Now we want to set **upper limits** on the signal strength parameter ($\mu$) of a given model

**Upper Limit Formula**
The $p_\mu$ value, which is the probability that the **signal-plus-background hypothesis** produces an excess as large as or larger than the observed one, is given by the integral:
$$
p_\mu = \int_{t_{\text{obs}}}^{\infty} f(t_\mu|H_\mu) dt_\mu
$$
This is often represented as **CL$_{s+b}$** and compares the observed result to the expected signal-plus-background distribution.

![[Pasted image 20240906173206.png|center|500]]

The plot shows two histograms:
- The **red histogram** represents the **signal-plus-background hypothesis** ($f(Q|s+b)$), which is the distribution of possible test statistic values assuming both signal and background are present.
- The **blue histogram** represents the **background-only hypothesis** ($f(Q|b)$), which is the distribution of test statistic values assuming only background is present.
- The observed test statistic value ($Q_{\text{obs}}$) is marked on the x-axis. 

### **Confidence Levels (CL)**
- The **$1-\text{CL}_b$ region** represents the probability that the **background-only hypothesis** could produce the observed data, while the **CL$_{s+b}$** represents the probability that the **signal-plus-background hypothesis** produces the observed data.
- If $p_\mu < \alpha$, where $\alpha$ is typically chosen as 5% or 10%, the signal-plus-background hypothesis is excluded at $1-\alpha$ confidence level (C.L.).

### **Setting Upper Limits**
The goal is to exclude the signal-plus-background hypothesis if $p_\mu$ is smaller than the chosen significance level $\alpha$. This is a way to set **upper limits** on the strength of the signal, ensuring that the observed data does not support a signal stronger than this limit.

--- 

## **Modified Frequentist Confidence Level CL$_s$** 
It is a method to set more conservative upper limits on signal strength and avoid excluding the signal hypothesis too easily in cases where the experiment is not sensitive enough. 


1. **If $N_{\text{obs}} < N_{\text{bkg}}$:**
   When the observed number of events is smaller than the expected number from background ($N_{\text{bkg}}$), the signal-plus-background hypothesis could be excluded even if the experiment is not very sensitive to the signal (due to small yields). 

2. **Definition of CL$_s$:**
   The formula for CL$_s$ is given by:
   $$
   \text{CL}_s = \frac{p_\mu}{1 - p_0} = \frac{\text{CL}_{s+b}}{\text{CL}_b}
   $$
   Where:
   - $p_\mu$ is the signal-plus-background hypothesis probability.
   - $p_0$ is the background-only hypothesis probability.
   - $\text{CL}_{s+b}$ is the confidence level for the signal-plus-background hypothesis.
   - $\text{CL}_b$ is the confidence level for the background-only hypothesis.

3. **Weaker Upper Limits:**
   The upper limits calculated using CL$_s$ are typically weaker than those derived from $p_\mu$ directly because CL$_s$ is larger than $p_\mu$. This reflects the fact that CL$_s$ provides a more conservative exclusion of the signal hypothesis.

4. **Exclusion Criterion:**
   If **CL$_s < 0.05$**, then the signal-plus-background hypothesis is excluded at **95% confidence level**. This is a typical threshold used in particle physics to claim that the signal hypothesis can be ruled out with strong certainty.

![[Pasted image 20240906173543.png|center|500]]
![[Pasted image 20240906173525.png|center|500]]

