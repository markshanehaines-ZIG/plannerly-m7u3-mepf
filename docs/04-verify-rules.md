# 04 — Verify Rules
## Plannerly M7U3 MEPF Starter Pack
### ISO 19650-Aligned Model Checking Rules

---

## 1. Purpose

This document defines the verification rules applied to each information requirement in the MEPF scope. Verification rules specify the IFC entity type, property set, and property name that must be present and populated in a compliant BIM model at the relevant project stage.

These rules have been configured as Information Requirements on each Plannerly Scope task, linked to the buildingSMART Data Dictionary (bSDD). When an IFC model is connected to the Plannerly Verify module, these rules are evaluated automatically and results are displayed as colour-coded pass/fail per element in the 3D viewer.

The machine-readable equivalent of these rules is encoded in `ids/mepf-requirements.ids` (ISO 21597 Information Delivery Specification format), which can be executed directly against IFC models using ifcopenshell for automated compliance checking independent of Plannerly.

---

## 2. Verification Methodology

Plannerly Verify operates by connecting an IFC model to the project and evaluating Information Requirements configured on each task. Two rule types are used:

- **Model Rules** — global rules that check a property across all elements of a given IFC entity type. For example, checking that every `IfcDuctSegment` in the model carries a `NominalWidth` value.
- **Task Rules** — specific rules tied to individual tasks, checking for particular property values rather than mere presence.

For this MEPF starter pack, all rules are configured as model rules checking for property presence (`Is not empty`), consistent with the ISO 19650 principle that information requirements must be verifiable at each information exchange.

The verification workflow is:

1. Appointed Party authors the IFC model in their chosen BIM tool (Revit, ArchiCAD, Tekla, etc.)
2. IFC model is uploaded to Plannerly Verify
3. Plannerly evaluates all configured Information Requirements against the model
4. Results are displayed per element — pass (green), fail (red), or not applicable
5. Failed elements are raised as issues on the Kanban board
6. Appointed Party resolves issues and re-submits
7. BIM Manager confirms verification complete and task moves to Complete status

This workflow aligns with ISO 19650-2 Section 5.5 — checking of information models prior to authorisation and sharing.

---

## 3. Verify Rules by Discipline Group

### 3.1 D3010 — Mechanical Ductwork

Responsible Party: MEC (Mechanical Engineer HVAC)

| Task Code | Task Title | IFC Entity | Property Set | Property | bSDD Match | Stage |
|---|---|---|---|---|---|---|
| MEPF.D3010.REQ-01 | Ductwork Dimensions and LOD | IfcDuctSegment | Pset_DuctSegmentTypeCommon | NominalWidth | Nominal Width | Stage 3 |
| MEPF.D3010.REQ-02 | Ductwork Material Specification | IfcDuctSegment | Pset_DuctSegmentTypeCommon | MaterialType | Material Type | Stage 3 |
| MEPF.D3010.REQ-03 | Ductwork System Classification | IfcDuctSegment | Pset_DuctSegmentTypeCommon | SystemType | System Type | Stage 3 |
| MEPF.D3010.REQ-04 | Ductwork Geometric Compliance LOD 350 | IfcDuctSegment | Pset_DuctSegmentTypeCommon | NominalWidth | Nominal Width | Stage 4 |
| MEPF.D3010.REQ-05 | Ductwork Insulation and Fire Rating | IfcDuctSegment | Pset_DuctSegmentTypeCommon | InsulationStandardClass | Insulation Standard Class | Stage 4 |
| MEPF.D3010.REQ-05 | Ductwork Insulation and Fire Rating | IfcDuctSegment | Pset_DuctSegmentTypeCommon | FireRating | Fire Rating | Stage 4 |

