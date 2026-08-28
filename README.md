# Variable Pitch Propeller

### Parametric Design, CFD Analysis, Fabrication and Experimental Validation

This project focuses on the **design, simulation, fabrication, and experimental testing of a manually adjustable variable pitch propeller**.

The basic idea behind variable pitch propulsion is simple: instead of keeping the blade pitch fixed, the blade angle can be changed to adapt the propeller to different operating conditions.

A fixed-pitch propeller is inherently a compromise. A pitch that works well at one operating condition may not be optimal at another.

A variable pitch system provides another degree of freedom:

```text
Operating Condition
        ↓
   Blade Pitch
        ↓
Aerodynamic Loading
        ↓
      Thrust
        ↓
 Propulsion Efficiency
```

The goal of this project was to investigate that relationship experimentally and computationally.

The study combines **propeller aerodynamic analysis, parametric CAD modelling, CFD, additive manufacturing, mechanical design, and experimental thrust measurement** into one complete workflow.

A total of **16 pitch configurations from 0° to 30° in 2° increments** were investigated. The propeller was simulated at 3000 RPM and subsequently tested using a physical prototype driven by a brushless DC motor.

The maximum thrust occurred at approximately **28° pitch**.

The CFD model predicted:

```text
Maximum simulated thrust = 2.20 N
Optimal pitch             = 28°
```

while the experimental setup measured:

```text
Maximum experimental thrust = 3.00 N
Optimal pitch                = 28°
```

The agreement in the overall trend provided useful experimental validation of the computational study.

---

# Project Website

**https://aboutkvs.vercel.app/**

---

# Project Overview

The project was developed around a simple engineering question:

> **How does changing propeller blade pitch affect thrust generation, and can a manually adjustable variable pitch mechanism provide a practical improvement over a fixed-pitch configuration?**

To answer this, the project was divided into four major stages:

```text
       AERODYNAMIC DESIGN
              ↓
       PARAMETRIC CAD
              ↓
             CFD
              ↓
        3D FABRICATION
              ↓
       EXPERIMENTAL TEST
              ↓
       DATA COMPARISON
```

The approach was intentionally iterative.

Rather than designing a mechanism first and testing it directly, the propeller geometry was developed parametrically, simulated across multiple pitch angles, fabricated, and then experimentally evaluated.

---

# Why Variable Pitch?

A propeller operates under changing aerodynamic conditions throughout a flight mission.

For a UAV, for example, the propeller may encounter different requirements during:

* Take-off
* Climb
* Cruise
* Descent
* Hover or low-speed operation

A fixed-pitch blade cannot change its aerodynamic pitch after manufacture.

A variable pitch propeller can instead adjust the blade angle to modify the aerodynamic loading.

The conceptual relationship is:

```text
Low Pitch
    ↓
Lower aerodynamic loading
    ↓
Lower thrust demand
    ↓
Suitable for some operating conditions

High Pitch
    ↓
Higher aerodynamic loading
    ↓
Higher thrust
    ↓
Potentially increased stall risk
```

The project investigates this tradeoff experimentally.

---

# Objectives

The main objective was to develop and evaluate a variable pitch propeller capable of producing different thrust levels through manual adjustment of blade pitch.

The specific objectives included:

* Develop a variable pitch propeller geometry.
* Create a parametric CAD model.
* Generate multiple pitch configurations.
* Perform CFD analysis at each pitch angle.
* Fabricate a functional prototype.
* Develop an experimental thrust measurement system.
* Measure thrust at controlled RPM.
* Compare experimental and CFD predictions.
* Identify the pitch angle providing maximum thrust.
* Study the onset of performance degradation and probable stall behaviour.

The project methodology combines conceptual design, CAD, CFD, physical fabrication, experimental testing, and result comparison.

---

# Overall Workflow

The complete engineering workflow was:

