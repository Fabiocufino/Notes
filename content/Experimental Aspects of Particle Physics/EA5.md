# Proton-proton scattering - part 2
## Collision events, cross sections and theory uncertainties

## The Optical Theorem

The forward amplitude for elastic scattering is connected to the total cross section:

$$ \sigma_{\text{total}} = \frac{16\pi}{1 + \rho^2} \left. \frac{d\sigma_{\text{el}}}{dt} \right|_{t=0}  $$

Here:
- $t$ represents the momentum transfer (a Mandelstam variable).
- $\rho$ stands for a model parameter.
- At small scattering angles, t can be approximated by: $-t = p\theta^2$, where $p$ is the momentum.

-> The strategy typically involves measuring elastic scattering at very small angles to leverage this theorem. This connection aids in understanding the total cross section based on the behavior of elastic scattering, providing insights into the underlying dynamics of particle interactions.


**Strategy: measure elastic scattering at (very) small angles so in the forward direction.**

 - By doing so, you can extract the differential cross-section  $\frac{d\sigma_{\text{el}}}{dt}$ at $t = 0$, which is crucial for determining the total cross-section $\sigma_{\text{tot}}$ using the **Optical Theorem**.

---
The ALFA (Absolute Luminosity for ATLAS) detector is specifically designed to measure elastic proton-proton scattering in the forward direction.

ALPHA is there: 
![[Pasted image 20240511173935.png|center|400]]

Here's how the ALFA detector works:

1. **Location**: The ALFA detector is positioned at a considerable distance from the main interaction point of the LHC, in the forward region of the ATLAS detector. Its location allows it to detect particles scattered at very small angles relative to the beam direction.

2. **Scintillating Fibers**: ALFA consists of arrays of scintillating fibers arranged in layers. These fibers are made of materials that emit light when charged particles pass through them. The position and intensity of the emitted light are used to reconstruct the trajectory of the passing particles.

3. **Roman Pot Detectors**: ALFA employs Roman Pot detectors to house the scintillating fiber arrays. These Roman Pots are movable devices that can be brought close to the beamline during data-taking and retracted to a safe distance during normal LHC operations. ![[Pasted image 20240423102920.png|center|400]]
   Requires special LHC runs with high β*>1000 m (large beam envelope results in small divergence and thus small t)

5. **Tracking and Reconstruction**: When protons scatter in the forward direction, they traverse through the scintillating fiber arrays, causing them to emit light. This light is then detected and converted into electronic signals, which are processed to determine the trajectory and momentum of the scattered protons.

6. **Measurements**: By analyzing the trajectories of scattered protons detected by ALFA, we can precisely measure the scattering angles and momentum transfers associated with elastic proton-proton collisions.

![[Pasted image 20240423102827.png|center|400]]


Plot of the measurements
![[Pasted image 20240423103429.png|center|400]]
**Problem**: 
You measure the cross section as a function of t (x axis), so low t is small angles and big t is bigger angles. So you want to measure as small angle as possible, obviously you don't measure the 0 because it will be still in the beam pipe.

How to solve an go further down?

**Small Beta Star**:
- The parameter $\beta^*$ is related to the **convergence** of the particle beam. A smaller $\beta^*$ results in a more focused beam, allowing for more precise measurements at smaller scattering angles. The plot shows how different values of $\beta^*$ correspond to different ranges of detectable angles (related to t).

If you have a small beta star you have a small covergency.
(The particles in the beam interact at different angles after the collision. The smaller the scattering angle, the closer the scattering is to being forward-directed, which is crucial for applying the **optical theorem**

With a smaller $\beta^*$ the beam is more focused, which minimizes the spread of the beam, allowing the detectors to reach closer to $t = 0$, meaning you can measure smaller angles. This is why smaller $\beta^*$ values are beneficial — they allow the detectors to access regions that are otherwise hidden within the beam, improving the precision of the measurement at small angles.)

---

Those measurements at higher |t|
![[Pasted image 20240907212038.png|center|400]]

