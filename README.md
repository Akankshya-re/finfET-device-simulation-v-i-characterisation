# FinFET Device Simulation and V-I Characterisation

A semiconductor device simulation project focused on the structural modelling of a 20 nm gate-length Fin Field-Effect Transistor (FinFET) and the study of its current–voltage (I–V) characteristics using Silvaco ATLAS / DeckBuild.

## Overview

Fin Field-Effect Transistors (FinFETs) are three-dimensional transistor structures in which the gate controls a thin silicon fin from multiple sides. This multi-gate configuration provides improved electrostatic control over the channel compared with conventional planar MOSFET structures.

This project focuses on developing a 3D FinFET structure, defining its source, channel, drain, gate oxide, gate electrodes, and doping profiles, and preparing the device for electrical characterisation through device simulation.

The project uses Silvaco ATLAS / DeckBuild for semiconductor device modelling and TonyPlot for visualisation of the device structure and simulation results.

## Objectives

- Develop a three-dimensional FinFET device structure.
- Define the source, channel, and drain regions with specified dimensions and doping concentrations.
- Model the gate oxide and multi-sided gate arrangement.
- Configure electrical contacts and device bias conditions.
- Obtain drain current versus drain voltage (I_D–V_DS) characteristics at multiple gate voltages.
- Examine the relationship between device geometry, gate bias, and drain current.
- Document the device construction and simulation workflow.

## Device Specifications

| Parameter | Specification |
|---|---|
| Device type | 3D FinFET |
| Source length | 20 nm |
| Gate length | 20 nm |
| Drain length | 20 nm |
| Total source-to-drain length | 60 nm |
| Silicon fin width | 20 nm |
| Silicon fin height | 20 nm |
| Gate dielectric | Silicon dioxide (SiO₂) |
| Gate oxide thickness | 4 nm |
| Source doping | n-type, 1 × 10¹⁸ cm⁻³ |
| Channel doping | p-type, 1 × 10¹⁷ cm⁻³ |
| Drain doping | n-type, 1 × 10¹⁸ cm⁻³ |
| Simulation environment | Silvaco ATLAS / DeckBuild |
| Visualisation | TonyPlot |

*Note: These are the intended parameters of the device model. Confirm the final simulated geometry, contact arrangement, and material regions in the generated structure before treating them as verified results.*

## Device Structure

The device is divided into three longitudinal sections:

1. **Source:** A 20 nm-long n-type silicon region.
2. **Channel:** A 20 nm-long p-type silicon region controlled by the gate.
3. **Drain:** A 20 nm-long n-type silicon region.

The silicon fin has a nominal cross-section of 20 nm × 20 nm. A silicon dioxide dielectric separates the gate from the channel. The intended tri-gate arrangement places the gate over the top surface and along both sidewalls of the fin.

The overall nominal source-to-drain length is 60 nm, excluding external contact structures.

## Methodology

### 1. Mesh Definition

A three-dimensional computational mesh is defined along the device's longitudinal, vertical, and lateral directions. A finer mesh is intended near the gate, channel, and dielectric interfaces to resolve the electric field and carrier distributions.

### 2. Region and Material Definition

The silicon regions representing the source, channel, and drain are defined separately. Silicon dioxide regions are assigned to the gate dielectric, and gate material regions are specified for the intended multi-sided gate geometry.

### 3. Doping Configuration

The source and drain are assigned n-type doping, while the channel is assigned p-type doping. These profiles define the intended n-channel transistor configuration.

### 4. Electrode and Contact Definition

Source, drain, and gate electrodes are defined to apply electrical biases. The top and side gate surfaces are intended to operate as a common gate terminal.

### 5. Structure Export and Inspection

The generated device structure is exported to a Silvaco structure file and inspected using a compatible TonyPlot viewer. The geometry and electrode placement should be verified before electrical simulation.

### 6. Electrical Characterisation

After the structure and contacts have been validated, the device is biased at selected gate voltages. The drain voltage is swept while the drain current is recorded to obtain the output characteristics.

The resulting I_D–V_DS curves can be compared across gate voltages to study transistor behaviour.

## Simulation Files

| File | Description |
|---|---|
| `decks/finfet_20nm_structure.in` | Defines the 3D mesh, material regions, electrodes, doping, and structure output. |
| `decks/finfet_20nm_iv.in` | Contains the biasing procedure and I–V characterisation setup. |
| `docs/simulation_workflow.md` | Provides the procedure for running and inspecting the simulation. |

## Results and Analysis

This section should be completed after successful execution of the simulation decks.

### 3D Device Structure

Insert the verified 3D structure screenshot here.

**Image:** `images/finfet_3d_structure.png`

The image should show the silicon fin, gate region, gate dielectric, and source/drain arrangement. Use a cross-sectional view or separate views if necessary to make the dimensions and materials distinguishable.

### Drain Current–Voltage Characteristics

Insert the actual simulated output curves here.

**Image:** `results/finfet_output_characteristics.png`

The output characteristics should show drain current (I_D) against drain-to-source voltage (V_DS) for the selected gate-to-source voltages (V_GS).

### Results Table

| V_GS (V) | V_DS (V) | I_D (A) | Observation |
|---:|---:|---:|---|
| To be filled | To be filled | To be extracted | To be completed |
| To be filled | To be filled | To be extracted | To be completed |
| To be filled | To be filled | To be extracted | To be completed |

Numerical values and observations should be entered only after the simulation has completed successfully and the results have been extracted.

## How to Run

1. Install and configure a compatible version of Silvaco ATLAS / DeckBuild.
2. Clone or download this repository.
3. Open `decks/finfet_20nm_structure.in` in DeckBuild.
4. Execute the structure deck and resolve any version-specific syntax or geometry errors.
5. Inspect the generated structure using the available 3D-capable TonyPlot viewer.
6. Verify that the gate dielectric, gate electrodes, source/drain contacts, and material regions are correctly defined.
7. Run `decks/finfet_20nm_iv.in` after ensuring that it loads or recreates the validated device structure and uses compatible electrode names.
8. Inspect the generated I–V data and plots.
9. Record the simulation conditions, extracted values, and observations in the results section.

Exact commands may require adjustment for the installed Silvaco version.

## Tools and Technologies

- **Silvaco ATLAS:** Semiconductor device simulation.
- **Silvaco DeckBuild:** Simulation deck development and execution.
- **TonyPlot:** Device structure and electrical-result visualisation.
- **Semiconductor device physics:** MOSFET/FinFET structure, doping, gate control, and current–voltage characterisation.

## Limitations

- The accuracy of the simulation depends on mesh quality, material models, doping profiles, boundary conditions, and contact definitions.
- A nominal 20 nm geometry does not by itself establish that the simulated device has the intended dimensions; the generated structure must be inspected.
- Electrical results are meaningful only after the structure and terminal connections have been validated.
- Simulated characteristics are model-dependent and should not be presented as measured experimental data.

## Future Improvements

- Validate and refine the three-dimensional mesh near the gate and channel.
- Investigate the influence of gate oxide thickness and fin dimensions.
- Compare output characteristics at different gate voltages.
- Extract threshold voltage, transconductance, and on/off current ratio where the simulation supports reliable extraction.
- Study the effects of different channel doping concentrations and gate work functions.
- Compare device performance across alternative FinFET geometries.


## Disclaimer

This repository is intended for academic learning and semiconductor device simulation. Results depend on the implemented model, simulator version, and simulation settings. Verify all geometry and electrical results before drawing conclusions.
