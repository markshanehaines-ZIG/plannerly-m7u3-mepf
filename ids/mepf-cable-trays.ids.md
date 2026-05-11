# IDS – Electrical Cable Trays (E3010)

> Information Delivery Specification for cable tray elements.

## Applicability
- IFC Class: `IfcCableCarrierSegment`, `IfcCableCarrierFitting`
- Stage: Stage 4 (Technical Design)

## Required Properties

| Property Set | Property Name | Data Type | Constraint | Req'd? |
|-------------|---------------|-----------|------------|--------|
| Pset_CableCarrierSegmentTypeCommon | NominalWidth | IfcPositiveLengthMeasure | > 0 | Mandatory |
| Pset_CableCarrierSegmentTypeCommon | NominalHeight | IfcPositiveLengthMeasure | > 0 | Mandatory |
| Custom_MEPF | LoadCapacity | IfcLinearForceMeasure | > 0 | Mandatory |
| Custom_MEPF | UniClass2015Code | IfcLabel | = `Ss_65_30_55` | Mandatory |
| Custom_MEPF | TrayType | IfcLabel | Not null | Mandatory |

## Notes
- TrayType values: `Ladder`, `Perforated`, `Solid-Bottom`, `Wire-Mesh`.
