# Eye Movement Model

A MATLAB implementation for simulating three-dimensional eye movement control based on a Hill-type muscle model and Listing’s law.

This repository provides a simple computational model of gaze transition between two 3D gaze vectors. The model includes gaze vector rotation, muscle activation, torque generation, and angular velocity changes during simulated eye movement.

## Overview

The code simulates an ocular motor model for controlling gaze in three dimensions. It starts from an initial gaze vector and estimates the movement toward a final gaze vector using rotational dynamics and muscle-related parameters.

The current implementation is contained in a single MATLAB script:

```text
main.m
```

The simulation produces angular velocity plots and a 3D visualisation of gaze vector movement.

## Features

- Simulation of 3D gaze movement
- Initial and final gaze vector definition
- Rotation-based gaze transformation
- Activation generation
- Torque generation
- Hill-type muscle force modelling
- Angular velocity visualisation
- 3D gaze vector movement plot

## Repository Structure

```text
eye-model/
│
├── main.m          # Main MATLAB script for simulating 3D eye movement
├── README.md       # Project documentation
└── .gitattributes
```

## Requirements

This project requires MATLAB.

Recommended environment:

- MATLAB R2020a or later

No additional MATLAB toolbox is currently required for running the main script.

## Outputs

The script generates the following plots:

1. Angular velocity changes around the x-axis
2. Angular velocity changes around the y-axis
3. Angular velocity changes around the z-axis
4. 3D movement of the gaze vector

These plots help visualise how the model estimates gaze movement over simulation iterations.

## Main Model Components

### 1. Gaze Vector Definition

The model starts with an initial gaze vector and a final gaze vector:

```matlab
X1 = [1; 1.3; 2];
X2 = [1; 3; 0.7];
```
You can modify these values to simulate different gaze transitions.

### 2. Rotation Calculation

The angle between the two gaze vectors is calculated using the dot product:

```matlab
theta = acos(num / det);
```

This angle is then used to define rotation matrices and rotation-related variables.

### 3. Activation Generator

Muscle activation values are generated based on the rotation vector:

```matlab
A = abs([a1; a2; a3]);
```

### 4. Torque Generator

The model includes simplified parameters for:

- Eyeball radius
- Viscosity coefficient
- Elastic coefficient
- Moment of inertia
- Muscle length
- Muscle velocity
- Muscle force
- Torque

### 5. Eye Movement Simulation

The simulation updates angular velocity, torque, and gaze direction iteratively.

## Citation

If you use or refer to this code, please cite the original model paper:

```text
Polpitaya, A. D., and Ghosh, B. K. (2003).
Modeling the dynamics of oculomotor system in three dimensions.
42nd IEEE International Conference on Decision and Control, 6418–6422.
doi: 10.1109/CDC.2003.1272353
```

## Author

**Hesam Shokouh Alaei**
