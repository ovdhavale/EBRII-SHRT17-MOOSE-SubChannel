# EBR-II SHRT-17 XX09 - MOOSE/SubChannel Portfolio Study

Independent thermal-hydraulics portfolio study of the **EBR-II SHRT-17 XX09 instrumented subassembly** using **MOOSE/SubChannel**.

The project is organized as a two-part verification and validation workflow:

- **Part A - pre-transient steady state:** establish the XX09 operating point, perform independent engineering checks, assess axial discretization sensitivity, and compare top-of-core thermocouple predictions with published measurements.
- **Part B - protected loss-of-flow transient:** reproduce the 900 s SHRT-17 transient, interpret the prescribed power and mass-flow forcing, and compare the calculated TTC-31 time history with published experimental measurements digitized from the official MOOSE validation figure.

## Headline results

| Study | Quantity | Result |
|---|---|---:|
| Part A | Bulk outlet temperature | 780.651 K |
| Part A | Assembly pressure drop | 34.063 kPa |
| Part A | Assembly Reynolds number | ~25,886 |
| Part A | TTC-27-35 MAPE | ~2.20% |
| Part B | Post-scram TTC-31 minimum | 660.25 K at 3.56 s |
| Part B | MOOSE TTC-31 peak | 883.09 K at 64.26 s |
| Part B | Digitized experimental peak | 892.12 K at 74.0 s |
| Part B | Peak-temperature difference | -9.03 K |
| Part B | TTC-31 MAE / RMSE | 14.88 K / 17.65 K |

## What I did

### Part A

- Interpreted the XX09 wire-wrapped bundle geometry and steady operating point.
- Performed independent checks for energy balance, mass flux, Reynolds number, and pressure-drop scale.
- Adapted the public MOOSE validation input for compatibility with the MOOSE snapshot available for Part A.
- Added an assembly pressure-drop postprocessor.
- Ran 25-, 50-, and 100-cell axial discretizations.
- Compared predicted TTC-27-35 temperatures with published measurements.
- Generated validation plots and a ParaView temperature-field visualization.

### Part B

- Reproduced the public SHRT-17 transient using MOOSE 2026.09.25 and the upstream upgraded Cheng-Todreas friction closure.
- Separated the numerical production run from the visualization-only MultiApp/Transfers.
- Examined the prescribed reactor-power and XX09 mass-flow histories.
- Extracted the TTC-31 post-scram minimum, reheating peak, and long-term cooling response.
- Digitized the published TTC-31 experimental markers and interpolated the MOOSE solution to those measurement times.
- Calculated peak-temperature error, peak-time error, MAE, and RMSE.
- Produced the Part B validation figures and technical note.

## Repository contents

```text
report/                            # Part A technical note and source
figures/                           # Part A figures
data/                              # Part A validation / mesh data
notes/                             # Part A handwritten media
code/                              # Part A study-specific code / notes
part_b/
  README.md
  report/                          # Part B technical note and source
  figures/                         # transient forcing and TTC-31 validation
  run/                             # reproducible Part B numerical input + forcing files
  results/                         # transient output and comparison data
  notes/                           # model provenance and upstream notice
PROVENANCE.md
```

## Model provenance

The numerical starting point for both parts is the **public MOOSE EBR-II SHRT-17 validation model**. I do **not** claim authorship of the upstream model.

Part A used an older installed MOOSE snapshot and required a documented compatibility substitution from the current upgraded Cheng-Todreas friction object to the available updated Cheng-Todreas object. Part B was rerun in **MOOSE 2026.09.25**, which accepts the upstream `SCMFrictionUpgradedChengTodreas` closure directly; no friction or heat-transfer closure was substituted in the final Part B production run.

The Part B standalone model uses prescribed mass-flow and power histories. It therefore validates the local bundle thermal response to benchmark forcing rather than independently predicting system-level natural circulation.

## Public sources

- Argonne National Laboratory, *Benchmark Specifications and Data Requirements for EBR-II Shutdown Heat Removal Tests SHRT-17 and SHRT-45R*, ANL-ARC-226 Rev.1 (2012):  
  https://publications.anl.gov/anlpubs/2012/06/73647.pdf
- MOOSE Framework, *EBR-II SHRT-17 Validation*:  
  https://mooseframework.inl.gov/modules/subchannel/v%26v/EBR-II.html
- MOOSE `PBSodiumFluidProperties`:  
  https://mooseframework.inl.gov/source/fluidproperties/PBSodiumFluidProperties.html

Full references and limitations are provided in the two technical notes.


## Licensing and third-party attribution

This repository is **not copyright-free**. The upstream MOOSE material remains copyrighted and is used/redistributed under the **GNU LGPL v2.1**. A copy of that license is included at `third_party/MOOSE_LICENSE_LGPL-2.1.txt`, with source-specific details in `THIRD_PARTY_NOTICES.md`.

The inclusion of the MOOSE license does not automatically license the author's independent portfolio prose, figures, calculations, or analysis under LGPL. The repository does not claim authorship of the upstream MOOSE model or benchmark forcing files. The Argonne benchmark PDF and the original published MOOSE validation figure are linked/cited rather than redistributed.

## Scope

This repository documents an **independent portfolio / learning study**, not a full-plant or licensing-grade EBR-II safety analysis. The project is intended to demonstrate reproducible thermal-hydraulics workflow: steady-state initialization, independent engineering checks, numerical sensitivity assessment, transient definition, and comparison with experimental data.
