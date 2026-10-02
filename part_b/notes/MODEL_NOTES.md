# Model provenance and modifications

## Public starting model

This study uses the public MOOSE/SubChannel EBR-II SHRT-17 XX09
transient validation model as the numerical starting point.

Upstream project:
https://github.com/idaholab/moose

Public transient input:
`modules/subchannel/validation/EBR-II/XX09_SCM_TR17.i`

MOOSE is distributed under the GNU Lesser General Public License v2.1.

## Software environment

- MOOSE package: 2026.09.25
- Application: SubChannelApp
- Transient duration: 900 s
- Axial discretization: 50 cells

## Modification made for this study

The production input:

`XX09_SCM_TR17_prod_latest.i`

was derived from the public SHRT-17 input.

The original physics model and
`SCMFrictionUpgradedChengTodreas` closure were retained.

The `MultiApps` and `Transfers` blocks used only for detailed 3-D
visualization were removed from the production calculation to reduce
computational overhead.

No alternative friction or heat-transfer closure was substituted in the
final production run.

## Study-specific work

The work performed in this portfolio study includes:

- reproduction of the public SHRT-17 transient calculation;
- verification of the transient input and software environment;
- separation of the numerical production run from visualization;
- analysis of prescribed power and mass-flow histories;
- extraction of TTC-31 transient quantities;
- identification of post-scram minimum and transient peak;
- digitization of published TTC-31 experimental markers;
- interpolation of the simulation to experimental measurement times;
- calculation of peak error, peak-time error, MAE and RMSE;
- preparation of validation figures and technical documentation.

## Experimental-data note

The TTC-31 experimental values contained in

`SHRT17_TTC31_experiment_digitized.csv`

were digitized from the published MOOSE SHRT-17 validation figure.

They are not original raw experimental measurements and should always
be identified as digitized values when reused.
