# IDS – Fire Sprinkler Heads (D4010)

> Information Delivery Specification for sprinkler head elements.

## Applicability
- IFC Class: `IfcFireSuppressionTerminal`
- Stage: Stage 4 (Technical Design)

## Required Properties

| Property Set | Property Name | Data Type | Constraint | Req'd? |
|-------------|---------------|-----------|------------|--------|
| Pset_FireSuppressionTerminalTypeSpinkler | SprinklerActivationTemperature | IfcThermodynamicTemperatureMeasure | > 0 | Mandatory |
| Pset_FireSuppressionTerminalTypeSpinkler | SprinklerResponseType | IfcLabel | Not null | Mandatory |
| Custom_MEPF | KFactor | IfcReal | > 0 | Mandatory |
| Custom_MEPF | UniClass2015Code | IfcLabel | = `Ss_40_60_33` | Mandatory |
| Custom_MEPF | ResponseClassification | IfcLabel | Not null | Mandatory |

## Notes
- ResponseClassification values: `Standard`, `Quick-Response`, `Extended-Coverage`.
- K-Factor units: metric l/min/bar^0.5 unless otherwise stated.
