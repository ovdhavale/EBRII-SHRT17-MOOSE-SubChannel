# Third-party notices

This portfolio repository contains or redistributes a small number of files derived from, or copied from, the public **MOOSE Framework** EBR-II SHRT-17 validation case.

## MOOSE Framework / Idaho National Laboratory

- Upstream project: https://github.com/idaholab/moose
- Official site: https://mooseframework.inl.gov
- Upstream SHRT-17 validation documentation: https://mooseframework.inl.gov/modules/subchannel/v%26v/EBR-II.html
- Upstream transient input: `modules/subchannel/validation/EBR-II/XX09_SCM_TR17.i`
- Upstream license: GNU Lesser General Public License v2.1 (LGPL-2.1)
- Upstream copyright notice: https://github.com/idaholab/moose/blob/next/COPYRIGHT
- Upstream license text: https://github.com/idaholab/moose/blob/next/LICENSE

A verbatim copy of the GNU LGPL v2.1 license text is included at:

`third_party/MOOSE_LICENSE_LGPL-2.1.txt`

MOOSE source files identify the project as licensed under LGPL 2.1 and direct users to the upstream `COPYRIGHT` and `LICENSE` files. The inclusion of the LGPL text here is for the redistributed/derived MOOSE material; it does **not** by itself place the author's independent portfolio prose, figures, calculations, or analysis under LGPL.

### MOOSE-derived / redistributed material in this portfolio

Part B contains an adapted production input derived from the public MOOSE SHRT-17 validation input, together with benchmark forcing/profile files used by that input. The adapted input retains the upstream physics model and `SCMFrictionUpgradedChengTodreas` closure. The study modification removes visualization-only `MultiApps` and `Transfers` blocks from the numerical production input. The modified input carries a notice at its top identifying the upstream source and the modification date.

The same production input and benchmark files may also appear under the Part B report source tree for reproducibility. See `part_b/notes/UPSTREAM_NOTICE.md` and `part_b/notes/MODEL_NOTES.md` for the exact study provenance.

## Argonne SHRT-17 benchmark material

The Argonne benchmark specification is **referenced and linked**, not redistributed as a full PDF in this repository:

https://publications.anl.gov/anlpubs/2012/06/73647.pdf

The TTC-31 experimental CSV in Part B was digitized from the published MOOSE validation figure and is explicitly labelled as digitized data rather than original raw experimental measurements. The original published validation figure is not redistributed in this repository.

## Attribution statement

This repository does not claim authorship of the upstream MOOSE model, MOOSE benchmark input histories, or Argonne benchmark material. Study-specific execution, numerical checks, post-processing, digitization, validation metrics, recreated figures, interpretation, and technical documentation are identified separately as portfolio work.
