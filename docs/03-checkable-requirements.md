# 03 – Checkable Information Requirements

> Each requirement must be verifiable – i.e., it can be checked as
> TRUE or FALSE against a model element or dataset.

## Format Convention
`[SYSTEM]-[CODE]-[SEQUENCE]: <Requirement statement>`

---

## Mechanical – D3010 Ductwork

| ID | Requirement | Check Method |
|----|-------------|--------------|
| M-D3010-001 | Every duct segment shall have a `System Type` parameter populated | IDS / Verify rule |
| M-D3010-002 | Every duct segment shall have an `Insulation Thickness` value ≥ 0 mm | IDS / Verify rule |
| M-D3010-003 | Every duct segment shall carry a `UniClass 2015 Code` of `Ss_65_10_30` | IDS / Verify rule |
| M-D3010-004 | Every duct fitting shall have a `Flow Rate (l/s)` parameter populated | IDS / Verify rule |

---

## Electrical – E3010 Cable Trays

| ID | Requirement | Check Method |
|----|-------------|--------------|
| E-E3010-001 | Every cable tray shall have a `Tray Width (mm)` parameter populated | IDS / Verify rule |
| E-E3010-002 | Every cable tray shall have a `Load Capacity (kg/m)` value populated | IDS / Verify rule |
| E-E3010-003 | Every cable tray shall carry a `UniClass 2015 Code` of `Ss_65_30_55` | IDS / Verify rule |

---

## Plumbing – D2010 Pipework

| ID | Requirement | Check Method |
|----|-------------|--------------|
| P-D2010-001 | Every pipe shall have `Nominal Diameter (mm)` populated | IDS / Verify rule |
| P-D2010-002 | Every pipe shall have `Material` parameter populated | IDS / Verify rule |
| P-D2010-003 | Every pipe shall carry a `UniClass 2015 Code` of `Ss_70_50_16` | IDS / Verify rule |
| P-D2010-004 | Every pipe shall have `Insulation Type` parameter populated where `System = HWS` or `CWS` | IDS / Verify rule |

---

## Fire – D4010 Sprinkler Heads

| ID | Requirement | Check Method |
|----|-------------|--------------|
| F-D4010-001 | Every sprinkler head shall have `Response Classification` populated | IDS / Verify rule |
| F-D4010-002 | Every sprinkler head shall have `K-Factor` value populated | IDS / Verify rule |
| F-D4010-003 | Every sprinkler head shall carry a `UniClass 2015 Code` of `Ss_40_60_33` | IDS / Verify rule |
