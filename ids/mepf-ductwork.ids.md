# IDS – Mechanical Ductwork (D3010)

> Information Delivery Specification for ductwork elements.
> Translate these into a formal `.ids` XML file using
> buildingSMART IDS schema when authoring in Revit/openBIM tools.

## Applicability
- IFC Class: `IfcDuctSegment`, `IfcDuctFitting`
- Stage: Stage 4 (Technical Design)

## Required Properties

| Property Set | Property Name | Data Type | Constraint | Req'd? |
|-------------|---------------|-----------|------------|--------|
| Pset_DuctSegmentTypeCommon | NominalWidth | IfcPositiveLengthMeasure | > 0 | Mandatory |
| Pset_DuctSegmentTypeCommon | NominalHeight | IfcPositiveLengthMeasure | > 0 | Mandatory |
| Pset_DuctSegmentTypeCommon | InsulationThickness | IfcNonNegativeLengthMeasure | ≥ 0 | Mandatory |
| Custom_MEPF | UniClass2015Code | IfcLabel | = `Ss_65_10_30` | Mandatory |
| Custom_MEPF | SystemType | IfcLabel | Not null | Mandatory |
| Custom_MEPF | FlowRate | IfcVolumetricFlowRateMeasure | > 0 | Mandatory (fittings) |

## Notes
- Round ducts: use `NominalWidth` for diameter.
- Insulation thickness of 0 is acceptable for uninsulated ducts —
  it must still be explicitly populated.