```text
Literature / Propeller Study
          ↓
Conceptual Design
          ↓
Blade Geometry Development
          ↓
OpenProp Parametric Design
          ↓
SolidWorks CAD
          ↓
Pitch Configuration Generation
          ↓
CFD Simulation
          ↓
Thrust vs Pitch Analysis
          ↓
Prototype Fabrication
          ↓
Blade Balancing
          ↓
Experimental Test Rig
          ↓
RPM Measurement
          ↓
Thrust Measurement
          ↓
Five Trials / Configuration
          ↓
Data Averaging
          ↓
CFD vs Experimental Comparison
          ↓
Performance Analysis
```

This workflow allowed the computational and physical parts of the project to inform each other rather than treating simulation and experimentation as separate activities.

---

# Propeller Geometry

A **3-blade open propeller** was selected for the study.

The design was developed with variable pitch capability so that the blade angle could be changed without redesigning the entire propeller.

The pitch range investigated was:

```text
0° → 30°
```

with a step size of:

```text
2°
```

This resulted in:

```text
16 pitch configurations
```

being evaluated.

The design included a rotating blade-root feature, allowing the pitch to be modified parametrically in the CAD model.

---

# Parametric Design

One of the important parts of the project was making the propeller geometry adjustable rather than creating independent models manually.

The blade was parametrically modelled so that changing the pitch parameter generated a new configuration.

This made it possible to create:

```text
0°
2°
4°
6°
8°
10°
12°
14°
16°
18°
20°
22°
24°
26°
28°
30°
```

without rebuilding the blade geometry from scratch.

This approach is particularly useful for aerodynamic optimisation because the geometry becomes a design variable.

Instead of:

```text
Model → Simulate → Redesign → Model → Simulate
```

the workflow becomes:

```text
Parameter
    ↓
Geometry
    ↓
Simulation
    ↓
Performance
```

That is much closer to how a computational design optimisation workflow is structured.

---

# OpenProp

**OpenProp** was used during the initial propeller design stage.

The parametric design process was used to establish the blade geometry and profile before transferring the design into SolidWorks for detailed CAD development.

This provided an aerodynamic starting point for the blade rather than relying entirely on manually defined geometry.

The resulting propeller profiles were then incorporated into the SolidWorks model.

---

# SolidWorks CAD

SolidWorks was used to develop the complete propeller assembly.

The CAD model included:

* Propeller blades
* Hub
* Blade-root interfaces
* Coupler
* Bolts
* Pitch adjustment mechanism
* Supporting components

Multiple components were created as individual parts and assembled into the final mechanism.

The hub incorporated radial sockets to securely hold the blade roots while still allowing the blade pitch to be adjusted.

---

# Variable Pitch Mechanism

The physical design was intentionally modular.

The blade roots were designed so that the pitch could be changed manually using alignment features.

This provided several advantages during testing:

* Easy blade replacement
* Repeatable pitch positioning
* Simple mechanical construction
* Low fabrication complexity
* Ability to test many pitch configurations

The prototype was therefore not simply a fixed propeller with multiple models.

It was a single modular system that could be reconfigured between tests.

---

# CFD Analysis

The aerodynamic behaviour of the propeller was studied using:

**SolidWorks Flow Simulation**

The CFD setup included a rotating region to represent propeller motion.

The simulations were performed at:

```text
RPM = 3000
```

under standard sea-level atmospheric conditions.

The simulation was repeated across the different blade pitch configurations.

---

# CFD Outputs

For each pitch configuration, the simulation was used to obtain:

* Thrust force
* Drag force
* Lift-to-drag ratio
* Flow field
* Velocity distribution
* Aerodynamic behaviour

The results were then compared as a function of blade pitch.

The primary quantity of interest was:

```text
Thrust vs Pitch Angle
```

This allowed the optimal pitch region to be identified.

---

# Stall Analysis

The CFD study also investigated flow behaviour at extreme pitch configurations.

Flow simulations indicated stall-like behaviour at:

```text
2° pitch
```

and:

```text
30° pitch
```

These cases were used to investigate the limits of the operating range and understand why increasing pitch does not indefinitely increase useful thrust.

