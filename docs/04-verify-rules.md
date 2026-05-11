# 04 – Plannerly Verify Rules

> These rules mirror the checkable requirements in `03-checkable-requirements.md`.
> Create each rule in Plannerly → Verify, linked to the corresponding Scope task.

## Rule Naming Convention
`VERIFY-[SYSTEM]-[SEQUENCE]: <Rule name as it appears in Plannerly>`

---

## Ductwork Rules

| Plannerly Rule Name | Linked Scope Task | Pass Condition |
|---------------------|-------------------|----------------|
| `VERIFY-M-001: Duct System Type populated` | Mechanical – D3010 Ductwork | Parameter exists and is not null |
| `VERIFY-M-002: Duct Insulation Thickness ≥ 0` | Mechanical – D3010 Ductwork | Numeric value ≥ 0 |
| `VERIFY-M-003: Duct UniClass Code correct` | Mechanical – D3010 Ductwork | Value = `Ss_65_10_30` |
| `VERIFY-M-004: Duct Flow Rate populated` | Mechanical – D3010 Ductwork | Parameter exists and is not null |

---

## Cable Tray Rules

| Plannerly Rule Name | Linked Scope Task | Pass Condition |
|---------------------|-------------------|----------------|
| `VERIFY-E-001: Tray Width populated` | Electrical – E3010 Cable Trays | Parameter exists and is not null |
| `VERIFY-E-002: Tray Load Capacity populated` | Electrical – E3010 Cable Trays | Numeric value > 0 |
| `VERIFY-E-003: Cable Tray UniClass Code correct` | Electrical – E3010 Cable Trays | Value = `Ss_65_30_55` |

---

## Pipework Rules

| Plannerly Rule Name | Linked Scope Task | Pass Condition |
|---------------------|-------------------|----------------|
| `VERIFY-P-001: Pipe Nominal Diameter populated` | Plumbing – D2010 Pipework | Numeric value > 0 |
| `VERIFY-P-002: Pipe Material populated` | Plumbing – D2010 Pipework | Parameter exists and is not null |
| `VERIFY-P-003: Pipe UniClass Code correct` | Plumbing – D2010 Pipework | Value = `Ss_70_50_16` |
| `VERIFY-P-004: Pipe Insulation Type for HWS/CWS` | Plumbing – D2010 Pipework | If System = HWS or CWS then Insulation Type ≠ null |

---

## Sprinkler Rules

| Plannerly Rule Name | Linked Scope Task | Pass Condition |
|---------------------|-------------------|----------------|
| `VERIFY-F-001: Sprinkler Response Classification populated` | Fire – D4010 Sprinkler Heads | Parameter exists and is not null |
| `VERIFY-F-002: Sprinkler K-Factor populated` | Fire – D4010 Sprinkler Heads | Numeric value > 0 |
| `VERIFY-F-003: Sprinkler UniClass Code correct` | Fire – D4010 Sprinkler Heads | Value = `Ss_40_60_33` |

---

## Evidence Required
- [ ] Screenshot of each rule in Plannerly Verify → add to `assets/screenshots/`
- [ ] Export of Verify results (pass/fail summary) → add to `assets/screenshots/`