**Notes:**
- REQ-01 and REQ-04 both check `NominalWidth` but at different stages and LOD levels. Stage 3 confirms routing geometry is present; Stage 4 confirms LOD 350 dimensional accuracy after coordination.
- REQ-05 carries two Information Requirements (insulation and fire rating) as both attributes are required on the same element at the same stage.
- `PredefinedType` is an IFC schema property rather than a bSDD property and is therefore enforced via the IDS file (`ids/mepf-requirements.ids`) rather than in Plannerly Verify directly.

---

### 3.2 E3010 — Electrical Cable Trays

Responsible Party: ELE (Electrical Engineer Sparkie)

| Task Code | Task Title | IFC Entity | Property Set | Property | bSDD Match | Stage |
|---|---|---|---|---|---|---|
| MEPF.E3010.REQ-01 | Cable Tray Dimensions and LOD | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | NominalWidth | Nominal Width | Stage 3 |
| MEPF.E3010.REQ-02 | Cable Tray Material Specification | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | MaterialType | Material Type | Stage 3 |
| MEPF.E3010.REQ-03 | Cable Tray Load Classification | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | LoadCapacity | Load Capacity | Stage 4 |
| MEPF.E3010.REQ-04 | Cable Tray Earthing Designation | IfcCableCarrierSegment | Pset_CableCarrierSegmentTypeCommon | EarthingStyle | Earthing Style | Stage 4 |

**Notes:**
- `LoadClass` (CABLOFIL classification) is not available in bSDD. `LoadCapacity` is used as the closest standard IFC property. When a real IFC model is connected, the Appointed Party should confirm whether the load classification is stored under `LoadCapacity` or a custom shared parameter, and the rule updated accordingly.
- `EarthingDesignation` is not available in bSDD. `EarthingStyle` is used as the closest match for BS 7671 earthing and bonding requirements.

---

### 3.3 D2010 — Plumbing Pipework

Responsible Party: MEC (Process Water Piping)

| Task Code | Task Title | IFC Entity | Property Set | Property | bSDD Match | Stage |
|---|---|---|---|---|---|---|
| MEPF.D2010.REQ-01 | Pipework Pressure Rating and Material | IfcPipeSegment | Pset_PipeSegmentTypeCommon | WorkingPressure | Working Pressure | Stage 3 |
| MEPF.D2010.REQ-01 | Pipework Pressure Rating and Material | IfcPipeSegment | Pset_PipeSegmentTypeCommon | MaterialType | Material Type | Stage 3 |
| MEPF.D2010.REQ-02 | Pipework System Classification | IfcPipeSegment | Pset_PipeSegmentTypeCommon | SystemType | System Type | Stage 3 |
| MEPF.D2010.REQ-03 | Pipework Insulation | IfcPipeSegment | Pset_PipeSegmentTypeCommon | InsulationStandardClass | Insulation Standard Class | Stage 4 |
| MEPF.D2010.REQ-04 | Valve Tagging and Type | IfcValve | Pset_ValveTypeCommon | Tag | Tag | Stage 4 |
| MEPF.D2010.REQ-04 | Valve Tagging and Type | IfcValve | Pset_ValveTypeCommon | PatternType | Pattern Type | Stage 4 |

**Notes:**
- REQ-01 carries two Information Requirements: working pressure rating and material. Both must be present on the same `IfcPipeSegment` element at Stage 3.
- REQ-04 applies to `IfcValve` elements rather than `IfcPipeSegment`. Plannerly Verify must be configured with a separate model rule targeting the valve entity type.
- `ValvePattern` is not available in bSDD. `PatternType` is used as the closest available match. This should be reviewed against the actual IFC model parameter name when a model is connected.

---

### 3.4 D4010 — Fire Sprinkler Heads

