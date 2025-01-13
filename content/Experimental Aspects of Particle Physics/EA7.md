Physics object: something that has been recontstructed by the detector.
-> Measure a track and i build a momentum, the momentum is a physics object.

## Kinematics

---
### Lorentz transformations

- The energy $E$ and 3-momentum $\boldsymbol{p}$ of a particle of mass $m$ form a 4 -vector $p=(E, \boldsymbol{p})$ whose square $p^2 \equiv E^2-|p|^2=m^2$.
- The velocity of the particle is $\beta=p / E$.
- The energy and momentum $\left(E^*, \boldsymbol{p}^*\right)$ viewed from a frame moving with velocity $\boldsymbol{\beta}_f$ are given by
$$
\binom{E^*}{p_{\|}^*}=\left(\begin{array}{cc}
\gamma_f & -\gamma_f \beta_f \\
-\gamma_f \beta_f & \gamma_f
\end{array}\right)\binom{E}{p_{\|}}, \quad p_T^*=p_T,
$$
where $\gamma_f=\left(1-\beta_f^2\right)^{-1 / 2}$ and $p_T\left(p_{\|}\right)$ are the components of $\boldsymbol{p}$ perpendicular (parallel) to $\boldsymbol{\beta}_f$. 

Other 4-vectors, such as the space-time coordinates of events, of course transform in the same way. The scalar product of two 4 -momenta $p_1 \cdot p_2=E_1 E_2-p_1 \cdot p_2$ is invariant (frame independent).

---
### Center-of-mass energy and momentum

In the collision of two particles of masses $m_1$ and $m_2$ the total center-of-mass energy can be expressed in the Lorentz-invariant form
$$
\begin{aligned}
E_{\mathrm{cm}} & =\left[\left(E_1+E_2\right)^2-\left(\boldsymbol{p}_1+\boldsymbol{p}_2\right)^2\right]^{1 / 2}, \\
& =\left[m_1^2+m_2^2+2 E_1 E_2\left(1-\beta_1 \beta_2 \cos \theta\right)\right]^{1 / 2}
\end{aligned}
$$
where $\theta$ is the angle between the particles.

In the frame where one particle (of mass $m_2$ ) is at rest (lab frame),
$$
E_{\mathrm{cm}}=\left(m_1^2+m_2^2+2 E_{1 \mathrm{lab}} m_2\right)^{1 / 2} .
$$
The velocity of the center-of-mass in the lab frame is
$$
\beta_{\mathrm{cm}}=p_{\text {lab }} /\left(E_{1 \text { lab }}+m_2\right)
$$
where $\boldsymbol{p}_{\text {lab }} \equiv \boldsymbol{p}_{1 \text { lab }}$ and
$$
\gamma_{\mathrm{cm}}=\left(E_{1 \mathrm{lab}}+m_2\right) / E_{\mathrm{cm}}
$$

---
### Inclusive reactions

Choose some direction (usually the beam direction) for the $z$-axis; then the energy and momentum of a particle can be written as
$$
E=m_T \cosh y, \;\; p_x,\;\; p_y,\;\; p_z=m_T \sinh y
$$
where $m_T$, conventionally called the 'transverse mass', is given by
$$
m_T^2=m^2+p_x^2+p_y^2
$$
and the rapidity $y$ is defined by
$$
\begin{gathered}
y=\frac{1}{2} \ln \left(\frac{E+p_z}{E-p_z}\right) \\
=\ln \left(\frac{E+p_z}{m_T}\right)=\tanh ^{-1}\left(\frac{p_z}{E}\right) .
\end{gathered}
$$

Note that the definition of the transverse mass differs from that used by experimentalists at hadron colliders. Under a boost in the $z$-direction to a frame with velocity
$$\beta, y \rightarrow y-\tanh ^{-1} \beta$$Hence the shape of the rapidity distribution $d N / d y$ is invariant, as are differences in rapidity.

For $p \gg m$, the rapidity may be expanded to obtain
$$
\begin{gathered}
y=\frac{1}{2} \ln \frac{\cos ^2(\theta / 2)+m^2 / 4 p^2+\ldots}{\sin ^2(\theta / 2)+m^2 / 4 p^2+\ldots} \\
\approx-\ln \tan (\theta / 2) \equiv \eta
\end{gathered}
$$
where $\cos \theta=p_z / p$.
The pseudorapidity $\eta$ defined by the second line is approximately equal to the rapidity $y$ for $p \gg m$ and $\theta \gg 1 / \gamma$, and in any case can be measured when the mass and momentum of the particle are unknown. From the definition one can obtain the identities
$$
\sinh \eta=\cot \theta, \;\;\;\; \cosh \eta=1 / \sin \theta, \;\;\;\; \tanh \eta=\cos \theta .
$$

This is the rapidity distribution with its values. 
![[Pasted image 20240907224338.png|center|500]]

---
### Transverse variables

At hadron colliders, a significant and unknown proportion of the energy of the incoming hadrons in each event escapes down the beam-pipe. Consequently if invisible particles are created in the final state, their net momentum can only be constrained in the plane transverse to the beam direction. Defining the $z$-axis as the beam direction, this net momentum is equal to the missing transverse energy vector
$$
\boldsymbol{E}_T^{\text {miss }}=-\sum_i \boldsymbol{p}_T(i)
$$
where the sum runs over the transverse momenta of all visible final state particles.

**The missing transverse momentum is a vector, the missing transverse energy is a scalar**

