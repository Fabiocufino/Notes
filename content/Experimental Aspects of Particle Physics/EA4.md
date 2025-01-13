# Proton-proton scattering
There are hypotesis, that the proton is an elementary particle or that it's not and it has constituents.

We derived several formulas and hypotesis to describe the proton and we develop the theoretical framework to compute the scattering with an electron, that is point like and so we can investigate the proton.

It's **not possible to predict the distribution function** because of the QCD high order mechanism -> mathematical problems.

Se we have to measure those.

## Parton distribution functions (continued)
There is a way to describe theoretically "something" for the PDF.

The evolution of Parton Distribution Functions (PDFs) with respect to $Q^2$ is described by the **DGLAP evolution equations**, formulated by Gribov and Lipatov in 1972, and later refined by Altarelli and Parisi in 1977, as well as by Dokshitzer in the same year. 
- These equations explain how PDFs change as a function of the momentum transfer $Q^2$.

It's essential to note that while these equations capture the relative changes in PDFs with $Q^2$, they don't specify the absolute dependence on $x$. The absolute $x$-dependence of PDFs must be determined from experimental data.

These evolution equations can be computed at different orders in perturbation theory. At first order:

![[Pasted image 20240422083036.png|center|500]]

- $q$, $\bar{q}$, $g$ are the distribution function of the quark, antiquark and gluon.

Splitting functions:
![[Pasted image 20240422083407.png|center|400]]


This is instead a graph that can actually help to understand in which direction the approximation of the behaviour of the inside of protons is going:
![[Pasted image 20240511164548.png|center|300]]

---
As said before, we have to **measure the PDF in dependence of x**. So we have to come up with a parametrisation.

Several PDF sets are available, each obtained by different research groups. Some of the renowned PDF sets include CTEQ, MSTW, NNDF, and HERAPDF. These sets vary in their parameterization, the number of parameters utilized, the input data employed, the treatment of heavy quarks, the value of $\alpha_s$, the handling of uncertainties, as well as the order of calculation, among other factors.

A typical parametrization used in PDF sets follows the form
$$x^a (1 - x)^b$$
where a and b are parameters determined through fitting to experimental data.

The input measurements utilized in constructing PDF sets include:
- Deep Inelastic Scattering (DIS) involving electron, muon, and neutrino scattering on hydrogen, deuterium, and heavier nuclei.
- Electron-proton DIS experiments conducted at HERA.
- Collider experiments such as those at the Tevatron and the LHC, encompassing processes like Drell-Yan production, production of W and Z bosons, as well as the ratio of W and single top cross sections, among others.

These diverse datasets contribute to the refinement and validation of PDF sets, enabling a more accurate description of proton structure and its interaction with high-energy particles.

Here instead different experiment that for different or $Q^2$ can have done a prediction of the PDFs
![[Pasted image 20240422084416.png|center|250]]

It's important to note that for example if i have $x = 10^{-3}$, we have results at HERA and we can use the PDF measurements and pdf taken and used at HERA and apply them for the same x at LHC.

Let's have a look at different processes at different x ranges
![[Pasted image 20240422084744.png|center|500]]

This table is essentially a summary of typical partonic interactions and their momentum distributions in different physical processes.

- The table links various collision processes to the parton-level interactions that occur inside the proton or neutron.
- It shows which **quarks**, **antiquarks**, or **gluons** are involved and what fraction of the proton's momentum they typically carry (through x-range).
- This information is essential for calculating **cross sections** and understanding what types of partons contribute to different high-energy processes at colliders like the LHC.


---
## Proton - Proton collisions (a quick look)

This is the description of a p-p collision.
![[Pasted image 20240422085324.png|center|300]]

And as we can see there is a **signature!** -> In the end we find a lepton-antilepton pair, and this has been used.
![[Pasted image 20240422085413.png|center|300]]
* *x axis is the rapidity*: there is the scattering angle that is the angle formed if you see the porcess in the COM. For low value of y means that we have a scattering angle that is very small.

In the graph we can see different PDF to do the prediciton (remember)
$$
\sigma \rightarrow \sigma^{Theor}_{proton} \cdot \; \textit{square summed}(x) \cdot f_1 f_2
$$
Here we can see 4 different parametrizations.

![[Pasted image 20240422085743.png|center|300]]

Here in the large energy we have large uncertainties because there are no a lot of data, for low energies the uncertainties are due to the difficulties in reconstruct the products.

---

- PDFs are available in the LHAPDF library.
- Several source of uncertainties are considered in the fits:
	- Experimental uncertainties due to limited statistics and due to systematics. The latter are often correlated and need to be treated with a lot of care.
	- Model uncertainties including the shape of the parameterization, the assumption of flavor symmetry of the sea quarks, the masses and treatment of heavy quarks, the choice of $\alpha_s$.
	• Theory uncertainties due to missing higher orders in the calculation.

• A working group has been set up in 2006 to formulate recommendations for the LHC, the PDF4LHC recommendations. The major aim is to help asses uncertainties and accuracies of PDF sets for different processes and to unify them among LHC experiments.

Now.

