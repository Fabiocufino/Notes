# Particle decay, hadronization and event generators

## Theoretical uncertainties

In particle physics, theoretical uncertainties are inherent due to the intricacies of calculations. While Leading Order (LO) and Next-to-Leading Order (NLO) computations can be automated, only select processes are ready for Next-to-Next-to-Leading Order (NNLO) precision. Higher-order calculations, beyond NNLO, remain feasible for a limited subset of processes due to their complexity. 

Perturbation theory necessitates renormalization, where the scale variation by factors of 0.5 and 2.0 offers insights into higher-order effects.

Achieving scale independence in predictions requires calculations to all orders.

Notable sources of **theoretical uncertainties**:
	• Renormalization scale
	• Factorization scale
	• PDF uncertainties

Understanding and mitigating these uncertainties are crucial for robust interpretations of experimental results in particle physics.

![[Pasted image 20240513182407.png|center|500]]

We can see that the dependence is going away if we increase the x axis.

---
---

## Particle Decay

Particle decay explain the transformation of initial state particles from hard-scattering processes into stable final-state particles.

These stable particles include charged leptons, neutrinos, and quarks, the latter constrained within hadrons due to the phenomenon of confinement. 

The transition from the 'parton level', where constituents are abstract entities, to the 'particle level' occurs through a series of well-defined steps:

1. **Parton Showering**: Initial quarks and gluons emit additional particles in a branching process known as parton showering. This leads to the creation of a cascade of secondary particles.

2. **Hadronization**: The showered partons undergo the process of hadronization, where they combine to form color-neutral hadrons, such as mesons and baryons, governed by the strong force.

3. **Prompt Decays**: The resulting hadrons and heavy leptons subsequently decay promptly into stable final-state particles. This includes charged leptons, neutrinos, quarks, gluons, and photons, which are observable in experimental detectors.

![[Pasted image 20240429084642.png|center|500]]


## The Model 

**Parton shower**
We start form e+e- that interact by exchanging a photon or Z and they decay into observable particles.

We can describe the shower with effective model:
	**Step 1**: Partons branch until they hit a lower energy threshold, e.g. t = 1 GeV^2
	(partons split or radiate additional partons (usually gluons) as they lose energy, continuing this process until they reach a certain low energy limit)
	![[Pasted image 20240429085110.png|center|500]]
	**Step 2**: hadronization sets in once the threshold if reached
	Theoretical description by a differential equation:
	![[Pasted image 20240429085456.png|center|400]]![[Pasted image 20240429085506.png|center|400]]
	First term: no branching, second term: last branching at t’

**Hadronization**
Hadronization, the process by which quarks and gluons combine to form color-neutral hadrons, it's a challenge in theoretical physics due to the non-perturbative nature of Quantum Chromodynamics (QCD) at low energies.

- Predicting hadronization directly using perturbative QCD is impractical due to the high coupling constant at small energies. Consequently, alternative methods are employed:

1. **Lattice QCD**: While challenging, lattice QCD provides a non-perturbative approach to study hadronization by simulating QCD on a discrete space-time lattice.

2. **Effective Models**: Effective models, such as **string** and **cluster** hadronization models, offer simplified descriptions of the process, allowing for practical calculations and insights into hadron formation.

3. **Local Parton-Hadron Duality**: This concept suggests that the momentum flow and quantum numbers at the hadron level mirror those at the parton level. Specifically, it proposes that a parton of a particular flavor results in a jet where the hadron with similar flavor content is closely aligned with the jet axis. This principle finds utility, particularly in the study of b-hadrons.

**String Hadronization**: This approach conceptualizes the interaction between partons by envisioning a "string" stretched between them, with a constant energy per unit length reminiscent of the QCD potential. At higher energies, the string undergoes tension-induced breakage, resulting in the formation of hadrons. Notably, the presence of hard gluons can introduce kinks in the string, influencing the hadronization process. 

- This framework finds practical application in event generators like Pythia.
![[Pasted image 20240513190022.png|center|300]]


**Cluster hadronization:** Cluster hadronization provides another lens through which to understand the complex process of hadron formation:
- gluons undergo transformation into mesons towards the end of a showering process. 
- Quarks are envisioned to condense into a colorless cluster. From this cluster, both mesons and baryons emerge. 
- This approach is employed in event generators like Herwig

![[Pasted image 20240513190136.png|center|500]]


## Fragmentation

Fragmentation explains the intricate process of transferring momentum from a parton to a hadron.

- **Measurement**: Fragmentation can be quantified through fragmentation functions, $𝐹^ℎ$(𝑥,𝑠), which represent the probability of finding a hadron with a momentum fraction 𝑥 in a scattering process.
	- Formula$$ F^h(x, s)=\frac{1}{\sigma} \frac{d \sigma}{d x}\left(e^{+} e^{-} \rightarrow h+X\right) $$ - $x=2^{E_h} / \sqrt{s} \approx 2^{p_h} / \sqrt{s}$ Momentum fraction of the Hadron
    
- **Hadron Multiplicity**: The average hadron multiplicity, denoted as ⟨$𝑛_ℎ$(𝑠)⟩, provides insight into the number of hadrons produced in a scattering process. $$ \left\langle n_h(s)\right\rangle=\int_0^1 \mathrm{~d} x F^h(x, s) $$
- **Factorization**: Fragmentation functions exhibit factorization, separating into a product of a process-dependent coefficient, 𝐶𝑖(𝑠,𝑧), and a universal decay function, $𝐷_𝑖^ℎ$(𝑥/𝑧,𝑠), representing the transition probability of a parton 𝑖 into a hadron ℎ with momentum fraction 𝑥𝑧.$$ F^h(x, s)=\sum_i \int_x^1 \frac{\mathrm{d} z}{z} C_i(s, z) D_i^h\left(\frac{x}{z}, s\right) $$
	- $c_i$: Process dependent
	- $D_i^h$: universal decay function parton $i \rightarrow$ hadron $h$
	
Here, 𝐶𝑖​ captures process-specific dynamics, while $𝐷𝑖^ℎ$ encapsulates universal aspects of parton-to-hadron transitions. This factorization scheme facilitates the separation of perturbative and non-perturbative physics, enhancing the predictive power of theoretical calculations in high-energy scattering processes. 

![[Pasted image 20240513190549.png|center|300]]

# Event generators
![[Pasted image 20240907222722.png|center|500]]


```audio-player

```

```audio-player
[[Recording 20240513184238.webm]]
```
```audio-player
![[Recording 20240429094522.webm]]
```