Responsible Party: FIR (Fire's R US)

| Task Code | Task Title | IFC Entity | Property Set | Property | bSDD Match | Stage |
|---|---|---|---|---|---|---|
| MEPF.D4010.REQ-01 | Sprinkler Head Location and Coverage Zone | IfcFireSuppressionTerminal | Pset_FireSuppressionTerminalTypeCommon | SprinklerType | Sprinkler Type | Stage 4 |
| MEPF.D4010.REQ-02 | Sprinkler Head Type and Temperature Rating | IfcFireSuppressionTerminal | Pset_FireSuppressionTerminalTypeCommon | ActivationTemperature | Activation Temperature | Stage 4 |
| MEPF.D4010.REQ-03 | Sprinkler Pipework and Zone Valve Attribution | IfcValve | Pset_ValveTypeCommon | Tag | Tag | Stage 4 |
| MEPF.D4010.REQ-04 | Sprinkler System Design Standard and Hazard Class | IfcZone | Pset_ZoneCommon | Category | Category | Stage 4 |

**Notes:**
- All D4010 tasks are Stage 4 requirements. No Stage 3 information requirement exists for sprinkler heads because the hydraulic design, which determines coverage zone geometry and head specification, cannot be completed until Stage 4 Technical Design. This is consistent with the progressive information delivery principle of ISO 19650.
- REQ-04 targets `IfcZone` rather than a terminal element. Zone-level properties require a separate model rule configured against the zone entity type.

---

### 3.5 H5000 — Handover As-Built and COBie

Responsible Party: LAP (Zigurat — Lead Appointed Party)

No Plannerly Verify Information Requirements are configured for H5000 tasks. These tasks relate to document delivery, COBie data drops, and commissioning record linkage rather than IFC model property checks. Verification for H5000 tasks is performed manually by the Lead Appointed Party through review of the CDE submission against the approved handover checklist.

The COBie data drops (REQ-02, REQ-03, REQ-04) are verified by the BIM Manager using the COBie validation tools within the CDE, not through Plannerly Verify.

---

## 4. Relationship to the IDS File

The `ids/mepf-requirements.ids` file (Information Delivery Specification, ISO 21597) encodes all 23 requirements as machine-readable rules. This file is the authoritative source for automated IFC model checking and is independent of Plannerly.

The relationship between the three verification layers is:

| Layer | Format | Purpose | Tool |
|---|---|---|---|
| Human-readable requirements | This document (Markdown) | Communication and audit | GitHub / PDF |
| Plannerly Verify rules | Information Requirements on tasks | Project management and tracking | Plannerly |
| Machine-readable rules | `ids/mepf-requirements.ids` (ISO 21597) | Automated IFC compliance checking | ifcopenshell |

All three layers encode the same requirements. The IDS file is the most precise and portable — it can be executed against any IFC model from any BIM authoring tool without requiring a Plannerly licence.

---

## 5. Known Limitations and Observations

**bSDD property name mismatches:** Several IFC property names (e.g. `PredefinedType`, `LoadClass`, `ValvePattern`, `EarthingDesignation`) are not available as named properties in the buildingSMART Data Dictionary. Closest available bSDD properties have been selected and are documented in the notes above. These selections should be reviewed and updated when a real IFC model is connected and actual property names confirmed.

**Custom shared parameters:** Many BIM authoring tools use custom shared parameters that do not map directly to IFC Pset property names. When a model is connected to Plannerly Verify, parameter name matching must be verified carefully — even a single whitespace character can break the link. The recommended approach is to copy the parameter name directly from the model property window and use the browser search to confirm a 100% match with the Information Requirement name in Plannerly.

**H5000 verification scope:** COBie data drops and O&M manual linkage cannot be verified through IFC property checking alone. A separate COBie validation workflow is required, using a COBie-aware viewer or validation tool within the CDE. This is a known limitation of IFC-based model checking and is documented here as a critical evaluation of the tool methodology.

---

*Document prepared as part of Module 7, Unit 3 — Plannerly MEPF Starter Pack*
*Masters in AI in Architecture and Construction — Zigurat Global Institute of Technology*
*Standard references: ISO 19650-1/-2, ISO 21597 (IDS), ISO 16739-1 (IFC), buildingSMART bSDD*