---
**Other Kinematics**
$$
p_T=\sqrt{p_x^2+p_y^2} \quad \begin{aligned}
& p_x=p_T \cos \phi \\
& p_y=p_T \sin \phi \\
& p_z=p_T \sinh \eta
\end{aligned}
$$
$$
|p| = p_T cosh(\eta)
$$
$$
 E_T = \frac{E}{cosh(\eta)}
$$
The transverse momentum is invariant under Lorentz transformations in z-direction!

----
## ATLAS and CMS coordinate system
The picture shows the coordinate system with both angles and x,y. 
![[Pasted image 20240514163232.png|center|400]]

# Detector concepts - an overwiew

These detector concepts outline how different types of particles are detected and measured in high-energy physics experiments:

![[Pasted image 20240907224558.png|center|400]]

(P.S this picture is wrong. Can you spot the mistake?)
## Prompt Electrons and Muons, Charged Mesons and Leptons (in Jets):

- **Tracker and Magnetic Field**: Charged particles are deflected in a magnetic field, with the bending radius providing a measure of the particle's momentum. Tracking detectors reconstruct particle trajectories, crucial for vertex reconstruction and identifying the origin of particles.

- **Calorimeter**: Particles may stop in a calorimeter, depositing all or some of their energy. Calorimeters measure the energy of particles.

**Photons, Neutral Mesons (in Jets):**

- **Calorimeter**: Photons and neutral mesons do not interact with the magnetic field, making momentum measurement impossible. However, they interact with the calorimeter via electromagnetic interactions or strong interactions. Calorimeters measure their energy, aiding in event reconstruction and particle identification.

**Neutrinos:**

- **No Direct Interaction**: Neutrinos interact weakly, making direct detection challenging.
  
- **Transverse Momentum Imbalance**: Neutrinos do not have a direct interaction signature. However, their presence can be inferred from momentum imbalance in the event, especially in the transverse plane. The sum of transverse momentum components of all detected particles should be zero in the absence of external forces. Any imbalance indicates the presence of undetected neutrinos, enabling indirect inference of their transverse momentum.

## Tracking
Tracking charged particles is a fundamental task in particle physics experiments, crucial for reconstructing particle trajectories and identifying their properties. Here are some key points regarding tracking:

**Key Objectives:**

- **Close to the Vertex**: Tracking occurs close to the interaction vertex where particles are produced. This proximity enables precise determination of the particle's origin and properties.

- **Spatial Resolution**: High spatial resolution is essential for accurately reconstructing particle trajectories and vertex positions. This allows for precise measurements of particle momentum and identification of secondary vertices.

- **Minimal Material**: To minimize multiple scattering and energy loss, there should be minimal material in front of the tracking system. This ensures accurate measurement of particle trajectories and energy deposition.

- **Primary Vertex Distinguishability**: The ability to distinguish primary vertices (where the collision occurred) from secondary vertices (where particles decay) is crucial for identifying particle interactions and understanding the underlying physics processes.

- **b-Tagging**: Identifying b-quarks (bottom quarks) is important for studying processes involving the production and decay of heavy-flavor particles.

**Detector Types:**

1. **Silicon Pixel and/or Strip Detectors**: These detectors offer excellent spatial resolution and are commonly used in tracking systems. They consist of arrays of pixel or strip sensors, where charged particles create electron-hole pairs, generating a measurable electrical signal.

2. **Time-Projection Chambers (TPCs)**: TPCs use the drift of ionization electrons in a uniform electric field to reconstruct particle trajectories in three dimensions. They offer good spatial resolution and are particularly useful for tracking in high-rate environments.

3. **Wire Chambers**: Wire chambers, such as drift chambers and multi-wire proportional chambers, detect charged particles by ionizing gas molecules along their path. The resulting electron drift is measured to reconstruct the particle trajectory.


**ATLAS Inner detector**
![[Pasted image 20240514164246.png|center|500]]
![[Pasted image 20240514164303.png|center|500]]

## Calorimeters
Calorimeters are crucial components in particle physics experiments for measuring the energy of particles.

- **Energy Measurement**: Calorimeters measure the total energy deposited by particles passing through them.

- **Direction Information**: Segmented calorimeters provide info on the direction of the particle: by dividing the detector into segments.
#### Concept:

1. **Particle Shower Formation**: When particles enter the calorimeter, they interact with the material, producing a cascade of secondary particles known as a shower. These showers consist of electrons, positrons, photons, and other particles created in the initial interactions.

2. **Energy Sampling or Measurement**: Calorimeters sample or measure the energy deposited by particles within their volume. This measurement can be achieved through various techniques, such as measuring the ionization.

#### Types of Calorimeters:

1. **Electromagnetic Calorimeters (ECAL)**:
   - Designed to measure the energy of electromagnetic particles such as electrons and photons.
   - Typically composed of dense materials that interact strongly with electromagnetic particles, leading to the generation of electromagnetic showers.
   - Examples include lead-glass calorimeters and lead-scintillator calorimeters.

2. **Hadronic Calorimeters (HCAL)**:
   - Designed to measure the energy of hadrons (particles composed of quarks) such as protons, neutrons, and mesons.
   - Need to be able to absorb and measure the energy of hadronic showers, which are typically more extended and less well-contained than electromagnetic showers.
   - Often made of dense materials with high nuclear interaction lengths, such as steel, iron, or plastic scintillator.
![[Pasted image 20240514165233.png|center|500]]

![[Pasted image 20240514165239.png|center|500]]

## Muon systems
• The only (visible) particle escaping the calorimeter is the muon (particle identification)
• Use tracking technology including a magnet system to measure the muon momentum
• Less precise measurements compared to inner tracking detectors


**ATLAS muon spectrometer**
![[Pasted image 20240515101439.png|center|500]]
![[Recording 20240430114541.webm]]














