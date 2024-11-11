
# Frequentist VS Subjective probability and Bayes’ Theorem

**Outline**

- Bayes’ Theorem
- Frequentist VS Bayesian statistics
- Examples

---

**How to update probability based on new evidence?**

---

## **Bayes’ theorem**

Bayes’ theorem provides a nice mechanism to update probability in light of new evidence:

- **Prior Probability,** $P(A)$: Initial belief before seeing evidence
- **Marginal Likelihood,** $P(B)$: Overall probability of the evidence
- **Likelihood,** $P(B|A)$: Probability of evidence given the hypothesis
- **Posterior Probability,** $P(A|B)$: Updated probability after observing evidence

Key Insights:
- Bayes’ Theorem updates beliefs based on new evidence  
  → resembles how we think
- It accounts for both the strength of the evidence and prior knowledge
- Note: prior belief/knowledge is not necessarily subjective probability


---

**Law of total probability**

Express the probability of an event $B$ in terms of a disjoint partition of the sample space $S$:

- Partition the sample space $S$ into disjoint subsets $E_i$ so that: $\cup E_i = S$
- Then a subset $B$ of $S$ can be expressed as:  
  $$B = B \cap S = B \cap \left( \bigcup E_i \right) = \bigcup \left( B \cap E_i \right)$$

![[Pasted image 20241018103243.png|300]]

- Leveraging conditional probability, we can re-write:  
![[Pasted image 20241001111741.png|600]]

Thus, Bayes’ theorem becomes:  
![[Pasted image 20241001111804.png|500]]

---

**Bayes’ theorem: example**

Suppose you want to know the probability of having a disease (A) given that you tested positive (B) for it:

- **Prior Probability** $(P(A) = P(\text{disease}))$: reflects our belief in the hypothesis before seeing any evidence, e.g., probability of the disease in the population, independent of the test
- **Likelihood** $(P(B|A) = P(\text{positive test} | \text{disease}))$: how probable the evidence is, assuming the hypothesis is true, i.e., the probability of testing positive, given that you actually have the disease
- **Marginal Likelihood** $(P(B) = P(\text{positive test}))$: probability of the evidence, i.e., overall probability of testing positive, including both correct and incorrect outcomes
  → law of total probability:  
  $$P(B) = P(B|A) \cdot P(A) + P(B| \neg A) \cdot P(\neg A)$$

- **Posterior Probability** $(P(A|B) = P(\text{disease} | \text{positive test}))$: updated probability after observing the evidence, i.e., probability of having the disease given the test result

---
Suppose you want to know the probability of having a disease (A) given that you tested positive (B) for it.

In practice:

- Suppose 1% of the population has the disease → $P(\text{disease}) = 0.01$
- Suppose the test has:
  - 90% sensitivity, i.e., it correctly identifies 90% of diseased testers → $P(\text{positive test} | \text{disease}) = 0.90$
  - 5% false positive rate, i.e., 5% of healthy people test positive → $P(\text{positive test} | \neg \text{disease}) = 0.05$

We can compute the posterior probability using Bayes' Theorem:

$$P(\text{disease} | \text{positive}) = \frac{P(\text{positive} | \text{disease}) P(\text{disease})}{P(\text{positive})}$$

Where $P(\text{positive})$ is the marginal likelihood:

$$P(\text{positive}) = P(\text{positive} | \text{disease}) P(\text{disease}) + P(\text{positive} | \neg \text{disease}) P(\neg \text{disease})$$
$$= 0.9 \cdot 0.01 + 0.05 \cdot 0.99 = 0.0585$$

Therefore:

$$P(\text{disease} | \text{positive}) = \frac{0.9 \cdot 0.01}{0.0585} = 0.1538 \approx 15\%$$

---

**Exercise**
![[Pasted image 20241001111926.png|500]]

---

## **What probability interpretation should we use?**

We have seen several definitions. Which one should we use?

- **Axiomatic definition**  
  - Rules to handle probability mathematically  
  - Always applies but not practical as we do not have $P(E_i)$

- **Classical**  
  - Useful when we can enumerate favorable and total outcomes  
  - Outcomes are equiprobable  
  - Not practical (or even unfeasible) with large/infinite sample spaces

- **Frequentist**  
  - Useful when we can perform repeated experiments under the same conditions  
  - Note: the more trials, the better the approximation!

- **Subjective**  
  - Allows dealing with one-off or rare events  
  - Based on personal belief and knowledge, therefore questionable  
    → **Bayes’ theorem makes it more rigorous and mathematically grounded**

---

## **What is statistics?**

Statistics is the science of collecting, analyzing, interpreting, presenting, and organizing data.

- Provides tools and methodologies to make sense of raw data and draw conclusions  
  → turns data into meaningful information

Key areas:
- **Descriptive Statistics:** summary and description of main features in data, e.g., mean, median, variance, standard deviation, coefficient of variation
- **Inferential Statistics:** goes beyond the data to make predictions or inferences about a larger population  
  → hypothesis testing, confidence intervals, and predictions based on observed data
- **Prediction:** What will happen given my model and the given data?
- **Inference:** What can I learn from the data about my model?

Statistics helps us answer questions like:
- Is a new drug effective in treating a disease?
- What is the average strength of a material under stress?
- Is the observed signal a new particle, or due to random background fluctuations?
![[Pasted image 20241001112002.png|700]]



### **Frequentist statistics**

Frequentist statistics is a framework that:

- Builds upon the frequentist definition of probability: long-run frequencies of events  
  → repeatable experiments

- The concept of probability is strictly tied to data:  
  - We cannot answer: "P(Higgs boson exists)?"
	  - $P(\text{Higgs boson exists})$ is either 0 or 1, we do not know which
  - We cannot answer: "P(\text{Higgs boson exists} | \text{data})?" either
  - What we can do: "P(\text{data} | \text{Higgs boson exists})?"

- Accepted theories/models are those most compatible with experimental data.

---

### **Bayesian statistics**

Bayesian statistics is a framework that:

- Builds upon the subjective definition of probability: degree of belief about a hypothesis
- Exploits Bayes' theorem to update our knowledge based on data:![[Pasted image 20241001113225.png|500]]
  → Actually measuring $P(\text{Higgs boson exists} | \text{data})$!
- However, the prior choice is subjective.

---

**Frequentist VS Bayesian statistics**

In summary, two alternative interpretations:

- Frequentist framework works on the likelihood of data given hypotheses: $P(\text{data} | H)$
- Bayesian approach works on prior update given data: $P(H | \text{data})$
- Frequentists take decisions based on the likelihood.
- Bayesians take decisions based on the posterior.

