# Variable Pitch Propeller Test Rig

Design, CFD analysis, 3D-printed prototype, and experimental thrust testing of a manually adjustable variable-pitch propeller.

## Overview

Fixed-pitch propellers are only efficient at one operating point. This project builds a variable-pitch propeller where blade pitch can be set mechanically (rack-and-pinion style hub) and tests how thrust changes with pitch angle, from 0 to 30 degrees in steps, using both CFD and a physical test bench.

Work was done as a group project (5 students, Aerospace Propulsion course, RVCE) covering the full pipeline: aerodynamic design, CAD, CFD validation, fabrication, and instrumented testing.

## How it works

**Aerodynamic design**: blade geometry (twist distribution, chord, radius) generated using Blade Element Momentum Theory (BEMT) via OpenProp, then parameterized in SolidWorks.

**CFD**: each pitch configuration (16 angles, 0 to 30 degrees) simulated in SolidWorks Flow Simulation to get predicted thrust and to check for stall onset at low and high pitch extremes.

**Pitch mechanism**: a rack-and-pinion hub (`cad/hub.SLDPRT`, `cad/hub1.SLDPRT`, `cad/coupler.SLDPRT`) lets blade pitch be set manually and locked before a test run, not actuated in real time.

**Fabrication**: blades and hub 3D printed in PLA (`cad/print1 - CONT-1.STL`, `cad/print1 - string-1.STL`, etc.).

**Test bench**: brushless DC motor spins the prop, with three Arduino sketches handling instrumentation:
- `arduino-code/tachometer.ino` — RPM from an IR/optical blade-interrupt sensor, interrupt-driven with per-rotation smoothing
- `arduino-code/loadcell.ino` / `loadcell_caliberation.ino` — thrust from an HX711 load cell amplifier, with a serial calibration routine (tare, known-mass calibration, EEPROM storage of the cal factor)
- `arduino-code/rpm_control.ino` / `pitch_control_servo.ino` — motor speed / servo position set from a potentiometer

Each pitch angle was locked in mechanically, then RPM and thrust were logged from the load cell and tachometer.

## Results

Max thrust of 3.00 N observed at 28 degrees pitch, closely matching the CFD prediction. Thrust increases with pitch angle until aerodynamic stall effects start to reduce it. Experimental data tracked the simulated trend well across the tested range.

![CAD model](media/images/cad_model.jpeg)
![Pitch mechanism](media/images/rack_pinion_pitch_mechanism.jpg)
![CFD flow simulation](media/images/cfd.jpeg)
![Load cell setup](media/images/loadcell.jpg)
![Tachometer readout](media/images/tachometer.png)
![Thrust vs pitch angle](media/images/performance_plot.png)

Video: `media/cad_pitch.mp4` (pitch mechanism CAD), `media/pitch_mechanism.mp4`, `media/complete_working_model.mp4` (full test run).

Full writeup with methodology, CFD setup, and result plots: `docs/project_report.pdf`.

## Limitations

- Pitch is set manually between runs, not adjustable in flight/in real time (no closed-loop pitch actuator).
- Only 16 discrete pitch angles tested, all at a single fixed RPM range from the bench motor.
- No wind-tunnel forward-flow testing, static thrust only.
- `python_output.png` in `media/images/` implies a Python data-processing step for the plots, but no Python script is checked into the repo.

## Repo layout

```
arduino-code/   RPM control, pitch servo control, tachometer, load cell + calibration
cad/            SolidWorks parts/assemblies and STLs for the hub, coupler, blades
docs/           full project report (PDF)
media/          photos, plots, and videos of the test rig and results
```

## Note

No matching page exists on the portfolio website for this project; this README is the primary documentation.
