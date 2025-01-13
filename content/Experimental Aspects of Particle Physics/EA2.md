Why do we need to accelerate particle?

High-energy collisions can lead to the creation of new particles that are not observed in everyday interactions.

But now, how do we accelerate particles?
## RadioFrequency cavities
RF cavities utilize alternating electric fields to accelerate charged particles in particle accelerators. When charged particles pass through the cavity, they interact with the oscillating electric field, gaining energy during the portion of the field cycle when it is aligned with their motion. The frequency of the RF voltage applied to the cavity is tuned to match the natural resonance frequency of the cavity, maximizing the energy transfer efficiency. Focusing elements such as magnetic lenses or quadrupole magnets may also be incorporated to control and focus the particle beams as they accelerate through the cavities.
![[Pasted image 20240416180959.png|center|400]]

We should be careful of the fact that the protons injected in the machines are not sigle point-like, but they are more like bunches that have spread: so a particle in this shape will arrive earlier wrt the anotherone in the end that will arrive retarded. 

**Consequence:**
![[Pasted image 20240416181359.png|center|500]]

So a linear beam of protons that has been injected gets divided in bunches smaller and more confined.
## Synchrotrons and storage rings
The important thing here is that the RF cavities that we showed before were linear, in order to have the kind of energy that particle physics require, we need to build things that are super long OR .. yes, you make a circle.
![[Pasted image 20240416205532.png|center|400]]

## Acceleration
We can finally talk about accelerating stuff. 

As the particles travel through the RF cavities, they gain energy, but they also experience longitudinal oscillations in their energy due to various factors such as the RF frequency, the focusing forces from magnetic fields, and the particle's own inertia. These oscillations are called **synchrotron oscillations** because they are synchronized with the RF frequency of the accelerator.
Net acceleration (This means they gain energy in a consistent, cumulative manner every time they pass through the RF cavities) if frequency of the RF cavities is a multiple of the revolution frequency, i.e
$$
f_{RF} = h f_{rev}
$$
Example:
	During the 2012 data taking, the cavities of the LHC were tuned to $f_{RF} = 400$ $MHz$. In general, the revolution frequency of the particles is defined by the ratio of the speed of light, c, and the circumference of the accelerator, so $u = 26 659m$ for the LHC and thus $f_{REV} = c/u = 11.245$ $kHz$. This lead to $h = f_{RF}/f_{REV} = 35,640$ buckets. 
	- This means that the spaces aveileable per a single bunch was 35,640 places to be in order to get a kick. Only $nb = 2808$ were filled and carried bunches. 
	- The bunches were 7.5 m apart, which corresponds to a bunch spacing of 25 ns.
	- The number of protons per bunch was $N1/2=1.15·10^11$. Back then, the LHC accelerated particles from 450 GeV to 4 TeV and then kept them on a stable orbit for collisions.

-> From frequency calculation you can compute the number of buckets.

## Controlling the particles
Two fundamental concepts in particle accelerator design are weak focusing and strong focusing. These concepts pertain to the means by which magnetic fields are employed to guide and focus particles within the accelerator.

**Weak focusing:**
	Weak focusing utilizes DIPOLE MAGNETS to provide a force when particles deviate from their ideal trajectory. These oscillations, calles **betatron oscillations** characterized by the **tune**, the number of oscillations per turn. For instance, the Large Hadron Collider (LHC) operates with a tune of about 60, indicating relatively large oscillations.
	
**Strong focusing:**
	In the LHC, strong focusing tightly controls particle trajectories using a combination of DIPOLE and QUADRUPOLE magnets. Dipole magnets bend particle paths, while quadrupole magnets focus beams both horizontally and vertically. This precise magnetic setup minimizes deviations from ideal trajectories, ensuring stable beams and efficient collisions at experiment points.
	![[Pasted image 20240416210800.png|center|300]]
	Here a representation of Quadrupole Magnets with inverted polarisation ![[Pasted image 20240416210915.png|center|200]]

---
## Beam dynamics
The motion of charged particles inside the beam in the x and y directions is described by Hill differential equations
![[Pasted image 20240416211044.png|center|200]]
- $𝐾_𝑥(𝑠)$ is a restoring force that depends on the position s and which is defined by the magnet system
- As a remark: see that it depends on the position!

The general solution that is not a simple cosine or sine can be parametrised as
![[Pasted image 20240416211356.png|center|400]]

All particles oscillated around the ideal trajectory and within the envelope $\sqrt{\epsilon * \beta(s)}$.

Let's plot the spread in the phase space 
![[Pasted image 20240416211512.png|center|250]]
The area of phase space is constant (Liouville’s theorem) and equal to 𝜀 ∙ 𝜋.

But why do we want to squeeze them? We have $10^{12}$ particles and we want them to collide -> to have collisions we need to squeeze them.







## Collision rates
The amplitude function at the interaction point is referred to as $𝛽^∗$ the corresponding transverse beam size is
$$
\sigma^* = \sqrt{\epsilon \beta^*}
$$
The smaller $\epsilon$ and $𝛽^*$, the more particles are squeezed and brought into collision.

Example:
	In 2012, the LHC was operated with 𝛽∗= 55 cm and 𝜀 = 3.75 µm resulting in a transverse beam spread of 𝜎∗= 17 µm. The bunch length has been $𝜎_𝑧$ = 7.5 cm.

## Luminosity
Luminosity refers to the measure of the rate at which particles collide within the accelerator. It represents the number of collisions per unit area per unit time. Let's build it.

The number of colliding particles per unit time is
$$
\dot N = \sigma \mathcal{L}
$$
- 𝜎 is the cross section of the particle reaction
- ℒ is the instantaneous luminosity

*Unit: cm-2s-1*

The integrated luminosity is a measure of the total number of collisions
![[Pasted image 20240416214538.png|center|150]]
*Unit: cm-2 or fb-1*

The instantaneous luminosity can be calculated from the beam properties
![[Pasted image 20240416214633.png|center|300]]
This is a plot of the Luminosity in the 4 detectors in LHC 
![[Pasted image 20240416215043.png|center|400]]

## LHC dipole magnets
Those are the original actually used in LHC from CERN
![[Pasted image 20240905192827.png|center|500]]


![[Pasted image 20240416215206.png|center|300]]

