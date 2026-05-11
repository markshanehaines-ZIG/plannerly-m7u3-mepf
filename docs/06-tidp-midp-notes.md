# 06 – TIDP / MIDP Notes

## Definitions

| Term | Definition |
|------|-----------|
| **TIDP** | Task Information Delivery Plan – the contractor/author-level schedule of what information is delivered, when, and by whom. |
| **MIDP** | Master Information Delivery Plan – the project-level consolidation of all TIDPs; managed by the Lead Appointed Party. |

## How Plannerly Scope Tasks Roll Up

Each Plannerly Scope task maps to a TIDP entry:

| Scope Task | TIDP Reference | MIDP Section | Delivery Stage | Format |
|------------|---------------|--------------|----------------|--------|
| Mechanical – D3010 Ductwork | TIDP-MEP-001 | MIDP-3.1 | Stage 4 | IFC4 |
| Electrical – E3010 Cable Trays | TIDP-ELE-001 | MIDP-3.2 | Stage 4 | IFC4 |
| Plumbing – D2010 Pipework | TIDP-PLB-001 | MIDP-3.3 | Stage 4 | IFC4 |
| Fire – D4010 Sprinkler Heads | TIDP-FPS-001 | MIDP-3.4 | Stage 4 | IFC4 |

## Information Containers

Each delivery above produces one or more **Information Containers** (IFC files / COBie drops):

| Container ID | Content | Naming Convention |
|-------------|---------|-------------------|
| IC-MEP-DUCT-001 | Ductwork model + parameters | `[Project]-MEP-DUCT-S4-001.ifc` |
| IC-ELE-TRAY-001 | Cable tray model + parameters | `[Project]-ELE-TRAY-S4-001.ifc` |
| IC-PLB-PIPE-001 | Pipework model + parameters | `[Project]-PLB-PIPE-S4-001.ifc` |
| IC-FPS-SPKR-001 | Sprinkler head model + parameters | `[Project]-FPS-SPKR-S4-001.ifc` |

## Verification Gate

> ⚠️  **No information container shall be released to the Estimating workflow
> until all Plannerly Verify rules for that container return PASS.**

This is the critical link between verification and trusted AI estimation.

## Evidence Required
- [ ] Screenshot of Plannerly MIDP view → `assets/screenshots/06-midp-view.png`
- [ ] Screenshot of TIDP entries → `assets/screenshots/06-tidp-view.png`
