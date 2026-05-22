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

## Background

Eye movement is controlled by the coordinated action of extraocular muscles. This repository provides a simplified computational implementation inspired by biomechanical modelling of the oculomotor system.

The model is based on the following reference:

> A. D. Polpitaya and B. K. Ghosh, “Modeling the dynamics of oculomotor system in three dimensions,”  
> 42nd IEEE International Conference on Decision and Control, 2003, pp. 6418–6422.  
> DOI: 10.1109/CDC.2003.1272353

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

## Installation

Clone the repository using Git:

```bash
git clone https://github.com/Hesam-lab/eye-model.git
```

Then open the project folder in MATLAB.

## How to Run

In MATLAB, navigate to the repository folder and run:

```matlab
main
```

The script will simulate the gaze movement and generate several figures.

## Input Parameters

The initial and final gaze vectors are defined in `main.m`:

```matlab
X1 = [1; 1.3; 2];   % Initial gaze vector
X2 = [1; 3; 0.7];   % Final gaze vector
```

You can modify these values to simulate different gaze transitions.

For example:

```matlab
X1 = [1; 0; 0];
X2 = [0; 1; 0];
```

Both vectors should be non-zero 3D column vectors.

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

## Example Output

After running `main.m`, MATLAB will display plots showing angular velocity changes and the movement of the gaze vector in 3D space.

The final 3D plot uses:

```matlab
quiver3
```

to visualise the direction of gaze movement.

## Suggested Repository Improvements

Future versions of this repository could include:

- Refactoring `main.m` into separate reusable functions
- Adding detailed comments for each model parameter
- Adding example output figures to the README
- Adding unit tests for mathematical components
- Validating the simulation against the original published model
- Adding a `src/` folder for model functions
- Adding an `examples/` folder for different gaze movement scenarios

A possible future structure could be:

```text
eye-model/
│
├── main.m
├── README.md
├── LICENSE
├── .gitignore
│
├── src/
│   ├── compute_rotation.m
│   ├── generate_activation.m
│   ├── generate_torque.m
│   └── simulate_eye_movement.m
│
└── examples/
    └── example_gaze_transition.m
```

## Known Limitations

- The current implementation is a simplified research simulation.
- All model parameters are fixed inside `main.m`.
- The code has not yet been modularised into separate functions.
- The model has not yet been validated against experimental eye-tracking data.
- The simulation is not currently designed for real-time gaze control.
- Further checking may be needed for the rotation matrix update step.

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

## License

No license has been added yet. If you want others to reuse, modify, or distribute this code, consider adding an open-source license such as the MIT License.
