# Proton structure and proton-proton scattering

## Proton structure
The proton, once thought elementary, is now known as a composite particle made up of **partons**. Initially, a simple model suggested two up-quarks and one down-quark. However, Quantum Chromodynamics (QCD) revealed a more complex reality: valence and sea quarks, along with gluons. Ongoing research delves into the substructure of quarks, advancing our understanding of particle physics.

How did we understand that? 

### Elastic electron-proton scattering
Electron-proton scattering offers a valuable method to probe the proton's structure.

By employing a point-like charge (the electron) to interact with the proton or its constituents, we gain insights into the charge distribution and the proton's magnetic moment.

The important part is that the electron is point like. We know that. that's why we use it. 

In scenarios where the proton behaves as a point-like particle, especially when its mass is significantly larger than that of the electron, and it remains at rest, we can simplify the analysis. 

- No recoil effects
- No-relativistic scattering
- Proton is steady target

Described by the Rutherford formula.

The Rutherford formula for non-relativistic scattering, when considering a point-like proton with a mass much larger than that of the electron and neglecting recoil effects, is given by:

$$ \frac{d\sigma}{d\Omega} =  \frac{\alpha ^2}{16 T_e\sin^4(\theta/2)} $$

Where:
- $T_{\text{e}}$ is the kinetic energy of the incident particle, and
- $\theta$ is the scattering angle.

In relativistic scattering, taking into account 
- Spin effects 
- No proton recoil

the process is described by Mott scattering. The differential cross-section for Mott scattering is given by:

$$ \frac{d\sigma}{d\Omega} =  \frac{\alpha ^2}{4 E_e^2 \sin^4(\theta/2)} \cos^2(\theta/2)  $$


To actually have a better approximation of what is the actual phenomenon we need to include 
- proton’s magnetic moment 
- consider recoil of proton for large electron energies. 

Start from a QED graph for scattering of point-like particles instead of Mott scattering, e.g. eμ scattering:
$$
\frac{\mathrm{d} \sigma}{\mathrm{d} \Omega}=\left(\frac{\alpha^2}{4 E^2 \sin ^4 \frac{\theta}{2}}\right) \frac{E^{\prime}}{E}\left[\cos ^2 \frac{\theta}{2}-\frac{q}{2 m^2} \sin ^2 \frac{\theta}{2}\right]
$$

where:
- m is the muon mass,
- E and E′ are the electron’s energy before and after scattering
- $𝑄^2$ = −$𝑞^2$

For $𝑄^2$ ≪ $𝑚_𝑝^2$, the formula reduces to the Mott scattering formula.

**Adding form factors**

In the realm of nuclear physics, we often utilize form factors to describe the charge distribution of a target. Analogously, in particle physics, we can employ a similar concept when considering the elastic scattering of spin-1/2 electrons on a spin-less target with a charge distribution.

In this scenario, the differential cross-section for elastic scattering is expressed as the Mott cross-section multiplied by the square of a form factor. 

This form factor encapsulates -> Spatial Distribution of **charge** within the target.

Mathematically, this relationship is represented as:

$$ \frac{d\sigma}{d\Omega} = \left( \text{Mott cross-section} \right) \times \left| \text{Form factor (q)} \right|^2 $$

where 𝑞 is the momentum transfer between the electron and the proton. 

The form factor F is the Fourier transform of the charge distribution 𝜌(𝑥):
$$ F(q) = \int d^3x \rho(x) e^{i q x} $$
charge distributions:

![[Pasted image 20240511154222.png|center|500]]


Using the same concept and considering the most general Lorentz invariant form of electron-proton scattering for single-photon exchange gives the **Rosenbluth formula**:

![[Pasted image 20240511154415.png|center|400]]


The terms in blue are contributing because the proton actually has a size and it's not like an electron.
Of course the terms G are liked with the fact that the proton has a spatial distibution and because of this it will have a charge and momentum sitribution as well.

P.S. For now we keep separate the charge an the momentum distribution of the proton, but maybe we are wrong.. it's a general model, let's see where it will bring us.
![[Pasted image 20240906203951.png|center|400]]


$𝐺𝐸(𝑄^2)$ and $𝐺𝑀(𝑄^2)$ are approximately:
$$
\begin{aligned}
G_E\left(Q^2\right) & \approx G_E\left(\vec{p}^2\right)=\int \mathrm{d}^3 \vec{x} \rho(\vec{x}) e^{i \vec{q} \vec{x}} \\
G_M\left(Q^2\right) & \approx G_M\left(\vec{p}^2\right)=\int \mathrm{d}^3 \vec{x} \mu(\vec{x}) e^{i \vec{q} \vec{x}}
\end{aligned}
$$
where $\rho(\vec{x})$ and $\mu(\vec{x})$ are the charge and magnetic-moment distributions.

