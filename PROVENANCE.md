# Provenance and attribution

This repository separates third-party source material from work performed for the present portfolio study.

## Third-party sources

- The EBR-II SHRT-17 benchmark specification, plant/test data, and experimental basis originate from Argonne National Laboratory.
- The numerical starting model originates from the public MOOSE/SubChannel EBR-II SHRT-17 validation case maintained by the MOOSE project / Idaho National Laboratory.
- Sodium-property correlations and literature methods are cited in the technical report.

No authorship claim is made over these upstream materials.

## Present-study work

The following were produced or carried out for this study:

- software-version compatibility adaptation documented in `code/model_changes.md`;
- added assembly pressure-drop postprocessing;
- 25/50/100-cell mesh-sensitivity runs;
- independent engineering checks and derived quantities;
- error metrics and comparison tables;
- validation and mesh-sensitivity plots;
- ParaView visualization;
- handwritten geometry interpretation and engineering calculations;
- technical report and repository documentation.

The full public benchmark PDF and full upstream MOOSE validation input are intentionally linked rather than copied into this repository.
