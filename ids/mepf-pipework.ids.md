# IDS – Plumbing Pipework (D2010)

> Information Delivery Specification for pipework elements.

## Applicability
- IFC Class: `IfcPipeSegment`, `IfcPipeFitting`
- Stage: Stage 4 (Technical Design)

## Required Properties

| Property Set | Property Name | Data Type | Constraint | Req'd? |
|-------------|---------------|-----------|------------|--------|
| Pset_PipeSegmentTypeCommon | NominalDiameter | IfcPositiveLengthMeasure | > 0 | Mandatory |
| Pset_PipeSegmentTypeCommon | Material | IfcLabel | Not null | Mandatory |
| Custom_MEPF | UniClass2015Code | IfcLabel | = `Ss_70_50_16` | Mandatory |
| Custom_MEPF | SystemType | IfcLabel | Not null | Mandatory |
| Custom_MEPF | InsulationType | IfcLabel | Not null when SystemType ∈ {HWS, CWS} | Conditional |

## Notes
- Conditional insulation rule: if `SystemType` is `HWS` or `CWS`,
  `InsulationType` must not be null.