The normalizations are chosen such that they reflect the total charge and the anomalous magnetic moment of the proton:
$$
\begin{aligned}
G_E(0) & =\int \mathrm{d}^3 \vec{x} \rho(\vec{x})=1 \\
G_M(0) & =\int \mathrm{d}^3 \vec{x} \mu(\vec{x})=+2.79
\end{aligned}
$$

The form factors $G_E$ and $G_M$ are independently measurable.
When considering small values of $Q^2$, where $\tau \ll 1$, the term associated with $G_E$ predominates. Conversely, for larger $Q^2$ values, the term linked to $G_M$ dominates.

![[Pasted image 20240511160539.png|center|200]]

This observation leads to the conclusion that experimental data conform to a "dipole" distribution pattern. At lower energies, the data align with expectations for a point-like proton, suggesting a compact structure. However, at higher energies, both form factors become significant, indicating that the proton behaves as an extended object.

**It's crucial to note that while elastic scattering experiments reveal the proton's extended nature, they do not provide evidence for its composite nature with distinct "partons".***


### Inelastic electron-proton scattering

In inelastic scattering, the proton can be excited by a photon, leading to the production of additional particles, such as $e p \rightarrow e \Delta^+ \rightarrow e p \pi$.

When the momentum transfer is small, this process is permissible.

However, for large momentum transfers, the *proton may breaks apart*. To accommodate inelastic scattering, it's necessary to extend the scattering formulas.

Introducing more general **structure functions**, denoted as $W_{1/2}$, these functions become dependent on two independent Lorentz scalar variables.
- $Q^2=-q^2$
- Invariant mass of proton final state $W^2=\left(p_p+q\right)^2$.
	- $p_p$ is the proton four-momentum.
- Bjorken $x$ or "elasticity": $x=\frac{Q^2}{2 p_p \cdot q}$
	- Can take values between 0 and 1 -> 1 means elastic scattering.
- Inelasticity $y: \; y=\frac{p_p \cdot q}{p_p \cdot p_e}$. Can take values between 0 and 1.
- Energy lost to the electron: $\nu=\frac{p_p \cdot q}{m_p}$.

These variables are not independent, e.g. $x=\frac{Q^2}{2 m_p \nu}$.

This generalization allows for a more comprehensive description of scattering processes, including both elastic and inelastic scattering scenarios.
![[Pasted image 20240511160855.png|center|500]]


In this graph we can see resonances. This means that something is actually happening inside the proton.

-> Something that will not happen if you consider just elastic scattering.

The differential cross section then becomes:
$$
\frac{\mathrm{d}^2 \sigma}{\mathrm{d} E^{\prime} \mathrm{d} \Omega}=\left(\frac{\alpha^2}{4 E^2 \sin ^4 \frac{\theta}{2}}\right)\left[W_2\left(\nu, Q^2\right) \cos \frac{\theta}{2}+2 W_1\left(\nu, Q^2\right) \sin ^2 \frac{\theta}{2}\right]
$$
If the proton is made up of pointlike particles, *named partons by Feynman in the late 60ies,* then for high energies (large $Q^2$ ), it would be intuitive that the **inelastic** scattering of a proton can be viewed as **elastic** scattering off these partons. 

---
Explanation of the last sentence:
- The high energy provides enough resolution to "see" these partons individually. (steady)
- The scattering is effectively elastic at the parton level, as the photon interacts directly with a single parton, rather than with the proton as a whole.

Thus, inelastic scattering (which changes the state of the proton) at the level of the proton as a composite object can be understood as elastic scattering at the level of the partons.

---

The structure functions are thus
$$
\begin{aligned}
2 m W_1 & =\frac{Q^2}{2 m \nu} \delta\left(1-\frac{Q^2}{2 m \nu}\right) \\
\nu W_2 & =\delta\left(1-\frac{Q^2}{2 m \nu}\right),
\end{aligned}
$$
- where $m$ is now the mass of the quark


In inelastic electron-proton scattering, it's crucial to note that **the form factors now depend solely on the ratio of $Q^2$ to $\nu$**, rendering them no longer independent. 

### Bjorken scaling

This phenomenon is termed Bjorken scaling, where the structure functions of the proton exhibit no dependence on the momentum transfer $Q^2$
![[Pasted image 20240906211449.png|center|400]]

The exploration of proton structure using electrons is commonly referred to as deep inelastic scattering (DIS). 
Remarkably, experimental observations align with this scaling behavior, indicating that the proton's structure functions remain invariant with changes in $Q^2$. 

**The experimental finding shows indeed an independence from $𝑄^2$ and thus supports the hypothesis that the proton is composed of partons.**

