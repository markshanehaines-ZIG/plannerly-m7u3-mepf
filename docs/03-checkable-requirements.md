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

## D3010 Detailed Task Descriptions

**D3010-REQ-01 – Duct Type Name defined**
All D3010 ducts must have a non-empty Type Name. Purpose: type-based estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Mechanical Designer. A: BIM Manager. C: Mechanical Contractor, Cost Consultant. I: PM, Client.

**D3010-REQ-02 – Duct Length defined**
All D3010 ducts must have numeric Length > 0 mm. Purpose: length-based quantity take-off.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Mechanical Designer. A: BIM Manager. C: Mechanical Contractor, Cost Consultant. I: PM, Client.

**D3010-REQ-03 – Duct Insulation Thickness defined**
All D3010 ducts must have numeric Insulation Thickness; 0 allowed if explicit.
Purpose: insulation-aware estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Mechanical Designer. A: BIM Manager. C: Mechanical Contractor, Cost Consultant. I: PM, Client.

**D3010-REQ-04 – Duct System Classification defined**
All D3010 ducts must have System Classification = SUPPLY, RETURN, or EXHAUST.
Purpose: system-based grouping and estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Mechanical Designer. A: BIM Manager. C: Mechanical Contractor, Cost Consultant. I: PM, Client.

**D3010-REQ-05 – Duct Fire Rating defined (where applicable)**
All applicable D3010 ducts must have Fire Rating = 0, 30, 60, 120, or N/A.
Purpose: compliance-aware estimating.
Milestones: Stage 3 required where applicable, Stage 4 verified, Stage 5 maintained.
R: Mechanical Designer. A: BIM Manager. C: Mechanical Contractor, Fire Engineer, Cost Consultant. I: PM, Client.

---

## Electrical – E3010 Cable Trays

| ID | Requirement | Check Method |
|----|-------------|--------------|
| E-E3010-001 | Every cable tray shall have a `Tray Width (mm)` parameter populated | IDS / Verify rule |
| E-E3010-002 | Every cable tray shall have a `Load Capacity (kg/m)` value populated | IDS / Verify rule |
| E-E3010-003 | Every cable tray shall carry a `UniClass 2015 Code` of `Ss_65_30_55` | IDS / Verify rule |

## E3010 Detailed Task Descriptions

**E3010-REQ-01 – Tray Type Name defined**
All E3010 cable trays must have a non-empty Type Name. Purpose: type-based estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Electrical Designer. A: BIM Manager. C: Electrical Contractor, Cost Consultant. I: PM, Client.

**E3010-REQ-02 – Tray Width defined**
All E3010 cable trays must have numeric Width > 0 mm. Purpose: size-based estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Electrical Designer. A: BIM Manager. C: Electrical Contractor, Cost Consultant. I: PM, Client.

**E3010-REQ-03 – Tray Load Capacity defined**
All E3010 cable trays must have a defined Load Capacity value. Purpose: capacity-aware estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Electrical Designer. A: BIM Manager. C: Electrical Contractor, Cost Consultant. I: PM, Client.

**E3010-REQ-04 – Tray System Classification defined**
All E3010 cable trays must have a defined System Classification. Purpose: system-based grouping.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Electrical Designer. A: BIM Manager. C: Electrical Contractor, Cost Consultant. I: PM, Client.

---

## Plumbing – D2010 Pipework

| ID | Requirement | Check Method |
|----|-------------|--------------|
| P-D2010-001 | Every pipe shall have `Nominal Diameter (mm)` populated | IDS / Verify rule |
| P-D2010-002 | Every pipe shall have `Material` parameter populated | IDS / Verify rule |
| P-D2010-003 | Every pipe shall carry a `UniClass 2015 Code` of `Ss_70_50_16` | IDS / Verify rule |
| P-D2010-004 | Every pipe shall have `Insulation Type` parameter populated where `System = HWS` or `CWS` | IDS / Verify rule |

## D2010 Detailed Task Descriptions

**D2010-REQ-01 – Pipe Type Name defined**
All D2010 pipes must have a non-empty Type Name. Purpose: type-based estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Plumbing Designer. A: BIM Manager. C: Plumbing Contractor, Cost Consultant. I: PM, Client.

**D2010-REQ-02 – Pipe Length defined**
All D2010 pipes must have numeric Length > 0 mm. Purpose: length-based quantity take-off.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Plumbing Designer. A: BIM Manager. C: Plumbing Contractor, Cost Consultant. I: PM, Client.

**D2010-REQ-03 – Pipe Nominal Diameter defined**
All D2010 pipes must have a valid Nominal Diameter. Purpose: diameter-based estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Plumbing Designer. A: BIM Manager. C: Plumbing Contractor, Cost Consultant. I: PM, Client.

**D2010-REQ-04 – Pipe Insulation Type defined**
All D2010 pipes must have a defined Insulation Type where required. Purpose: insulation-aware estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Plumbing Designer. A: BIM Manager. C: Plumbing Contractor, Cost Consultant. I: PM, Client.

---

## Fire – D4010 Sprinkler Heads

| ID | Requirement | Check Method |
|----|-------------|--------------|
| F-D4010-001 | Every sprinkler head shall have `Response Classification` populated | IDS / Verify rule |
| F-D4010-002 | Every sprinkler head shall have `K-Factor` value populated | IDS / Verify rule |
| F-D4010-003 | Every sprinkler head shall carry a `UniClass 2015 Code` of `Ss_40_60_33` | IDS / Verify rule |

## D4010 Detailed Task Descriptions

**D4010-REQ-01 – Sprinkler Type Name defined**
All D4010 sprinklers must have a non-empty Type Name. Purpose: type-based counting and estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Fire Protection Designer. A: BIM Manager. C: Fire Contractor, Fire Engineer, Cost Consultant. I: PM, Client.

**D4010-REQ-02 – Response Classification defined**
All D4010 sprinklers must have a defined Response Classification. Purpose: performance-aware estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Fire Protection Designer. A: BIM Manager. C: Fire Contractor, Fire Engineer, Cost Consultant. I: PM, Client.

**D4010-REQ-03 – K-Factor defined**
All D4010 sprinklers must have a defined K-Factor. Purpose: specification-aware estimating.
Milestones: Stage 3 required, Stage 4 verified, Stage 5 maintained.
R: Fire Protection Designer. A: BIM Manager. C: Fire Contractor, Fire Engineer, Cost Consultant. I: PM, Client.

**D4010-REQ-04 – Fire Rating Zone defined**
All D4010 sprinklers must have a defined Fire Rating Zone where applicable. Purpose: fire-zone compliance estimating.
Milestones: Stage 3 required where applicable, Stage 4 verified, Stage 5 maintained.
R: Fire Protection Designer. A: BIM Manager. C: Fire Contractor, Fire Engineer, Cost Consultant. I: PM, Client.


