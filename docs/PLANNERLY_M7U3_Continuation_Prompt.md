# Plannerly M7U3 MEPF — Project Continuity Prompt
## Copy and paste this entire document into a new chat to continue the project

---

## Who I am and what this project is

I am a student on the **Masters in AI in Architecture and Construction** programme at **Zigurat Global Institute of Technology**. This is my **Module 7, Unit 3 (M7U3) assignment** — a Plannerly MEPF Starter Pack demonstrating ISO 19650-aligned BIM information management for four MEPF discipline groups.

---

## Project locations

- **GitHub repo:** `https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf`
- **Local repo:** `C:\Users\ShaneHaines\Downloads\plannerly-m7u3-mepf`
- **Plannerly project:** `https://app.plannerly.com/projects/fb0a668b-7754-496e-939a-04bdc2812fa2/scope`
- **Git Bash prompt:** `AzureAD+ShaneHaines@AD3D006 MINGW64 ~/Downloads/plannerly-m7u3-mepf (main)`

---

## What has been completed

### GitHub Repository
- ✅ Repo created with full folder structure (22 files)
- ✅ Description and 9 topic tags added
- ✅ **11 commits** pushed — clean audit trail from May 11–13 2026
- ✅ `docs/02-purpose-and-scope.md` updated
- ✅ `docs/03-checkable-requirements.md` updated with all 23 task descriptions

### Automation files built and committed
- ✅ `plannerly/plannerly-scope-import.csv` — Plannerly bulk import CSV in exact Plannerly column format (Level, Type, Code, Title, Subtitle, Entity Type) with hierarchical MEPF-prefixed codes
- ✅ `ids/mepf-requirements.ids` — ISO 21597 IDS XML file encoding all 23 requirements as machine-checkable rules (IFC entity, property set, property name, permitted values) — runnable against real IFC models via ifcopenshell

### Plannerly Scope — FULLY BUILT
- ✅ **5 groups, 23 tasks** imported and structured:
  - `MEPF.D3010` — Mechanical Ductwork (5 tasks, REQ-01 to REQ-05)
  - `MEPF.E3010` — Electrical Cable Trays (4 tasks, REQ-01 to REQ-04)
  - `MEPF.D2010` — Plumbing Pipework (4 tasks, REQ-01 to REQ-04)
  - `MEPF.D4010` — Fire Sprinkler Heads (4 tasks, REQ-01 to REQ-04)
  - `MEPF.H5000` — Handover As-Built and COBie (6 tasks, REQ-01 to REQ-06)
- ✅ **3 milestones** created: Stage 3 – Spatial Coordination | Stage 4 – Technical Design | Stage 5 – Construction
- ✅ All 23 tasks assigned to correct milestones (Stage 3 for geometry/material tasks, Stage 4 for detailed spec tasks, Stage 5 for H5000 handover tasks)
- ✅ COBie split correctly into progressive data drops: S3 Spaces, S4 Types, S5 Components

### Plannerly Teams — FULLY BUILT
Six ISO 19650-aligned teams created with colour coding:
- `LAP` — Zigurat (Lead Appointed Party) — blue
- `MEC` — Mechanical Engineer HVAC (Mech Dry) — teal
- `ELE` — Electrical Engineer Sparkie — orange
- `MEC` — Process Water Piping (Mech Wet) — dark
- `APP` — Client (Appointing Party) — purple
- `FIR` — Fire's R US (Fire Suppression Engineer) — red
- `BIM` — AD3D (BIM Manager) — black

