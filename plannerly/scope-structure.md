# Plannerly Scope Structure

> Copy this structure into Plannerly → Scope.
> Use the indentation to set parent/child relationships.

```
📁 MEPF – AI Estimation Trust Requirements
    📋 Mechanical – D3010 Ductwork
        ☑ M-D3010-001: Duct System Type populated
        ☑ M-D3010-002: Duct Insulation Thickness populated
        ☑ M-D3010-003: Duct UniClass Code = Ss_65_10_30
        ☑ M-D3010-004: Duct Flow Rate populated (fittings)

    📋 Electrical – E3010 Cable Trays
        ☑ E-E3010-001: Tray Width populated
        ☑ E-E3010-002: Tray Load Capacity populated
        ☑ E-E3010-003: Cable Tray UniClass Code = Ss_65_30_55

    📋 Plumbing – D2010 Pipework
        ☑ P-D2010-001: Pipe Nominal Diameter populated
        ☑ P-D2010-002: Pipe Material populated
        ☑ P-D2010-003: Pipe UniClass Code = Ss_70_50_16
        ☑ P-D2010-004: Pipe Insulation Type (HWS/CWS)

    📋 Fire – D4010 Sprinkler Heads
        ☑ F-D4010-001: Sprinkler Response Classification populated
        ☑ F-D4010-002: Sprinkler K-Factor populated
        ☑ F-D4010-003: Sprinkler UniClass Code = Ss_40_60_33
```

## Tips
- Set each `📋` item as a **Scope Task** in Plannerly.
- Set each `☑` item as a **sub-task / requirement** under its parent.
- Link each sub-task to the corresponding Verify rule (see `verify-task-names.md`).
- Assign milestones at the `📋` level: `Stage 4 – Parameter Population Complete`.