The important physical observation is that increasing pitch increases blade loading only up to a certain point.

Beyond that region, aerodynamic losses and probable stall effects begin to limit further thrust improvement.

---

# Prototype Fabrication

The propeller was manufactured using:

**FDM 3D printing**

with:

**PLA**

as the material.

The modular design allowed the blades and hub to be printed separately.

After printing, the components were:

* Sanded
* Balanced
* Checked for alignment
* Assembled
* Installed on the motor

The blade roots incorporated locking holes for manually setting the pitch using alignment pins.

This made the prototype inexpensive and relatively quick to iterate.

---

# Experimental Test Rig

A dedicated experimental setup was developed to measure actual propeller thrust.

The main components were:

```text
BLDC Motor
     ↓
Propeller
     ↓
Load Cell
     ↓
Thrust Measurement
```

with RPM independently monitored using a laser tachometer.

The setup included:

| Component                | Function            |
| ------------------------ | ------------------- |
| BLDC motor               | Propeller drive     |
| ESC                      | Motor speed control |
| Laser tachometer         | RPM measurement     |
| Load cell                | Thrust measurement  |
| Digital pitch protractor | Pitch verification  |
| Throttle controller      | RPM control         |

The motor was rated around 3000 RPM and the experiments were performed at 3000 RPM.

---

# Experimental Procedure

Each pitch configuration was tested using the following procedure:

```text
Set Blade Pitch
       ↓
Verify Pitch
       ↓
Start Motor
       ↓
Increase RPM
       ↓
Reach 3000 RPM
       ↓
Record Thrust
       ↓
Repeat 5 Times
       ↓
Calculate Average
       ↓
Move to Next Pitch
```

Five trials were conducted for each configuration to reduce the influence of measurement fluctuations.

The averaged experimental values were then compared against the corresponding CFD predictions.

---

# Experimental Results

The key result was that both CFD and experimental testing identified **28° pitch as the optimum configuration**.

At the optimum pitch:

```text
Pitch Angle = 28°
```

the results were:

| Parameter      |    CFD | Experiment |
| -------------- | -----: | ---------: |
| Maximum thrust | 2.20 N |     3.00 N |
| Optimal pitch  |    28° |        28° |

The experimental thrust was consistently higher than the simulated values, but the overall trend with pitch was similar.

---

# Thrust Trend

The experimental and CFD data showed increasing thrust as pitch increased through most of the tested range.

Representative results included:

| Pitch | Simulated Thrust | Experimental Thrust |
| ----: | ---------------: | ------------------: |
|    0° |           0.12 N |              0.16 N |
|    2° |           0.26 N |              0.29 N |
|    4° |           0.39 N |              0.41 N |
|   24° |           2.10 N |              2.81 N |
|   26° |           2.18 N |              2.90 N |
|   28° |       **2.20 N** |          **3.00 N** |
|   30° |           2.19 N |              2.97 N |

The results show a clear rise in thrust with pitch followed by saturation or a slight decrease beyond the optimum region.

---

# Key Result

The most important finding from the project was:

> **Increasing blade pitch increased thrust up to approximately 28°, after which the thrust began to saturate or decrease slightly.**

This behaviour is consistent with the expected aerodynamic tradeoff.

At higher pitch angles, the blade experiences greater aerodynamic loading.

However, increasing loading indefinitely does not guarantee increasing useful thrust.

Eventually, flow separation and probable stall effects begin to reduce aerodynamic effectiveness.

The CFD results identified this behaviour, and the experimental results showed the same general trend.

---

# CFD vs Experiment

One of the most interesting results was that the experimental thrust was higher than the simulated thrust.

The report identifies several possible contributors:

* Real airflow behaviour not completely captured by the simulation
* Surface imperfections
* Sensor inaccuracies
* Indoor airflow conditions
* Possible RPM under-reporting by the tachometer

The experimental values were generally around **10 to 15% higher** than the CFD predictions.

This difference is important because it demonstrates that simulation should not automatically be treated as ground truth.