-> In 1966, studies conducted at SLAC revealed that protons possess a substructure, marking a significant milestone in our understanding of particle physics. Nobel of course.

---
### The naive parton model

We have to introduce parton distribution functions $f_i = dP_i / dx$, that describe the probability that the parton i carries the fraction x of the proton's momentum. 

-> x is the fraction of the momentum, f(x) is the probability that a parton taken out randomly carries that part of momentum.

- All momentum functions have to add up to 1
- The structure functions can now be written in terms of x (as they are independent of $𝑄^2$)
- All the structure functions are replaced with this distribution functions 
$$
\begin{aligned}
& v W_2\left(v, Q^2\right) \rightarrow F_2(x)=\sum_i e_i^2 x f_i(x) \\
& m_p W_1\left(v, Q^2\right) \rightarrow F_1(x)=\frac{1}{2 x} F_2(x)
\end{aligned}
$$

In the naïve parton model, it's important to recognize that photon scattering occurs incoherently off the quarks. Here, probabilities are summed, not amplitudes, **indicating that the quarks inside the proton do not interact** with each other directly. **This suggests that the timescale for, say, an electron to traverse the proton is much shorter than the timescale of parton-parton interactions**. Consequently, the set of partons behaves as a static target for the electron.

A notable outcome of this model is the Callan-Gross relation, expressed as $2x F_1 = F_2$. This relationship stems from the fact that quarks possess a spin of 1/2. It's worth noting that this relation would differ for spinless quarks.

-> The $F_1$ and $F_2$ are related to each other, from the last formula. This comes back to the fact that the momentum and charge distributin are correlated! (see the last P.S.) Before we considered those are independent. (The idea relies on the fat that if we have particles with spin and charge we can say that somehow they are correlated)


This is what we have to expect from the distribution of the momentum with different idea of the proton.

![[Pasted image 20240511162238.png|center|400]]


Now let's decompose the structure functions into individual quark components yields
$$
\frac{1}{x} F_2^{e p}(x)=\left(\frac{2}{3}\right)^2\left[u^p(x)+\bar{u}^p(x)\right]+\left(\frac{1}{3}\right)^2\left[d^p(x)+\bar{d}^p(x)\right]+\left(\frac{2}{3}\right)^2\left[s^p(x)+\bar{s}^p(x)\right]
$$
- where $u^p$ is the probability distribution of the up quark inside the proton, etc.. Heavier quarks are neglected.
- Two contributions, valence quarks and sea quarks, so e.g.
$$
\begin{aligned}
& u^p(x)=u_{\text {val }}(x)+u_{\text {sea }}(x) \\
& s^p(x)=s_{\text {sea }}(x)
\end{aligned}
$$
---
![[Pasted image 20240511162354.png|center|400]]

Lets look at the picture: on the x there is the momentum and on the y the probability distribution of find that momentum for that parton.

We can see that on the x they are roughly at 1/3 but the $u$ distribution is 2 times higher than the $d$ distribution. 

The important part is that as we can see there is the parton "gluon" that is the most probabile thing with low momentum. 

Let's picture this: if the proton is a bag and you insert your hand in it the most probabile thing that you can grab is a low momentum $gluon$. The second most probabile thing that you can grab is the $u$ quark with 1/3 of the momentum.

---
The momentum fraction carried by quarks:
$$\int_0^1 dx x (u+\bar{u} + d + \bar{d} + s + \bar{s} ) = 1 - \epsilon_g $$
Experimentally, it's found that gluons carry a significant portion of the proton's momentum, with approximately 46% attributed to gluons. This implies that about half of the proton's momentum is carried by gluons.

The momentum fractions carried by up and down quarks, including antiquarks, are also measured:
-  $\epsilon_u = \int dx \, x(u(x) + \bar{u}(x)) = 0.36$ 
-  $\epsilon_d = \int dx \, x(d(x) + \bar{d}(x)) = 0.18$ 

Associating partons with quarks, which interact via the strong force, provides a framework for understanding proton structure within Quantum Chromodynamics (QCD).

However, **calculating Parton Distribution Functions (PDFs) from first principles faces challenges due to the large coupling constant** ($\alpha_s$) **at** **small momenta**, **where perturbation theory is inapplicable**.

While lattice calculations offer some insights, the true essence lies in the not-so-naive version of the parton model, derived from QCD. This version predicts and experimentally observes scaling violation.

Scaling violation arises from the assumption that quarks carry no transverse momentum in the infinite-momentum frame. In QCD, this assumption is violated due to the radiation of hard gluons from quarks, leading to logarithmic scaling variations in $\log(Q^2)$ .

Consequently, at large $Q^2$, there's an increase in gluon density and sea quarks at low $x$, resulting in a softening of the initial quark momentum.