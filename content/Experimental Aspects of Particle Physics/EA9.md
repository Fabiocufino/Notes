![[Pasted image 20240516134918.png|center|600]]

## Aim
Event generators **simulate** the interactions occurring during collisions, generating a series of final particles described through four-dimensional vectors that can be processed by our computing devices.

However, it's crucial to understand that the information produced by these generators cannot be directly compared with the actual measurements from our detectors: they don't include the particle detection processes.

Consequently, to gain a comprehensive understanding of the studied phenomena, it's **necessary to also simulate** our detectors' response, accounting for factors such as spatial and energy resolution, detection efficiency, and particle acceptance. This simulation often requires the use of *Monte Carlo methods*, which enable us to manage the complexity of our detectors through simulations based on stochastic processes.

For the **simulation chain** we have: 

![[Pasted image 20240507103919.png|center|250]]

Now we will focus on 'Detector Simulation'.

To estimate **radiation effects in a given area**, we rely on advanced simulation tools like `Geant4`, `Fluka`, or `MCNP`. 

These tools take into account:

- **Setup geometry**: Details of the experimental setup, like collider configuration or clinical equipment.
- **Radiation source**: Whether it's radioactive material, particle beams, or collision processes.
- **Measurement volume**: Where we want to analyze radiation effects, such as detector elements or patients.

The simulations provide outputs like *energy distribution*, *dose per volume* (including biological impact), and *particle fluxes*.

The most important is `Geant4`

---
## Simple example

Consider 10 GeV protons that go through a 10mm thick scintillator

• **Event generation**: 
	• Particle has fixed energy 
	• Starts from fixed point
	• Goes to the right

• **Detector simulation**:
	• Particle scatters around
	• Deposits energy in the scintillator 
	• Secondary particles

![[Pasted image 20240507105204.png|center|250]]

In the picture the first kick is the proton that does an elastic collision with the oxygen and it kicks out a neutron.

You do that a lot of times and you see a landau distribution: **this is the original shape of the signal.**
![[Pasted image 20240507105234.png|center|300]]

**Analog signal:** 
	• Here: on average 10 photons per MeV detected by PMT 
	• Landau shape now *convoluted* with Poisson distribution
	![[Pasted image 20240519103544.png|center|300]]

**Digital signal**: 
	• Signal shape can be calculated convoluting half a dozen functions 
	• Or it can be done using a Monte Carlo method (random numbers)
![[Pasted image 20240507105951.png|center|150]]

---
## Geant4

Geant4 operates on a simple yet powerful concept:

- **Input the primary particles**: These are the initial particles generated, often stemming from interactions such as collisions or decay processes.

- **Propagate all primary and secondary particles through a volume**: Geant4 tracks the movement of these primary particles as well as any secondary particles they produce as they traverse through a specified volume, which could be a detector or any other defined region.

- **Use random numbers to create interactions**: To simulate the stochastic nature of particle interactions, Geant4 employs random numbers to determine when and how interactions occur, such as scattering or the photoelectric effect. This randomness mimics the probabilistic nature, ensuring a realistic simulation of particle behavior.

Several key elements contribute to its functionality and effectiveness:

**Kernel:**
- **Geometry and materials**: Defines the shape and composition of the simulated environment.
- **Tracks**: Tracks the paths of particles as they propagate through the simulation.
- **Events**: Represents interactions such as collisions or the creation of primary particles.
- **Runs**: Organizes simulations into discrete iterations or batches.

**Physics processes:**
- **Cross sections and final state generation**: Determines the likelihood of particle interactions and generates the resulting final states.
- **Models for electromagnetic, hadronic, and other interactions**: Provides a framework for simulating various types of particle interactions.
- **Physics lists**: Organizes physics processes into coherent sets tailored for specific applications.

**Auxiliary parts:**
- **User interface for control**: Allows users to interact with and control the simulation.
- **Visualization**: Provides tools for visualizing simulation results.
- **Interfaces for input of geometry and materials**: Facilitates the specification of simulation geometry and materials.
- **Record keeping**: Stores user-requested data such as energy deposits and particle fluxes for analysis and monitoring.

![[Pasted image 20240507111152.png]]

---
## Tracks
In Geant4, a Track is a snapshot of a particle. It encapsulates various physical quantities that characterize the particle at a specific moment, such as position, momentum, energy, and particle type. 

- A Step is the “delta” information of a track. A track is not a collection of steps. Instead, a track is updated in a series of steps.

A Track ceases to exist under various conditions:
- When the particle exits the outermost volume (often referred to as the 'world' volume).
- If the particle undergoes an interaction leading to its disappearance, such as decay or inelastic scattering.
- When the particle's kinetic energy diminishes to zero and no further "AtRest" processes apply.
- If the user explicitly terminates the track, either manually or through specified criteria.

It's important to note that all tracks cease to exist at the end of an event; none persist beyond this point.

## Steps
In Geant4, a Step is a fundamental unit of progression for a particle within the simulation. It encapsulates the changes experienced by the particle as it traverses a small interval of its trajectory. 

Here's a breakdown of key characteristics of a Step:

- **Two points**: A Step is defined by two points along the particle's path, representing its start and end positions within the simulation volume.

- **Delta information**: It provides information about changes experienced by the particle during the step, such as energy loss, time-of-flight, and other relevant parameters.

- **Volume association**: Each point of a Step is associated with the volume(s) it traverses during the step, along with the respective material(s) it encounters.

- **Boundary crossings**: If a Step crosses a volume boundary during its progression, its end point physically resides on the boundary while logically belonging to the next volume. This allows for the simulation of boundary processes such as reflection, refraction, and transition radiation.
![[Pasted image 20240516141201.png|center|400]]

## Event
- An event is the basic unit of simulation in Geant4, represents a set of tracks 
	- At its beginning primary tracks are generated ( and pushed onto a stack ). 
	- One ‘track’ at a time is popped from the stack and it is “tracked” 
- Any resulting secondary tracks are pushed back onto the stack.
- This “tracking” lasts as long as the stack has a track. 
	- When the stack becomes empty, it’s the end of processing that event.
- An object of the G4Event class represents an event. After its processing it contains few objects: 
	- List of primary vertices and particles (its input) 
	- Hits and Trajectory collections (its output.)

Here the event process:

![[Pasted image 20240516141353.png|center|400]]

## Runs
In analogy with real experiments, a G4Run starts with “Beam On”.
By definition within a run, the user cannot change
- detector setup
- settings of physics processes

Typically a run consists of one event loop. (Events are treated one after another.) At a run’s start, geometry structures and physics configurations are prepared
-  the geometry is optimized for navigation,
-  cross-section tables are calculated for the setup’s materials etc

## Geometry and material
-  Geometrical shapes
-  Logical volumes defined by geometrical shape and material
-  Can flag as “sensitive detector”
- Physical volumes are logical volumes placed in the simulation world. Each one has a unique ID.
- Sensitive detectors can store information about energy loss, interaction type, etc.
- Important for digitization (not part of particle transport codes)
![[Pasted image 20240908122318.png|center|500]]


## Digitization
- Geant4: energy deposition in sensitive volume
- Transfer energy into measurable signal, e.g. current or voltage pulse
- Parameterize the response as a function of the energy 
- Can include random processes, e.g. noise
- Validate in data

## Developments
- Fast Simulations
- Approximate the simulated detector answer e.g. by using machine learning
- Example: Fast simulation of a high granularity calorimeter by generative adversarial networks

![[Recording 20240507113620.webm]]