Instead:

```text
CFD
 ↓
Prediction

Experiment
 ↓
Physical Validation

CFD + Experiment
 ↓
Engineering Understanding
```

The agreement in the trend and optimum pitch provides more useful information than simply looking for identical numerical values.

---

# Why the Difference Matters

The CFD model necessarily simplifies the physical system.

The real experiment contains effects such as:

* Manufacturing imperfections
* Blade surface roughness
* Motor behaviour
* Measurement uncertainty
* Indoor airflow
* Structural vibration
* RPM variation
* Mounting effects

These effects are difficult to represent perfectly in a relatively simple CFD model.

The experimental system therefore provides a practical reality check on the numerical predictions.

---

# Engineering Interpretation

The results demonstrate that blade pitch is an effective control variable for propeller thrust.

The relationship can be summarized as:

```text
Low Pitch
    ↓
Low Blade Loading
    ↓
Low Thrust

Increasing Pitch
    ↓
Increasing Blade Loading
    ↓
Increasing Thrust

Optimum Pitch
    ↓
Maximum Useful Thrust

Excessive Pitch
    ↓
Flow Separation / Stall
    ↓
Thrust Saturation or Reduction
```

For this particular propeller configuration and operating condition, the optimum occurred around:

```text
28°
```

at:

```text
3000 RPM
```

The optimum should not be interpreted as a universal propeller operating point. It is specific to the geometry, RPM, test conditions, and configuration studied in this project.

---

# Mechanical Design Considerations

Designing the variable pitch mechanism introduced several additional constraints beyond aerodynamics.

The blade root had to:

* Rotate through the required pitch range
* Remain securely attached
* Maintain alignment
* Transfer aerodynamic loading
* Allow repeated adjustment
* Remain manufacturable using 3D printing

The hub therefore became a mechanical design problem as much as an aerodynamic one.

This is one of the reasons the project was developed as a modular assembly rather than a single printed component.

---

# Design Tradeoffs

The project highlighted several important engineering tradeoffs.

### Pitch vs Thrust

Increasing pitch generally increased thrust until the optimum region.

### Pitch vs Stall

Excessive pitch increased the likelihood of flow separation and stall.

### Mechanism vs Mass

A more sophisticated pitch mechanism can provide better control but introduces additional mass and complexity.

### Accuracy vs Cost

The manually adjustable mechanism is inexpensive and easy to fabricate, but it does not provide real-time pitch control.

### Simulation vs Reality

CFD provides repeatable predictions, while physical testing captures real-world effects that are difficult to model.

---

# What Makes This Project Different

This was not only a CAD project.

It was not only a CFD project.

It was not only a propulsion experiment.

The project connected all three with physical testing:

```text
             OpenProp
                 ↓
          Blade Geometry
                 ↓
            SolidWorks
                 ↓
          Parametric CAD
                 ↓
        Flow Simulation CFD
                 ↓
         Performance Study
                 ↓
           3D Printing
                 ↓
        Physical Assembly
                 ↓
          BLDC Test Rig
                 ↓
       Thrust Measurement
                 ↓
        Experimental Data
                 ↓
         CFD Comparison
```

That complete loop is the main engineering value of the project.

---

# Limitations

The project also identified several limitations.

### Static Pitch Adjustment

The pitch was manually changed between tests rather than dynamically during operation.

This means the study could not reproduce real-time in-flight pitch transitions.

### Indoor Testing

The experimental setup was operated indoors, where airflow recirculation and surrounding boundaries may influence the measurements.

### RPM Measurement

The accuracy of the laser tachometer introduced uncertainty into the actual operating RPM.

### Load Cell Calibration

Improved calibration could reduce uncertainty in the measured thrust.

### Simplified CFD

The numerical model cannot perfectly reproduce every physical effect present in the experiment.

---

# Future Work

The current system provides a foundation for developing a fully dynamic variable pitch propeller.

## Servo-Actuated Pitch

Replace manual pitch adjustment with servo-based actuation.

