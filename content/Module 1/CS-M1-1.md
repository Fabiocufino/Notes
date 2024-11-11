
## Foundamentals of Probability

### Introduction: what is probability?
- Branch of mathematics that deals with the likelihood or chance of events occurring
- Framework for reasoning about uncertainty and randomness
- Measure of how likely something is to happen, expressed as a number between 0 and 1
    - 0 → impossible, never happen
    - 1 → certain, definitely happen
- e.g. how likely is that the sun will rise tomorrow? how likely I’ll get a 6 rolling a dice?

### Do we really need probability in physics?

Several areas where this is useful:
- Handle measurement error/noise in experimental data
    - e.g. detector readouts in high-energy physics experiments
- Statistical mechanics: model collective instead of individual behavior
    - e.g. Maxwell-Boltzmann distribution for particle speed in gas
- Chaotic and complex systems
    - e.g. weather forecasts: range of possibilities varying initial conditions rather than deterministic prediction
- Quantum mechanics
    - e.g. inherent randomness of particles behavior, wave function, Heisenberg uncertainty principle
    - nature microscopic behavior, not just tool for measuring uncertainty!

### Definition

We have multiple definitions of what probability is:

1. Axiomatic, Kolmogorov around 1933 – 3 axioms as general rules for computing probabilities
2. Classical (Combinatorial), Laplace around 18th century
3. Frequentist (empirical), von Mises around 20th century
4. Subjective, De Finetti around 20th century – degree of confidence an individual has in the occurrence of an event

---

### Example: flipping a coin

![[Pasted image 20241018101904.png|700]]

### 1. Axiomatic definition

The axiomatic definition provides some rules to handle probability. From these we can derive further properties:

![[Pasted image 20241001104416.png|700]]

 **Axiomatic definition – limitations**

Although elegant and useful, it poses a few practical and philosophical issues:
- Does not define the probability of individual events
- Requires a clearly defined sample space, not always the case; e.g. economics, human behavior, …
- Not applicable to non-measurable sets
- Build upon objective probability, not always practical; e.g. personal belief: P(«bus getting on time»)

---

###### **Exercise**: Show that
$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$  (Hint: disjoint sets and 3rd axiom)

---

### 2. Classical (combinatorial) definition

Classical definition turns out useful when:
- We can enumerate possible outcomes
- Outcomes are equiprobable

--> e.g. we have a bag with 3 blue balls and 2 red ones. What is the probability of drawing 2 blue balls at once?

Using axiomatic definition is impractical here, as we do not know the probability of drawing a ball of a given color.

- We can use the classic definition instead!
    $$P(E) = \frac{\text{Number of favorable outcomes}}{\text{Number of possible outcomes}}$$

---

##### Elements of combinatorics

How to count and arrange n objects. Two key specs: order, repetitions

**Permutations** (order important)
- w/o repetition: $$n!$$
- w/ repetition: $$\frac{n!}{k_1! k_2! \dots k_r!}$$

**Dispositions** (order important)
- w/o repetition: $$\frac{n!}{(n-k)!}$$
- w/ repetition: $$n^k$$

**Combinations** (order not important)
- w/o repetition: 
    $$C_{n,k} = \frac{n!}{k!(n-k)!}$$
- w/ repetition:
    $$C'_{n,k} = \frac{(n+k-1)!}{k!(n-1)!}$$


Back to classical definition.. and the question:
- e.g. we have a bag with 3 blue balls and 2 red ones. What is the probability of drawing 2 blue balls at once?

Using the axiomatic definition is impractical here, as we do not know the probability of drawing a ball of a given color.

We can use the classic definition instead! Assuming each ball is equiprobable, we just need:
- How many ways of extracting 2 balls out of 5?
- How many of them contain 2 blue balls?
$$
P(\text{"2 blue balls"}) = \frac{C_{3,2}}{C_{5,2}} = \frac{\binom{3}{2}}{\binom{5}{2}} = \frac{3!}{2!1!} \cdot \frac{5!}{2!3!} = \frac{3}{10}
$$

**Classic definition – limitations**

Although intuitive, it poses a few practical and philosophical issues:
- Tautological, self-referential: what does it mean by "equiprobable"?
- What if events are not equally likely? For example, \( P(\text{"gold medal at Olympics final"}) \)
- Enumerating outcomes is not always feasible or even possible! (e.g. infinite sets)
- Does not apply to empirical data (e.g. \( P(\text{"taller than 1.80m"}) \)


**Exercise**

Imagine rolling a dice:
- Compute \( P(6) \)
- Compute \( P(\text{"even"}) \) and \( P(\text{"odd"}) \)
- Compute \( P(n < 3) \)

Imagine rolling two dice:
- Compute \( P(n < 3) \)


### 3. Frequentist definition
![[Pasted image 20241001105743.png|500]]
Frequentist definition assumes:
- Objective probabilities exist
- We can collect data about a phenomenon and count how many times an event of interest is observed
- As the number of trials (data) grows, the relative frequency approaches the true probability of the event
- Experiments can be repeated under identical conditions
    - e.g. What is the probability of an atom decaying in the next year?
        - Take many atoms and put them under same initial conditions
        - Observe them for a year
        - Count how many of them have decayed
    - As the number of atoms grows, we have: $$\lim_{n \to \infty} P(\text{decay in 1 year})$$$$P(E) = \lim_{n \to \infty} \frac{\text{Number of times event E occurs}}{\text{Number of trials}}$$


**Frequentist definition limitations**
• Experiments must be repeated under identical conditions, not always possible; e.g. difficult to control external factors
• Requires large number of trial for accurate approximation
• Consequently bad-suited for rare phenomenon, especially one-off events


### 4. Subjective definition

This definition is based on a quantification of the degree of belief. For this, we use a fair bet:

«P(A) = fraction of payout, Y, one would bet on A in order not to neither win nor lose money»

- Based on personal belief and knowledge
- Useful for unique, non-repeatable events; e.g. political election, betting, …
- Only option in many practical situations

- e.g. What is the probability that tomorrow will rain?
    - Weather forecasts report good weather
    - Today is sunny and warm
    - I have outdoor activities planned for tomorrow
-- Pessimistic: It would be fair to bet 10€ to win 100€ as, for me, rain is 9 times more likely: P(A) = 10/100
-- Optimistic: It would be fair to bet 99€ to win 100€ as, for me, sun is 99 times more likely: P(A) = 99/100


**Subjective definition limitations**

• Still hard to quantify, opinions change
• Naturally variable, personal

---

### Conditional probability & independence

Two fundamental concepts when operating on probabilities are conditional probability and independence:
- **Conditional probability** is the probability of an event occurring based on a given prior knowledge.  I.E. $P(A|B)$$ is the probability of A happening given that we know B has already happened.![[Pasted image 20241001110012.png|700]]
    - **Example:** Rolling a number lower than 3 given that the outcome is even:  
        $$P(n < 3 | n \text{ even}) = \frac{P(n < 3 \cap n \text{ even})}{P(n \text{ even})} = \frac{\frac{1}{6}}{\frac{3}{6}} = \frac{1}{3}$$

- **Independence:** Two events are independent if knowing something about one tells us nothing about the other.  
    - Mathematically: $$A, B \text{ independent } \implies P(A \cap B) = P(A)P(B)$$  
    - Note that if A, B are independent, $P(A|B) = P(A)$
    - Important: independent disjoint $P(A \cap B) = \emptyset$
