# Trigger and Data Acquisition

## Production rates
This is how to Estimate the total number of produced scattering events per second at 13 TeV
![[Pasted image 20240515103149.png|center|400]]

![[Pasted image 20240506082618.png|center|400]]

Why we separate in time the data tacking? (you can see from the graph that the peack luminosity goes down sometimes)

The answer is that if we want to keep the quality of the data high we should make sure that the detector is working properly in all the components. I cannot press start and record for half a year, otherwise if one of the million channels is not working, I can compromise the dataset.

## Production rates

1. **Instantaneous Luminosity (𝐿)**: This refers to the number of particle interactions (usually proton-proton collisions) per unit area per unit time. It essentially quantifies the rate at which collisions are occurring within the collider. Higher luminosity means more collisions are happening per second.
    
2. **Cross-section (𝜎)**: It represents the probability that a collision will happen when two particles come into contact. The larger the cross-section, the more likely the interaction.
    
3. **Detector Efficiency (𝜖)**: This represents the probability that the detector will register a collision that actually occurs. Detectors are not perfect; they may miss some collisions or fail to register them accurately due to limitations in their design or operation. Detector efficiency quantifies this imperfection.
    
4. **Detector Acceptance (𝐴)**: This is the fraction of collisions within the detector's geometric acceptance that are actually recorded. Not all collisions that occur within the detector's volume are effectively detected and recorded due to various factors like geometric limitations or inefficiencies in the detection process.

Remember the rate equation: 
$$\dot{N} = L \cdot \sigma \cdot \epsilon \cdot A$$

We get ATLAS peak luminosity during Run 2:
Here a graph for the luminosity: $L = 2.1 \cdot 10^{34}\;\; cm^{−2}s^{−1}$

![[Pasted image 20240506083119.png|center|400]]

The fact that the blue is less than the green and yellow is because of we said before, sometimes something happen that corrupts the data.

ATLAS peak luminosity during Run 2: 𝐿 = $2.1 \cdot 10^{34}$ cm−2s−1

The cross section at 13 TeV for inelastic scattering: $78.1±2.9 mb$

So the pure collision and production rate is:
![[Pasted image 20240907230407.png|center|400]]

In comparison

![[Pasted image 20240506083944.png|center|400]]

---

*We are colliding one every 25ns, that is 40 MHz. So why we collide much more slowly with respect to the time we record. Why?*

**In a bunch there are more than 1 proton.** Higher production rate than crossing rate? Several interactions per bunch crossing!

• Calculate pile-up: 1.64 GHz / 40 MHz ~ 40.
![[Pasted image 20240515104829.png|center|400]]
This is a summary of what is happening
![[Pasted image 20240506084709.png|center|500]]


But if we look a the production rates of study that we care about we see that in most of the cases, the events are just QCD stuff.
In every 40 events that are recorded, one of this is Higgs for example (looking at the production rate for particles).

### What to store?
Data rate is the amount of data recorded per time interval.

- Collision rate( not production rate because pile-up ends up in one event)
- Size of a recorded event

So the event size **without pile-up** is:
![[Pasted image 20240506085421.png|center|200]]
Data rate in ATLAS:
$$𝑅 = 40 \cdot 10^{6} s^{−1} \cdot 1.5 MB ≈ 60 TB/s$$

It's a way too large amount of data to store, so we need a filter: **TRIGGER**.

---
## Trigger concept

**A trigger starts the data acquisition.**

Think of it as the starting point for gathering information from various sensors or measuring devices.

Consider a scenario where you're conducting measurements using a sophisticated detector that provides **precise** readings **but** operates relatively **slowly**.

An external trigger serves as a straightforward example. 
Imagine you're monitoring a physical phenomenon, and you want to start recording data precisely when a specific event occurs. In this case, an *external trigger*, which could be a signal from another device or a manual command, is used to commence the data acquisition process.

It's essential to understand the dynamics between the trigger and the detector signal. While the trigger enables quick data acquisition, the detector's precision ensures accurate measurements.

In order to have interesting data we need to consider trigger and detector signal
![[Pasted image 20240506090314.png|center|400]]