### Responsibility Matrix — FULLY BUILT
- ✅ All 5 groups assigned to correct responsible teams via Quick Assign
- ✅ Status set to PROPOSED across all tasks
- D3010 → MEC (Mechanical Engineer HVAC)
- E3010 → ELE (Electrical Engineer Sparkie)
- D2010 → MEC (Process Water Piping)
- D4010 → FIR (Fire's R US)
- H5000 → LAP (Zigurat)

---

## Key academic decisions made — maintain these

1. **ISO 19650 terminology throughout** — Appointing Party (client), Lead Appointed Party (Zigurat/main contractor), Appointed Parties (discipline engineers)
2. **COBie is a progressive data drop** — S3 Spaces/Zones, S4 Types/Specifications, S5 Components/Assets — not a single Stage 5 event
3. **Plannerly's 3-level hierarchy limitation** — Folder → Group → Item. No sub-grouping within groups. Workaround: stage-prefixed naming convention (S3/S4/S5) implies logical hierarchy within flat item list. This limitation is documented in `docs/06-tidp-midp-notes.md` as critical evaluation of the tool.
4. **Automation methodology** — requirements defined once in IDS (ISO 21597 machine-readable), propagated into Plannerly for project management and into ifcopenshell for IFC verification. Human effort reserved for authoring requirements, not re-keying them.
5. **One responsible team per cell** in Plannerly — this is by design. Full RACI (A, C, I) is captured in the BEP document in Plannerly Docs, not in scope grid cells.

---

## What still needs to be done (in priority order)

### Plannerly — immediate next steps
1. **Verify module** — set up model checking rules in Plannerly Verify. Two options:
   - **Route A (preferred):** Upload a sample MEPF IFC model and run real automated checks, creating model rules and task rules, screenshot colour-coded results
   - **Route B:** Document the verify rules without a model, referencing `ids/mepf-requirements.ids` as the machine-readable equivalent
   - Plannerly Verify uses: model rules (global, match task property to model property across whole model) and task rules (specific, property-value matching for exceptions)
   - The Verify workflow: connect model → create rules → evaluate completion % → fix issues → move to complete on Kanban board

2. **Delete Milestone 4** — an unused empty milestone column appeared in Plannerly Scope. Delete it.

3. **Add task descriptions** — the 16 remaining Plannerly task description fields (in the Plannerly UI, not the CSV) still need the full description text pasting in. These were written in the previous session — see the full list below under "Task Descriptions Ready to Paste".

### Documentation
4. **Update `docs/04-verify-rules.md`** — document all 23 verify rules referencing IFC entity types, property sets, property names, and permitted values. Reference `ids/mepf-requirements.ids` as the machine-readable source.
5. **Update `docs/05-responsibility-matrix.md`** — update to reflect the completed Plannerly responsibility matrix with all 5 groups, team assignments, and ISO 19650 party definitions.
6. **Update `docs/06-tidp-midp-notes.md`** — document the TIDP/MIDP structure, Plannerly hierarchy limitation workaround, and COBie progressive drop methodology.
7. **Write `docs/07-final-submission.md`** — final submission summary document.

### GitHub
8. **Push all screenshots** to `assets/screenshots/` — scope matrix, milestone matrix, responsibility matrix, verify results
9. **Final push** with all docs updated

---

## Task Descriptions Ready to Paste into Plannerly UI

These descriptions were written in the previous session and are ready to paste into each task's description field in Plannerly. D3010-REQ-01 was already added.

**D3010-REQ-02 — Ductwork Material Specification**
All ductwork elements shall have a material property assigned in the BIM model that is drawn from the project-approved material schedule. The material value shall be one of: galvanised mild steel, stainless steel (grade specified), aluminium alloy, or GRP as appropriate to the zone classification. This attribute is required at Stage 3 and must be verifiable against the Employer's Information Requirements (EIR). Verification is by automated IFC property check against the approved material list.

**D3010-REQ-03 — Ductwork System Classification**
Each ductwork element shall be assigned a system type classification consistent with the project MEP coding structure (e.g. supply air, extract air, exhaust, smoke control). The system type shall be recorded as a structured property in the IFC model and shall correspond to the zone and fire compartment designation shown on the approved drawings. This requirement is applicable from Stage 3 onwards and is verified by cross-referencing IFC IfcSystem grouping against the approved schedule.

**D3010-REQ-04 — Ductwork Geometric Compliance (LOD 350)**
Ductwork elements shall be modelled to a minimum of LOD 350 at Stage 4, including accurate cross-section dimensions, overall routing, end connections, and any integral insulation envelope. The model geometry shall be sufficient to support coordinated clash detection against structural and architectural models. Verification is by automated bounding-box check and visual review in the CDE coordination model.

**D3010-REQ-05 — Ductwork Insulation and Fire Rating**
Where ductwork passes through fire compartments or serves smoke control zones, an insulation specification and fire rating attribute shall be attached to the relevant model elements. The fire rating value shall reference the applicable standard (e.g. BS EN 1366-1) and be consistent with the fire strategy drawing. This attribute is required no later than Stage 4 information exchange. Verification is by IFC property set query against the fire compartment boundary schedule.

**E3010-REQ-01 — Cable Tray Geometry and Routing (LOD 300)**
All cable tray elements shall be modelled to a minimum of LOD 300 at Stage 3, showing accurate tray width, depth, routing centreline, and support bracket spacing. The model shall be sufficient to detect clashes with primary structural members and ductwork zones. Verification is by automated clash detection run within the CDE and sign-off by the lead electrical engineer.

**E3010-REQ-02 — Cable Tray Material and Finish Specification**
Each cable tray element shall carry a material and surface finish attribute in the BIM model, drawn from the project specification (e.g. hot-dip galvanised steel, stainless steel grade 316, or PVC-coated). The attribute shall be consistent with the corrosion risk zone classification for the area served. This property is required at Stage 3 and is verified by automated IFC property check against the approved cable tray schedule.

**E3010-REQ-03 — Cable Tray Load Classification**
Cable tray elements shall include a load rating attribute indicating the approved load class (Light, Medium, or Heavy per CABLOFIL or equivalent classification). The load class shall be consistent with the number of cable runs shown in the associated cable schedule. This attribute is required at Stage 4 and is verified by cross-reference between the IFC model and the approved cable schedule submitted to the CDE.

**E3010-REQ-04 — Earthing and Bonding Tag**
Where cable trays form part of the earthing or bonding network, the relevant tray elements shall carry an earthing designation attribute in the BIM model. The attribute shall identify whether the element is a primary earth path, supplementary bond, or not in the earthing network. This requirement applies at Stage 4 and is verified by the electrical engineer against the earthing arrangement drawing issued to the CDE.

**D2010-REQ-01 — Pipework Material and Pressure Rating**
All pipework elements shall have a material attribute and a design pressure rating (in bar) assigned in the BIM model, consistent with the project mechanical specification. Material values shall include: copper, carbon steel, stainless steel (grade specified), CPVC, or HDPE as appropriate. Both attributes are required at Stage 3 and are verified by automated IFC property set query against the approved pipework schedule.

**D2010-REQ-02 — Pipe System and Flow Direction Classification**
Each pipework element shall be assigned a system classification (e.g. domestic cold water, domestic hot water, heating flow, heating return, chilled water flow, chilled water return) and, where applicable, a flow direction indicator. The system classification shall correspond to the colour coding and labelling scheme in the approved mechanical services drawing set. This attribute is required at Stage 3 and is verified by cross-reference with the system schematics issued to the CDE.

**D2010-REQ-03 — Pipework Insulation Specification**
Where pipework requires thermal insulation, fire protection, or acoustic lagging, an insulation type and thickness attribute shall be attached to the relevant model elements. The insulation specification shall reference the applicable product standard and be consistent with the building energy model (BEM) inputs. This attribute is required at Stage 4 and is verified by the mechanical engineer against the approved insulation schedule.

**D2010-REQ-04 — Valves, Isolators and Accessories (LOD 300)**
Significant in-line valves, isolating valves, pressure reducing valves, and strainers shall be modelled as discrete elements at a minimum of LOD 300 from Stage 4. Each element shall carry a duty/standby designation, a valve type attribute, and a reference to the relevant data sheet in the CDE. Verification is by checklist comparison between the IFC model valve count and the approved valve schedule.

**D4010-REQ-01 — Sprinkler Head Location and Coverage Zone**
All sprinkler head elements shall be modelled at their installed design position to LOD 300, with each head assigned to a coverage zone polygon consistent with the approved hydraulic calculation. The coverage zone attribute shall reference the sprinkler system zone identifier shown on the life safety drawing set. This property is required at Stage 4 and is verified by the fire engineer against the approved hydraulic design submitted to the CDE.

**D4010-REQ-02 — Sprinkler Head Type and Temperature Rating**
Each sprinkler head element shall carry a head type attribute (e.g. pendant, upright, concealed, sidewall) and a temperature classification (e.g. 57°C ordinary, 68°C ordinary, 79°C intermediate) consistent with the zone hazard classification. The attribute values shall be traceable to the specification and LPC Rules or NFPA 13 as applicable. This attribute is required at Stage 4 and is verified by automated IFC property check against the approved sprinkler head schedule.

**D4010-REQ-03 — Sprinkler Pipework and Zone Valve Attribution**
Sprinkler distribution pipework shall be modelled to LOD 300 from Stage 4, with each pipe section assigned to its corresponding zone and installation area as defined in the hydraulic design. Zone control valves shall be modelled as discrete objects with a valve reference attribute linking to the life safety panel schedule. Verification is by cross-reference between the IFC model and the approved zone valve schedule issued to the CDE.

**D4010-REQ-04 — Sprinkler System Design Standard and Hazard Class**
The sprinkler model and associated documentation shall record the governing design standard (LPC Rules for Automatic Sprinkler Installations, BS EN 12845, or NFPA 13 as applicable) and the hazard occupancy classification for each zone (Ordinary Hazard Group 1, 2, or 3; Extra High Hazard where applicable). These attributes shall be attached at zone level in the IFC model and are required at Stage 4. Verification is by the fire engineer against the approved hydraulic design document.

**H5000-REQ-01 — As-Built IFC Model Update**
The appointed parties shall update the IFC model to reflect actual installed positions, sizes, materials and routing following completion of installation works. The as-built model shall be issued to the CDE as a named revision with status S4 (Authorised) per ISO 19650-2. Verification is by the Lead Appointed Party against the approved as-built drawing set and site inspection record.

**H5000-REQ-02 — COBie Drop S3 – Spaces and Zone Classifications**
A COBie-compliant data drop shall be produced at Stage 3 information exchange covering space and zone data for all MEPF-served areas. The drop shall include floor designations, room names, zone classifications, and served area boundaries consistent with the architectural model. This data forms the spatial framework for subsequent Stage 4 and Stage 5 COBie drops. Verification is by the BIM Manager against the approved space schedule.

**H5000-REQ-03 — COBie Drop S4 – Types and Specifications**
A COBie-compliant data drop shall be produced at Stage 4 information exchange covering type-level data for all MEPF equipment and components. The drop shall include equipment type references, design specifications, product data sheet references, and design intent performance data. Verification is by the BIM Manager against the approved equipment schedules and product submittals issued to the CDE.

**H5000-REQ-04 — COBie Drop S5 – Components, Assets and Warranties**
A COBie-compliant data drop shall be produced at Stage 5 covering component-level asset data for all installed MEPF elements. The drop shall include serial numbers, manufacturer references, installation dates, warranty periods, spare parts lists, and maintenance interval data. This data forms the basis of the FM asset register. Verification is by the Lead Appointed Party against the commissioning and handover records.

**H5000-REQ-05 — O&M Manual References Linked to Model**
Operation and maintenance manual references shall be attached to all relevant IFC elements as document links pointing to the approved O&M file locations in the CDE. The document links shall use the CDE document reference number and revision status. This requirement is applicable at Stage 5 and is verified by the Lead Appointed Party as part of the handover package review.

**H5000-REQ-06 — Commissioning Records and Test Certificates**
Commissioning test certificates, system balancing records, and performance verification reports shall be linked to the relevant IFC system elements in the model. Each certificate shall be referenced by document number and stored in the CDE under the approved filing structure. This requirement is applicable at Stage 5 and verified by the client's representative as part of practical completion sign-off.

---

## Standards referenced in this assignment

| Standard | Application |
|---|---|
| ISO 19650-1 / -2 | BIM information management, exchange requirements, party definitions |
| ISO 21597 | IDS (Information Delivery Specification) schema |
| IFC (ISO 16739-1) | Open BIM model format, entity types and property sets |
| BCF 2.1 (buildingSMART) | Issue tracking and model coordination |
| RIBA Plan of Work 2020 | Stage definitions (Stage 3, 4, 5) |
| BS EN 12845 | Fixed firefighting systems — sprinkler design |
| LPC Rules | Loss Prevention Council sprinkler rules (UK) |
| NFPA 13 | Standard for installation of sprinkler systems |
| BS EN 1366-1 | Fire resistance of service installations — ducts |
| CABLOFIL | Cable tray load classification standard |
| COBie (BS 1192-4) | Construction Operations Building Information Exchange |
| Building Safety Act 2022 | Golden Thread — information management for higher-risk buildings |

---

## Verify module — research already done

Plannerly Verify combines a 3D model viewer with a Kanban board. Key facts:
- Requires an IFC model to be uploaded/linked to run automated checks
- **Model rules** — global rules matching a task property to a model property across the whole model (e.g. IfcDuctSegment elements → check NominalWidth property)
- **Task rules** — specific rules for individual tasks using property value matching (e.g. TypeName = "ConcreteSlab")
- Checks go beyond geometry — verifies that required information properties are present and complete
- Colour-coded results show pass/fail per element in the 3D viewer
- Kanban board tracks task status: Proposed → In Progress → QA → Complete
- Self-quality workflow: delivery team checks own model before submitting for formal review
- ISO 19650 aligned: checks information is verified against requirements before sharing

**Planned verify rules for MEPF:**

| Task | IFC Entity | Property Set | Property to Check |
|---|---|---|---|
| D3010-REQ-01 | IfcDuctSegment | Pset_DuctSegmentTypeCommon | NominalWidth |
| D3010-REQ-02 | IfcDuctSegment | Material | Material name in approved list |
| D3010-REQ-03 | IfcDuctSegment | Pset_DuctSegmentTypeCommon | PredefinedType |
| D3010-REQ-04 | IfcDuctSegment | Pset_DuctSegmentTypeCommon | InsulationThickness |
| D3010-REQ-05 | IfcDuctSegment | Pset_DuctSegmentTypeCommon | FireRating |
| E3010-REQ-01 | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | NominalWidth |
| E3010-REQ-02 | IfcCableCarrierSegment | Material | Material name in approved list |
| E3010-REQ-03 | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | LoadClass |
| E3010-REQ-04 | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | EarthingDesignation |
| D2010-REQ-01 | IfcPipeSegment | Pset_PipeSegmentTypeCommon | WorkingPressure + Material |
| D2010-REQ-02 | IfcPipeSegment | Pset_PipeSegmentTypeCommon | SystemClassification |
| D2010-REQ-03 | IfcPipeSegment | Pset_PipeSegmentTypeCommon | InsulationThickness |
| D2010-REQ-04 | IfcValve | Pset_ValveTypeCommon | Tag + ValvePattern |
| D4010-REQ-01 | IfcFireSuppressionTerminal | Pset_FireSuppressionTerminalTypeCommon | SprinklerType |
| D4010-REQ-02 | IfcFireSuppressionTerminal | Pset_FireSuppressionTerminalTypeCommon | ActivationTemperature |
| D4010-REQ-03 | IfcValve (zone control) | Pset_ValveTypeCommon | Tag |
| D4010-REQ-04 | IfcZone | Pset_ZoneCommon | Category |

---

## Important notes for the AI assistant receiving this prompt

- Always research Plannerly's documentation at `https://plannerly.com` and `https://help.plannerly.com` before giving instructions about Plannerly features — do not guess how the UI works.
- This is a **Masters in AI in Architecture and Construction** — automation methodology, standards alignment, and critical evaluation of tools are all academically significant.
- All content must be ISO 19650 accurate. Use correct terminology: Appointing Party, Lead Appointed Party, Appointed Party — not "client", "main contractor", "subcontractor".
- The student's Git Bash is always run from `~/Downloads/plannerly-m7u3-mepf` — remind them to `cd` there if commands fail.
- Screenshots are evidence — always prompt the student to take and commit screenshots after completing each Plannerly step.
- Professional, technically detailed writing style throughout — match this in all outputs.
- File outputs should be offered as downloadable files, not just shown inline.
- The IDS file (`ids/mepf-requirements.ids`) is the machine-readable version of the Verify rules — always reference it when discussing verification methodology.
