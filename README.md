# Eye Movement Model

This repository contains a MATLAB simulation of three-dimensional eye movement control based on Hill-type muscle dynamics and Listing’s law.

The model simulates the transition between an initial gaze vector and a final gaze vector, using rotational dynamics, activation generation, torque generation, and muscle force relationships.

## Overview

The code models aspects of the oculomotor system, including:

- 3D gaze vector transformation
- Eye rotation dynamics
- Muscle activation generation
- Torque generation
- Hill-type muscle force modelling
- Angular velocity changes during simulated movement

The implementation is based on the following reference:

> A. D. Polpitaya and B. K. Ghosh, “Modeling the dynamics of oculomotor system in three dimensions,” 42nd IEEE International Conference on Decision and Control, 2003, pp. 6418–6422, doi: 10.1109/CDC.2003.1272353.

## Repository Structure

```text
eye-model/
│
├── main.m          # Main MATLAB script for simulating 3D eye movement
├── README.md      # Project documentation
└── .gitattributes