## Trigger concept

This simple concept does not scale to large and complex experiments. Instead, a more sophisticated approach is often required. There are alternative strategy:

1. **Identifying "Interesting Events"**: Rather than reacting to general signals, scientists pinpoint specific "interesting events" within the data. These could involve complex processes like inelastic collisions featuring particles with substantial transverse momentum.

2. **Defining Signatures**: P. Physicist establish the defining characteristics of these events and their components. These components, known as trigger objects, encompass various particles such as electrons, muons, jets, etc. The collective attributes defining these trigger objects constitute what's referred to as a signature.

3. **Collision Analysis**: Every collision or event undergoes scrutiny to determine the presence of these defined trigger objects. This involves sifting through vast amounts of data to identify instances that match the established signature criteria.

4. **Trigger Criteria**: Different triggers are devised based on the identified trigger objects and their characteristics. For instance, a trigger might activate only if specific objects with a minimum transverse momentum are detected within a collision.

5. **Trigger Menu**: A comprehensive collection of these distinct triggers forms what's termed a trigger menu. This menu outlines the conditions under which each trigger is activated, allowing for precise control over the data acquisition process.

Example: Higgs boson production
![[Pasted image 20240506090752.png|center|400]]
*Signature*:
-  Two oppositely charged leptons of one type (e.g. electrons)
-  Two oppositely charged leptons of another type (e.g. muons)

*Possible triggers*:
- Require 1 charged lepton with high momentum (too large background)
- Require 2 charge leptons with high momentum (ok, still involves other processes, e.g. top-quark pair production, Z-boson production, etc.)
- Require 3 charged leptons (very special, few events)

---

It's crucial to remember that *events not captured by triggers are lost forever*. To optimize the **balance** between **background noise and desired signals**, and to accommodate processes not yet discussed, a strategic approach is necessary:

1. **Inclusive Triggers**: These are broad triggers designed to capture a wide range of events, often used in searches for new phenomena. For instance, an inclusive trigger might target single muons exhibiting large momentum, allowing for the detection of various potential signals.

2. **Special Triggers for Precision**: In contrast to inclusive triggers, special triggers are tailored for precision measurements. These triggers are finely tuned to detect specific phenomena, such as pairs of charged leptons, enabling accurate and detailed measurements.

3. **Back-up Triggers**: These triggers serve as fail-safes or controls. They ensure that even if primary triggers fail or encounter issues, data collection can still proceed. Back-up triggers provide a safety net, ensuring that no critical data is lost due to technical glitches.

4. **Specialized Triggers for Exploration**: Some triggers are designed for exploratory purposes, such as minimum-bias triggers. These triggers capture random events without specific selection criteria, allowing researchers to explore unexpected phenomena or background noise.

In scenarios where trigger rates are excessively high, pre-scaling is employed. This technique involves storing data only after a trigger has fired a certain number of times (denoted as "n").


---
## Trigger levels 

Start with course triggers (L1).
Refine selection with (L2, HLT)

Example: select the picture of Peter Higgs

- Level 1
	- Full rate
![[Pasted image 20240506092342.png|center|400]]

-  Level 2
	-  A bit more information
	-  Reduced rate
	-  Can see people

![[Pasted image 20240506092406.png|center|400]]

- HLT
	- Add more information
	- Low rate
	- Select “real” people
	- End up with two pictures
	- Basis of data analysis (use these pictures to run face recognition)

![[Pasted image 20240506092725.png|center|400]]


## Trigger summary

