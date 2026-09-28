# Changes made relative to the public MOOSE validation input

The public MOOSE EBR-II SHRT-17 validation model is the upstream numerical starting point. The full upstream file is not redistributed here; see the MOOSE validation link in the repository README.

## 1. Software-version compatibility

Public/current model setting:

```text
type = SCMFrictionUpgradedChengTodreas
```

Setting available in the MOOSE snapshot used for this study:

```text
type = SCMFrictionUpdatedChengTodreas
```

This substitution was made only to run the public validation model with the installed snapshot and is reported explicitly in the technical note.

## 2. Assembly pressure-drop postprocessor

The following postprocessor was added for the present study:

```text
[DP_assembly]
  type = SubChannelDelta
  variable = P
  execute_on = 'TIMESTEP_END'
[]
```

## 3. Axial mesh-sensitivity cases

The reference model uses 50 axial cells. Additional runs were created with:

```text
n_cells = 25
n_cells = 50
n_cells = 100
```

The same axial cell count was applied to both the subchannel and duct mesh generators for each sensitivity case.
