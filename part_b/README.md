# Part B - SHRT-17 protected loss-of-flow transient

This folder extends the Part A steady-state XX09 study to the **900 s EBR-II SHRT-17 protected loss-of-flow transient** using **MOOSE/SubChannel**.

The public SHRT-17 model is used as the numerical starting point. The final production run was executed with **MOOSE 2026.09.25** and retained the current `SCMFrictionUpgradedChengTodreas` closure. The visualization-only `MultiApps` and `Transfers` blocks were removed from the production input to reduce computational overhead.

## Main results

| Quantity | Result |
|---|---:|
| Pre-transient TTC-31 | 813.54 K |
| Post-scram minimum | 660.25 K at 3.56 s |
| MOOSE TTC-31 peak | 883.09 K at 64.26 s |
| Digitized experimental peak | 892.12 K at 74.0 s |
| Peak-temperature difference | -9.03 K |
| Peak-time difference | -9.74 s |
| TTC-31 MAE | 14.88 K |
| TTC-31 RMSE | 17.65 K |
| Final TTC-31 at 900 s | 696.57 K |
| Final mass flow | 0.06353 kg/s |
| Final power | 5.94 kW |

## Physical interpretation

Immediately after the scram, power falls much faster than coolant flow, so TTC-31 cools rapidly. Continued pump coastdown then reduces the imposed XX09 mass flow to a very small fraction of its initial value while decay power remains finite; TTC-31 therefore reheats and reaches a second peak. At later times, continued decay-power reduction produces the long cooling tail.

The standalone SubChannel calculation uses **prescribed power and mass-flow histories**. It therefore evaluates the bundle-scale thermal response to benchmark forcing; it does not independently predict the system-level pump coastdown or natural-circulation flow.

## Experimental-data note

The TTC-31 experimental markers in this repository were **digitized from the published MOOSE SHRT-17 validation figure**. They are not raw experimental measurements. The reported MAE, RMSE, and peak comparison therefore include small digitization uncertainty.

## Folder contents

```text
report/
  EBRII_SHRT17_PartB_Report.pdf
  source/                         # Overleaf/LaTeX source
figures/
  SHRT17_TTC31_validation.png     # present MOOSE run vs digitized experiment
  SHRT17_transient_forcing.png    # normalized prescribed power and flow
run/
  XX09_SCM_TR17_prod_latest.i
  pin_power_profile61_uniform.txt
  power_history_SHRT17.csv
  massflow_SHRT17.csv
results/
  XX09_SCM_TR17_prod_latest_out.csv
  SHRT17_TTC31_experiment_digitized.csv
  SHRT17_TTC31_validation_comparison.csv
  SHRT17_PartB_summary.txt
notes/
  MODEL_NOTES.md
  UPSTREAM_NOTICE.md
```

## Reproduce the production run

Use a MOOSE installation that provides `SubChannelApp` and `SCMFrictionUpgradedChengTodreas`. The study run used MOOSE package **2026.09.25**.

From `part_b/run/`:

```bash
moose --app SubChannelApp -i XX09_SCM_TR17_prod_latest.i
```

The production input is intentionally the numerical-only case; the detailed visualization MultiApp was removed.

## Public sources

- Argonne National Laboratory, *Benchmark Specifications and Data Requirements for EBR-II Shutdown Heat Removal Tests SHRT-17 and SHRT-45R*, ANL-ARC-226 Rev.1 (2012):  
  https://publications.anl.gov/anlpubs/2012/06/73647.pdf
- MOOSE Framework, *EBR-II SHRT-17 Validation*:  
  https://mooseframework.inl.gov/modules/subchannel/v%26v/EBR-II.html
- MOOSE `SCMFrictionUpgradedChengTodreas`:  
  https://mooseframework.inl.gov/moose/source/scmclosures/SCMFrictionUpgradedChengTodreas.html

Full references and limitations are given in the technical report.
