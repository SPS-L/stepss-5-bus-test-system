# 5-Bus Test System - STEPSS Dynamic Simulation Tutorial

This repository contains startup material for dynamic simulation studies with
the [STEPSS](https://stepss.sps-lab.org/) platform on a 5-bus system. The
simulations can be run either from Python with the PyRAMSES API (used in the
example notebooks) or through the STEPSS Java interface. The material is
designed for the **Control and Operation of Electric Power Systems (EEN452)**
course at Cyprus University of Technology.

## Overview

The assignment focuses on understanding generator and controller behavior during
disturbances, and on interpreting dynamic responses (frequency, voltage, rotor
angle, and power). The test system includes:

- One synchronous generator with detailed machine, governor, and AVR models
- Composite load behavior (impedance and motors)
- External grid representation for disturbance studies
- Multiple operating points and disturbance scenarios

## Course Context

This material is part of the
[EEN452 course](https://sps-lab.org/courses/een452/) taught by Dr. Petros
Aristidou at the Sustainable Power Systems Lab.

## Assignment and Deliverables

The full assignment brief is provided in:

- [assignment.pdf](./assignment.pdf)

According to the assignment document, students must submit:

- A report (PDF) addressing all requested case-study questions, or equivalent
	answers in notebook Markdown cells
- The working notebook implementation (`.ipynb`) and all required input files

This assignment contributes **10%** of the final grade. Late submissions are
penalized according to the assignment rules.

## Repository Files

- **`Transient Angle.ipynb`**: Example notebook for transient angle studies
- **`Case 2.ipynb`**: Example notebook implementation for Assignment Case 2
- **`dyn.dat`**: Dynamic model data
- **`lf1.dat`, `lf1solv.dat`**: Operating point 1 load-flow and solved state
- **`lf2.dat`, `lf2solv.dat`**: Operating point 2 load-flow and solved state
- **`obs.dat`**: Observable definitions for post-processing
- **`solveroptions.dat`**: Solver and simulation options
- **`nothing.dst`**: Empty disturbance file
- **`assignment.pdf`**: Official assignment handout

## Experimental Cases

The assignment defines seven case studies (Cases 1-7), including:

- Set-point changes (active power and voltage)
- External system voltage dips
- Fault-and-clear events on line 1-3
- Line tripping scenarios
- Analysis of controllers (governor, AVR, PSS) and load recovery behavior

Use the notebooks as starting points and extend/adapt them to implement all
required cases from [assignment.pdf](./assignment.pdf).

## Getting Started

The test case can be run with either of the two STEPSS front-ends; both consume
the same data files.

### Option A: PyRAMSES (Python, used in the notebooks)

Prerequisites: access to the course JupyterHub platform or a local JupyterLab,
with PyRAMSES available in the notebook environment, and basic familiarity with
Python and power system dynamics. For a local environment:

```bash
pip install matplotlib scipy numpy mkl jupyter ipython pyramses
```

1. Open this folder in JupyterHub or JupyterLab.
2. Start with `Transient Angle.ipynb` or `Case 2.ipynb`.
3. Run cells sequentially.
4. Modify operating point files and disturbances to implement each assignment
	 case.
5. Plot and comment on the requested observables.

### Option B: STEPSS Java interface

In the [STEPSS Java interface](https://github.com/SPS-L/stepss-java-ui), create
a simulation with:

- **Data files**: `dyn.dat`, `lf1solv.dat` (or `lf2solv.dat` for operating
	point 2), and `solveroptions.dat`
- **Disturbance file**: `nothing.dst`, or a copy extended with the disturbance
	records of the case under study
- **Observables file**: `obs.dat`

Run the simulation and inspect the requested observables with the built-in
plotting tools. Disturbances that the notebooks apply interactively (set-point
changes, faults, line trips) are entered as timed records in the disturbance
file instead.

## References

- [STEPSS documentation](https://stepss.sps-lab.org/) (data formats, PyRAMSES, and the Java interface)
- [STEPSS Java interface](https://github.com/SPS-L/stepss-java-ui)
- [EEN452 course page](https://sps-lab.org/courses/een452/)
- [JupyterHub 5-bus workspace](https://sps.cut.ac.cy/jhub-5-bus)
- Original exercises by
	[Prof. Thierry Van Cutsem](https://thierryvancutsem.github.io/)

## Support

For STEPSS technical issues, consult the
[official documentation](https://stepss.sps-lab.org/). For course-related
questions, use the course communication channels.

---

![5-bus system one-line diagram](./5_bus_oneline.png)

*This material is part of the EEN452 course curriculum at Cyprus University of
Technology, developed by the Sustainable Power Systems Lab.*
