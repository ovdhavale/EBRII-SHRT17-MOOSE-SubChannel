# Provenance and attribution

This repository is an independent portfolio study built around public EBR-II SHRT-17 benchmark material and public MOOSE/SubChannel validation inputs.

## External sources

- **Argonne National Laboratory** provides the EBR-II SHRT-17 / SHRT-45R benchmark specification and experimental context.
- **MOOSE Framework / Idaho National Laboratory** provides the public EBR-II SHRT-17 SubChannel validation model, input histories, fluid-property implementation, closure implementations, and validation documentation.

I do not claim authorship of those upstream materials.

## Part A study-specific work

Part A includes independent execution and interpretation, hand calculations, an assembly pressure-drop postprocessor, axial mesh-variation runs, error metrics, validation plots, and ParaView visualization. The public upstream validation input is not redistributed in the Part A root folders; changes are documented separately.

## Part B study-specific work

Part B includes execution of the 900 s transient in MOOSE 2026.09.25, removal of visualization-only MultiApp/transfer blocks for the numerical production run, forcing-history analysis, extraction of TTC-31 transient features, digitization of published experimental markers, code-to-data error metrics, figures, and the technical note.

The Part B production input is derived from the public MOOSE SHRT-17 transient input. The upstream physics model and `SCMFrictionUpgradedChengTodreas` closure are retained. See `part_b/notes/UPSTREAM_NOTICE.md` and `part_b/notes/MODEL_NOTES.md`.

## Experimental-data note

The Part B TTC-31 experimental CSV is digitized from a published MOOSE validation figure. It is **not** the original raw experimental dataset and should be described as digitized whenever reused.

## Key public references

- https://publications.anl.gov/anlpubs/2012/06/73647.pdf
- https://mooseframework.inl.gov/modules/subchannel/v%26v/EBR-II.html
- https://github.com/idaholab/moose


## License hygiene

Redistributed or adapted MOOSE material is accompanied by the upstream GNU LGPL v2.1 license text at `third_party/MOOSE_LICENSE_LGPL-2.1.txt` and by `THIRD_PARTY_NOTICES.md`. The adapted Part B production input contains an explicit header identifying the upstream file, modification date, and study-specific change. The upstream MOOSE copyright notice remains available at https://github.com/idaholab/moose/blob/next/COPYRIGHT.

The LGPL notice applies to the MOOSE-derived/redistributed material; it is not presented as a blanket license for the author's independent portfolio prose, figures, calculations, or analysis.