We are interested in measure at high energies because we aim to measure heavier particles. But how we can do that? We can increase energy or we can run the same experiment for twice longer.
![[Pasted image 20240422090811.png|center|300]]
turns out looking at this graph that run at high energies is better:

The graph clearly indicates that running at a higher energy, like 13 TeV, is significantly better for probing heavy particles because:
- The probability of the necessary parton interactions (gg, qq̅, qg) increases.
- There is direct access to higher mass scales, allowing the discovery of new heavy particles.
- The production cross-sections for heavy particles grow faster with energy than they would by simply increasing luminosity at a lower energy.


Let's go back to the PDFs.

We can see similar PDF for other particles, here we see Kaon and Pion with 2 quarks.
![[Pasted image 20240422090854.png|center|400]]

## Proton - Proton scattering

We need to discuss the kinematics first.
Let's look at 2 proton hitting each other in the x direction. The $\theta$ is the scattering angle. 
![[Pasted image 20240422091328.png|center|300]]

Usually we don't use the scattering angle but we use the **rapidity** 
$$
\eta = -ln[(\tan{\theta/2})]
$$
- the reason why is that the intervals (the deltas) on rapidity are Lorentz invariant! 

Let's se the translation between angle and the rapidity:
![[Pasted image 20240422091401.png|center|200]]

Also we need to discuss about the **transverse momentum**.

$$
p_T = p * sin(\phi_{cm})
$$

This is the projection of the particle momentum on the xy plane, is a measure of how much they go away from the beam pipe! 
![[Pasted image 20240422091613.png|center|300]]

Why we need the transverse momentum?
When we collide the proton-proton there is something important that we don't know. The Center of mass energy. This is because every time an interaction between stuff inside the proton happens we don't know the x of the particles that interact -> x of gluon and x of up quark or something.


#### 1. Elastic scattering
Protons interact as a whole with each other because they interact by photon exchanging. The protons remain intact indeed and there is a *small momentum transfer*, with a small scattering angle.
AS KK said "they pass by and they say hi to each other"

![[Pasted image 20240422092237.png|center|300]]
#### 2. Inelastic scattering
In inelastic scattering, protons interact with each other, leading to their breakup. This process is characterised by *large momentum transfer* and large scattering angles, allowing for extensive exploration of proton dynamics. 
Notably, the color connection between protons can induce hadronic activity between them, manifesting as additional particle production and accompanying energy deposition.

![[Pasted image 20240422092332.png|center|300]]

- Inelastic scattering problems:

partons (quarks and gluons) from one proton interact with partons from the other proton. In this interaction, the color charge of the partons must be conserved, as dictated by Quantum Chromodynamics (QCD). However, when partons from one proton interact with those from the other, the color neutrality of individual protons is momentarily disrupted.

**To conserve color charge**, the interacting partons from one proton need to connect to the partons of the other proton through the exchange of gluons. This exchange ensures that the total color charge remains neutral overall. However, the gluon exchange between partons can lead to additional complications.

For instance, a gluon connecting two partons from different protons may, in turn, emit additional gluons or even create quark-antiquark pairs due to the strong nature of the color force. These newly created particles can then further interact with the original partons or with other particles created in the interaction, leading to a cascade of particle production.

![[Pasted image 20240511171245.png|center|400]]

### 3. Diffractive scattering
In diffractive scattering, two protons engage in an exchange reaction, where either one or both protons may break up during the process. Despite this breakup, the quantum numbers of the protons remain intact. The exchange occurs via a colorless particle, such as a pomeron or a gluon ladder, ensuring conservation of color charge.

Experimentally, diffractive scattering is characterised by the observation of a rapidity gap between the scattered proton remnants. This gap arises because there are no color connections between the proton remnants, indicating the absence of strong interactions between them.
![[Pasted image 20240422093103.png|center|400]]

---
## Making predictions: proton-proton scattering

Proton-proton scattering primarily via strong interaction
-  Field quanta of QCD carry color charge and couple to themselves
- The strong coupling constant αs is running:
	- Small for large momentum transfer (small distances)
	- Large for small momentum transfer (large distances)

![[Pasted image 20240422093840.png|center|400]]

Understanding this running behavior of 𝛼𝑠 is crucial for making predictions about proton-proton scattering and other strong interaction processes.

- Perturbation Theory: Perturbation theory is applicable for processes with small couplings, typically observed at large values of 𝑄2.
- Inelastic Scattering: Inelastic scattering processes generally align well with perturbative calculations.
- Diffractive Scattering: Diffractive scattering, characterized by the exchange of colorless particles, often defies perturbative treatment.
- Total Cross Section: Calculating the total cross section for proton-proton scattering solely using QCD is challenging.
- Inference Methods:
    - Estimation: Despite limitations, rough estimates can be made based on theoretical considerations.
    - Symmetries: Utilizing symmetries inherent in QCD aids in understanding scattering processes.
    - Experimental Measurements: Direct measurements in particle colliders provide empirical data to validate and refine theoretical models, offering crucial insights into proton-proton scattering dynamics.

---
Historical comment:

**Froissart-Martin bound**
![[Pasted image 20240907210039.png|center|500]]

**Pomeranchuk theorem**
![[Pasted image 20240907210056.png|center|500]]



![[Recording 20240422094618.webm]]