Since the start of Run 2, the ATLAS detector has had a two-level trigger system. The first-level trigger (Level-1 trigger, L1) is implemented in hardware and uses a subset of the detector information to reduce the rate of accepted events from an input rate of up to 40 MHz to maximally 100 kHz. The L1 topological trigger processor (L1Topo) combines information about several objects into topological information about the event, and is used to greatly enhance the background rejection at L1 by exploiting the topological features of the targeted signal process. This is followed by a software-based trigger (high-level trigger, HLT) that reduces the rate of recorded events. An average rate of ∼ 1.2 kHz is written out for physics analysis. HLT objects, such as leptons or jets, are only reconstructed when specified L1 triggers have accepted an event. This event reconstruction is referred to as online reconstruction. Events that are accepted by the HLT are written out into different streams and transferred to CERN’s Tier-0 computing centre for offline reconstruction. Event selections in the HLT are referred to as triggers, and the collection of all L1 and HLT triggers and their prescales is called the trigger menu. Triggers are comprised of steps, where a step is a sequence of algorithms. A typical step will execute multiple feature-extraction algorithms requesting event-data fragments from within a rectangular (in η × φ) Region of Interest (RoI) defined by the L1 output, and run reconstruction algorithms over this sub-set of the event data. Each step terminates on a hypothesis algorithm, which uses the reconstructed features to form a boolean decision whether the trigger condition is satisfied. Triggers can also comprise a single hypothesis algorithm that makes no additional selection on an event after the L1 trigger; triggers with this selection are referred to as pass-through. The output of single algorithms and entire steps is cached, as is the partial-event data requested by feature extraction algorithms, and any subsequent requests for the same algorithm/step (within the same RoI) or data fragment(s) within the event processing returns the local cached version. Each L1 and HLT trigger has an associated prescale pL1 and pHLT, respectively, which take values ≥ 1. Only 1/pL1 events passing by a L1 trigger accepted for HLT processing and only 1/pHLT events passing the L1 selection required by an HLT trigger are processed at the HLT. Triggers with both pL1 = 1 and pHLT = 1 are referred to as unprescaled.

---
![[Pasted image 20240515112415.png|center|400]]

*Figure*: The average recording rate of the main physics data stream and the B-physics and light states data stream for each ATLAS pp physics run taken in 2018. The total average of all runs is indicated as a red dash-dotted line, and the total average of the main physics stream is indicated as a blue dashed line


![[Pasted image 20240515122416.png|center|400]]

*Figure*: Output bandwidth at the HLT as a function of time in a fill taken in September 2018 with a peak luminosity of $L = 2.0 × 10^{34} cm−2s−1$ and a peak pileup of 56. Presented are the main physics stream rate, containing all triggers for physics analyses; the B-physics and light states (LS) stream, containing triggers specific to B-physics analyses; the express stream, which records events at a low rate for data quality monitoring; other minor streams with physics applications, such as zero-bias and background events; the trigger-level analysis stream; and the detector calibration streams. The monitoring stream is not reflected in the output bandwidth as the monitoring data are not written out to disk.


**Trigger efficiency**
The "tag-and-probe" method is a valuable technique used to evaluate the efficiency of triggers in data acquisition systems. Here's how it works:

1. **Methodology**: The tag-and-probe method relies on known physical processes to assess the effectiveness of triggers. It's particularly useful for studying trigger efficiency in complex experimental setups.

2. **Example Process**: Consider the production of a Z boson followed by its decay into two muons. This well-understood process serves as a benchmark for trigger efficiency evaluation.

3. **Tagging Process**: In the tag-and-probe method, one of the muon tracks is designated as the "tag." This track is required to satisfy the trigger condition, meaning it must have initiated the trigger.

4. **Probe Analysis**: The other muon track, termed the "probe," is then analyzed offline. The primary question is whether this probe track would have also triggered the system if it were the only one considered.

5. **Evaluation**: By comparing the trigger status of the probe track to the trigger condition applied to the tag track, researchers can evaluate the efficiency of the trigger system. Specifically, they assess how often the trigger correctly identifies both muon tracks within the Z boson decay.

6. **Applicability**: While the tag-and-probe method is highly effective for processes like Z boson decays, it has limitations, particularly concerning resonant processes. Resonances may bias the results, affecting the method's applicability in certain experimental contexts.

![[Pasted image 20240515125902.png|center|400]]

## Trigger and DAQ comparison (Run 3)

![[Pasted image 20240515125946.png|center|400]]

![[Recording 20240506094517.webm]]
If you want to study triggers https://cds.cern.ch/record/2693402/files/ATL-DAQ-PUB-2019-001.pdf