- At small |t|, Coulomb (electromagnetic) scattering dominates with a $|t|^{-2}$ behavior.
- As |t| increases, the Coulomb and nuclear forces interfere, allowing the extraction of key parameters like total cross-section and luminosity. 
- In the intermediate |t| range, nuclear scattering dominates, following an exponential decay $\exp(-b|t|)$ 
- At very high |t| , perturbative QCD effects take over, with the cross-section decreasing steeply as $|t|^{-8}$ 



This is the result of Run1, the total cross section is 
![[Pasted image 20240423103817.png|center|600]]
with theory and experimental errors.

The plot gives an overview of the measurements that have been done in different experiments with cosmic rays, ATLAS etc
![[Pasted image 20240423103954.png|center|400]]

-- It's fun to see that cosmic rays experiments with high super high energy particles coming from somewhere in the universe with Peta energy do not provide better measurements that ATLAS because it's a FIXED TARGET experiment the cosmic rays, ATLAS not. --

---
We can measure yes, but we do not have clue of what is really happening. Let's see what's is going on. 

.
.
.
.
.
.
.


## Anatomy of a collision event

For $e^+ e^- \rightarrow \mu^+ \mu^-$ experiment the things are clean. We know the center of mass energy of this.

Let's see the situation for protons.

We know that the proton is made out of partons. Could happened that one partons of the right p and another one from the left p interact and since we remove color from the protons they have to reconnect with gluons, so there are gluons going from partons on the left p that are going to the right partons to reestablish colorless particles.

Let's see $p p \rightarrow \mu^+ \mu^-$

![[Pasted image 20240423104946.png|center|400]]


1. **Hard Scattering Process**: The primary interaction between two high-energy particles, such as protons, where constituents collide with significant momentum transfer, often resulting in the production of massive particles or jets.

2. **Underlying Event**: (something that does not originate from the Hard Scattering outgoing partons)
   - **Beam Remnant and Beam Halo**: Fragments of the colliding particles that escape interaction, often carrying small fractions of the total momentum.
   - **Multiparton Interactions**: Additional interactions between partons within the colliding protons, distinct from the primary hard scattering process.
   - **ISR/FSR (Initial/Final State Radiation)**: Emission of additional gluons or photons by the incoming or outgoing particles, contributing to the overall event topology.

3. **Non-Collision Background**:
   - **Beam-Induced Background**: Background signals arising from stray particles or interactions unrelated to the collision process, often originating from residual beam particles or interactions with beamline components.
   - **Cosmic Muons and Natural Radioactivity**: External particles such as cosmic rays or radioactive decay products that penetrate the detector volume, generating spurious signals.
   - **Detector Noise**: Intrinsic electronic or thermal fluctuations within the detector system, contributing to background signals.

4. **Pile-Up**:
   - **In-Time Pile-Up**: Additional collision events occurring within the same bunch crossing, leading to multiple overlapping signals in the detector.
   - **Out-of-Time Pile-Up**: Signals from collision events occurring in neighboring bunch crossings, overlapping with the current event and contributing to background noise.
   - In a bunch there are $10^{11}$ protons and every time 2 banchs collide there are 15/20 pp interactions. And sometime we "make a picture" of 4 collisions intead of one pp. This is nasty.

This is a summary: 

![[Pasted image 20240423105532.png|center|500]]

---

Let's see the theoretical point of view:
![[Pasted image 20240423110351.png|center|300]]

But how many interactions we can actually see?
![[Pasted image 20240423110409.png|center|300]]

On average in the blu line there are 6 interactions per 25ns -> 6 photographs on top of each other.

That was run 1, let's see run 2:
![[Pasted image 20240423110457.png|center|300]]

Let's see the ATLAS point of view

![[Pasted image 20240423110735.png|center|400]]
The red linea are muons, the green ones are electrons and positron.

The dots in the last picture are reconstructed vetex, WELL sperareted vertex.  
So we have like ~15 and if we see the ditribution shown in the before in the last 2 plots is ok.