This would allow:

```text
Flight Condition
       ↓
Controller
       ↓
Servo
       ↓
Blade Pitch
       ↓
Thrust
```

to be adjusted in real time.

## PID Control

A PID controller could automatically regulate RPM and pitch based on a desired thrust condition.

## Dynamic Testing

Instead of testing only static pitch configurations, the propeller could be tested during continuous pitch transitions.

## Open-Jet Wind Tunnel

Moving the experiment to an open-jet wind tunnel would reduce indoor recirculation effects and provide better aerodynamic control.

## Composite Manufacturing

Future prototypes could use carbon-fibre or composite materials for improved strength-to-weight ratio.

## Blade Optimisation

Further aerodynamic optimisation could incorporate:

* Blade twist
* Airfoil profiling
* Chord distribution
* Pitch distribution
* Tip geometry

The project report specifically identifies servo-based pitch control, PID regulation, open-jet or outdoor testing, composite fabrication, and improved blade profiling as important future directions.

---

# Potential UAV Application

A dynamic pitch propeller could be particularly useful for UAV propulsion because UAV operating conditions can vary significantly throughout a mission.

A future system could use flight-controller data to modify blade pitch depending on:

* Required thrust
* Vehicle speed
* Climb rate
* Battery condition
* Flight phase

For example:

```text
              UAV Flight Controller
                       │
                       ▼
                Required Thrust
                       │
                       ▼
                 Pitch Controller
                       │
                       ▼
                    Servo
                       │
                       ▼
               Variable Pitch Hub
                       │
                       ▼
                    Propeller
```

This could enable the propeller to operate closer to its desired aerodynamic condition across a wider operating envelope.

---

# Technical Stack

### Propeller Design

* OpenProp
* Blade Element / Momentum based design approach
* Parametric geometry development

### CAD

* SolidWorks
* Parametric modelling
* Assembly design
* Mechanical pitch mechanism

### CFD

* SolidWorks Flow Simulation
* Rotating-region simulation
* Aerodynamic force extraction
* Velocity-field analysis
* Stall investigation

### Manufacturing

* FDM 3D printing
* PLA
* Manual assembly
* Blade balancing

### Experimental Testing

* BLDC motor
* ESC
* Laser tachometer
* Load cell
* Digital pitch protractor
* Throttle control

---

# Repository Structure

A clean GitHub structure for the project would be:

```text
variable-pitch-propeller/
│
├── README.md
│
├── design/
│   ├── openprop/
│   ├── blade_geometry/
│   ├── hub/
│   └── pitch_mechanism/
│
├── cad/
│   ├── blades/
│   ├── hub/
│   ├── coupler/
│   └── assembly/
│
├── cfd/
│   ├── pitch_00/
│   ├── pitch_02/
│   ├── pitch_04/
│   ├── ...
│   ├── pitch_28/
│   └── pitch_30/
│
├── fabrication/
│   ├── STL/
│   ├── print_settings/
│   └── assembly/
│
├── experiments/
│   ├── raw_data/
│   ├── processed_data/
│   └── test_setup/
│
├── analysis/
│   ├── thrust_vs_pitch/
│   ├── cfd_vs_experiment/
│   └── stall_analysis/
│
└── documentation/
    └── project_report.pdf
```

---

# Reproducibility

To reproduce the study:

```text
1. Generate the baseline blade geometry
2. Create the variable pitch CAD model
3. Generate pitch configurations from 0° to 30°
4. Set the CFD operating condition to 3000 RPM
5. Run Flow Simulation for each pitch
6. Extract thrust and aerodynamic forces
7. Fabricate the selected geometry
8. Balance the propeller
9. Install the BLDC motor and test rig
10. Set the desired pitch
11. Run the motor at 3000 RPM
12. Record thrust
13. Repeat five times
14. Calculate average thrust
15. Compare CFD and experimental results
16. Identify the optimum pitch region
```

This makes the project reproducible as a combined computational and experimental propulsion study.

