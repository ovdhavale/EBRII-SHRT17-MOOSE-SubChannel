# EBR-II SHRT-17 XX09 — MOOSE/SubChannel Part A

Independent thermal-hydraulics portfolio study of the **pre-transient steady state** of the EBR-II SHRT-17 XX09 instrumented subassembly using **MOOSE/SubChannel**.

The aim of Part A was to reproduce and understand the public steady-state validation case rather than treat it as a black box. The work combines independent engineering checks, a small axial mesh-sensitivity study, comparison with published thermocouple measurements, and ParaView post-processing.

## Main results

| Quantity | 50-cell reference case |
|---|---:|
| Bulk outlet temperature | 780.651 K |
| Assembly pressure drop | 34.063 kPa |
| Assembly Reynolds number | ~25,886 |
| TTC-27–35 MAPE | ~2.20% |

The 25/50/100-cell sensitivity study showed a **0.005 K** change in outlet temperature and about **0.22%** change in pressure drop between 50 and 100 axial cells.

## What I did

- Interpreted the XX09 wire-wrapped bundle geometry and steady-state operating point.
- Performed independent checks for energy balance, mass flux, Reynolds number, and pressure-drop scale.
- Adapted the public MOOSE validation input for compatibility with the MOOSE snapshot available in my environment.
- Added an assembly pressure-drop postprocessor.
- Ran 25-, 50-, and 100-cell axial discretizations.
- Compared predicted TTC-27–35 temperatures with published measurements.
- Generated original validation plots and ParaView temperature-field visualizations.

## Repository contents

```text
report/
  EBRII_SHRT17_PartA_Report.pdf   # 4-page technical note
  source/                         # Overleaf/LaTeX source
figures/
  temperature_field.png           # ParaView visualization
  ttc_validation.png              # experiment vs MOOSE
notes/
  geometry.png                     # handwritten geometry interpretation
  hand_calculations.png            # handwritten engineering checks
data/
  mesh_sensitivity.csv
  ttc_validation.csv
code/
  pressure_drop_postprocessor.i    # postprocessor added in this study
  model_changes.md                 # compatibility/modification notes
PROVENANCE.md
```

## Model provenance

The numerical starting point was the **public MOOSE EBR-II SHRT-17 validation model**. I do **not** claim authorship of that upstream model. This repository intentionally does not redistribute the full upstream validation input; instead, it documents the changes made for this study and links to the original public source.

The current public input uses `SCMFrictionUpgradedChengTodreas`. The MOOSE snapshot used for this work exposed `SCMFrictionUpdatedChengTodreas`, so that available closure was used as a documented software-version compatibility substitution.

## Public sources

- Argonne National Laboratory, *Benchmark Specifications and Data Requirements for EBR-II Shutdown Heat Removal Tests SHRT-17 and SHRT-45R*, ANL-ARC-226 Rev.1 (2012):  
  https://publications.anl.gov/anlpubs/2012/06/73647.pdf
- MOOSE Framework, *EBR-II SHRT-17 Validation*:  
  https://mooseframework.inl.gov/modules/subchannel/v%26v/EBR-II.html
- MOOSE `PBSodiumFluidProperties`:  
  https://mooseframework.inl.gov/source/fluidproperties/PBSodiumFluidProperties.html
- SAS4A/SASSYS-1 sodium-property documentation:  
  https://sas-doc.nse.anl.gov/5.7.2/Part04/Ch12/12.13.html

Full references are provided in the technical note.

## Scope

This is a **portfolio / learning study**, not a full-plant or licensing-grade EBR-II safety analysis. Part A covers the pre-transient steady state. A future Part B is intended to extend the work toward the SHRT-17 protected loss-of-flow transient.