Another important thing is that, looking at the vertex we can see that the red lines are coming from the same event, as the green one. This means that there is a Higgs candidate. 

## And the grey stuff?

There are a lot of hadrons since we have collided protons and since there is not energy deposit in the calorimeter we can say that they are low energy because they are stopped before.

---
A display of a Z->μμ candidate event from proton-proton collisions recorded by ATLAS with LHC stable beams at a collision energy of 13 TeV on the 29th of September 2017 (Run 336852, Event 883966264).

The Z boson candidate is reconstructed in a beam crossing with 65 additionally reconstructed vertices from minimum bias interactions. The two muons have $P_T^\mu=61.5$ GeV and 60 GeV. The invariant mass of the two muons is 87 GeV.

![[Pasted image 20240423111814.png|center|300]]

## Cross section

Fermi's Golden Rule
$$
\mathrm{d} \sigma=\frac{(2 \pi)^4|M|^2}{4 \sqrt{\left(p_1 \cdot p_2\right)^2-m_1^2 m_2^2}} \mathrm{~d} \Phi_n\left(p_1+p_2 ; \; p_3 \ldots ; p_{n+2}\right)
$$

- Denominator: Flussfaktor (im SP-System):
$$
\sqrt{\left(p_1 \cdot p_2\right)^2-m_1^2 m_2^2}=p_{1, \mathrm{~cm}} \cdot \sqrt{s}
$$
- Nunerator: M is Matrix element squared

- Lorentz-invarianter Phasenraum
$$
\left.\mathrm{d} \Phi_n{\left(\right.}p_1+p_2 ; p_3 \ldots ; p_{n+2}\right)=\delta^4\left(p_1+p_2-\sum_{i=3}^{n+2} p_i\right) \prod_{i=3}^{n+2} \frac{\mathrm{d}^3 p_i}{(2 \pi)^3 2 E_i}
$$
## Example for $2 \rightarrow 2$  process

![[Pasted image 20240423112247.png|center|400]]

## How does it work for proton proton?

We cannot calculate a diagram for proton with perturbative QCD. 
How can we still make predictions if we cannot use QCD? 

We are lucky. We can separate this process in parts: 

**Proton-(anti-)proton cross sections factorize.**

**Factorization theorem**
1. First factor is the removal of the partons from a (anti-)protons: using the PDF that we already know. 
2. Second factor is the scattering of the partons off each other
![[Pasted image 20240423112616.png|center|500]]
3. Sum over all possible partons (valence quarks, sea quarks, gluons): i, j
5. Integrate over unknown momentum fractions of the partons: xi, xj
6. Need to define an energy scale that separates the two factors: factorization scale 𝜇𝐹


The cross section for $pp\rightarrow X$ takes from 
$$
\sigma_{p p \rightarrow X}=\sum_{i j} \iint d x_i d x_j f_i\left(x_i, \mu_F\right) f_j\left(x_j, \mu_F\right) \cdot \widehat{\sigma}_{i j \rightarrow X}\left(\alpha_S\left(\mu_R\right), Q^2, \mu_F, \mu_R\right)
$$
Maybe we are missing something: this is oversimplify, but the corrections that we are missing are small, so it's ok.

How does this can work? Take ep-scattering as an example: 
- The relativistic electron sees a Lorentz-contracted proton. The timescale for the electron to fly through the proton is much shorter than the timescale of parton-parton interactions. The electron sees a quasi-statistic picture of the partons with momentum fractions xi.

Additional info: 
- Partons are taken from the proton at an energy scale 𝜇_𝐹.
- For practical purposes, the factorization scale is usually assumed to be equal to the renormalization scale 𝜇_𝑅.
- It is scaled up and down by factors of 0.5 and 2.0 to estimate systematic uncertainties.
- First discussed by Drell and Yan 1970 for the description of Drell-Yan production.

But? It works!
theory of Drell Yan.

black is the data and the color is the theory 
![[Pasted image 20240423113852.png|center|600]]

![[Pasted image 20240423114517.png|center|400]]

![[Recording 20240423114530.webm]]