---

# Key Results

| Parameter                      |                  Result |
| ------------------------------ | ----------------------: |
| Propeller type                 |  3-blade variable pitch |
| Pitch range                    |               0° to 30° |
| Pitch increment                |                      2° |
| Number of configurations       |                      16 |
| Test / CFD speed               |                3000 RPM |
| Maximum CFD thrust             |                  2.20 N |
| Maximum experimental thrust    |                  3.00 N |
| Optimum pitch                  |                     28° |
| Experimental vs CFD trend      |      Strong correlation |
| Experimental increase over CFD | Approximately 10 to 15% |

The project found that thrust increased with pitch until approximately 28°, followed by saturation or slight reduction at higher pitch.

---

# Key Takeaways

### 1. Variable pitch works

Changing blade pitch produced a clear and measurable change in thrust.

### 2. 28° was the optimum for this configuration

Both simulation and experiment identified 28° as the maximum-thrust configuration at 3000 RPM.

### 3. CFD captured the overall trend

Although the absolute thrust values differed, the computational model correctly captured the trend of increasing thrust followed by saturation.

### 4. Experimental validation matters

The physical test exposed differences that would not be visible from CFD alone.

### 5. The mechanism is a useful starting point

The manually adjustable mechanism demonstrated the feasibility of variable pitch while remaining inexpensive and easy to modify.

### 6. Dynamic actuation is the logical next step

A servo-actuated system with closed-loop control would transform the prototype into a true dynamic propulsion system.

---

# What I Learned

The biggest takeaway from this project was that propulsion design does not stop once the CAD model looks correct.

The actual engineering loop was:

```text
Design
  ↓
Simulate
  ↓
Build
  ↓
Test
  ↓
Compare
  ↓
Understand
  ↓
Improve
```

The difference between CFD and experimental thrust was especially useful because it showed how much the real system can differ from an idealised numerical model.

The project also gave practical experience in connecting aerodynamic design with mechanical constraints.

A variable pitch propeller is not simply a blade with a rotating joint. The hub, blade root, locking mechanism, balance, motor, measurement system, and control system all affect whether the final system works.

That was probably the most valuable part of the project.

---

# Conclusion

This project demonstrated the complete development cycle of a **variable pitch propeller system**, from aerodynamic design and parametric CAD to CFD analysis, physical fabrication, and experimental validation.

A total of 16 pitch configurations were investigated between 0° and 30°.

The simulations and experiments both showed increasing thrust with increasing pitch up to approximately 28°, after which the performance began to saturate.

At 28°:

```text
CFD          → 2.20 N
Experiment   → 3.00 N
```

at 3000 RPM.

Although the experimental results were consistently higher than the simulations, the agreement in the overall trend and optimum pitch provided useful validation of the computational study.

The manually adjustable mechanism successfully demonstrated the feasibility of variable pitch control while keeping the system simple enough to fabricate and test.

The natural next step is a **servo-actuated, closed-loop variable pitch system**, potentially combined with PID control and improved aerodynamic blade optimisation for UAV propulsion.

---

# Project Information

**Project:** Variable Pitch Propeller

**Application:** UAV and aerospace propulsion

**Propeller:** 3-blade open propeller

**Pitch Range:** 0° to 30°

**Pitch Resolution:** 2°

**CFD Software:** SolidWorks Flow Simulation

**CAD:** SolidWorks

**Initial Design:** OpenProp

**Manufacturing:** FDM 3D printing

**Material:** PLA

**Motor:** BLDC

**Test Speed:** 3000 RPM

**Maximum Simulated Thrust:** 2.20 N

**Maximum Experimental Thrust:** 3.00 N

**Optimum Pitch:** 28°

---

# Team

**Aerospace Engineering Department**
RV College of Engineering
Academic Year 2024-2025

---

# Project Website

More details, visuals, and other aerospace engineering projects are available on my portfolio:

**https://aboutkvs.vercel.app/**

---

## License

© 2025 Project Team. All rights reserved.
