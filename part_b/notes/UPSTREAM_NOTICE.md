# Upstream notice

The Part B numerical starting point is the public MOOSE/SubChannel EBR-II SHRT-17 XX09 transient validation case.

Upstream project: https://github.com/idaholab/moose

Upstream validation documentation: https://mooseframework.inl.gov/modules/subchannel/v%26v/EBR-II.html

Benchmark specification: https://publications.anl.gov/anlpubs/2012/06/73647.pdf

The production input in `../run/XX09_SCM_TR17_prod_latest.i` is derived from the public MOOSE input `modules/subchannel/validation/EBR-II/XX09_SCM_TR17.i`. The final run retained the upstream physics model and `SCMFrictionUpgradedChengTodreas`; only the visualization-only `MultiApps` and `Transfers` blocks were removed for the numerical production run.

MOOSE is distributed under the GNU Lesser General Public License v2.1. This repository does not claim authorship of the upstream MOOSE model. Study-specific work is documented in `MODEL_NOTES.md` and the technical report.

The TTC-31 experimental CSV is digitized from the published MOOSE validation figure and is not the original raw experimental dataset.


## License files included with this repository

A copy of the GNU LGPL v2.1 text used by MOOSE is included at `../../third_party/MOOSE_LICENSE_LGPL-2.1.txt`. Repository-level third-party attribution is recorded in `../../THIRD_PARTY_NOTICES.md`. The modified production input itself also carries a prominent upstream/modification notice.
