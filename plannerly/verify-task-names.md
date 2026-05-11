# Plannerly Verify – Task Name Reference

> Use these exact names when creating rules in Plannerly → Verify.
> Consistent naming makes cross-referencing easier.

## Ductwork
- `VERIFY-M-001: Duct System Type populated`
- `VERIFY-M-002: Duct Insulation Thickness ≥ 0`
- `VERIFY-M-003: Duct UniClass Code = Ss_65_10_30`
- `VERIFY-M-004: Duct Flow Rate populated`

## Cable Trays
- `VERIFY-E-001: Tray Width populated`
- `VERIFY-E-002: Tray Load Capacity populated`
- `VERIFY-E-003: Cable Tray UniClass Code = Ss_65_30_55`

## Pipework
- `VERIFY-P-001: Pipe Nominal Diameter populated`
- `VERIFY-P-002: Pipe Material populated`
- `VERIFY-P-003: Pipe UniClass Code = Ss_70_50_16`
- `VERIFY-P-004: Pipe Insulation Type for HWS/CWS`

## Sprinkler Heads
- `VERIFY-F-001: Sprinkler Response Classification populated`
- `VERIFY-F-002: Sprinkler K-Factor populated`
- `VERIFY-F-003: Sprinkler UniClass Code = Ss_40_60_33`

## Linking Rules to Scope
In Plannerly, each Verify rule should be linked to its parent Scope task:

| Verify Rule Prefix | Parent Scope Task |
|-------------------|-------------------|
| VERIFY-M-* | Mechanical – D3010 Ductwork |
| VERIFY-E-* | Electrical – E3010 Cable Trays |
| VERIFY-P-* | Plumbing – D2010 Pipework |
| VERIFY-F-* | Fire – D4010 Sprinkler Heads |
