# 06 — TIDP / MIDP Notes
## Plannerly M7U3 MEPF Starter Pack
### Task Information Delivery Plans, Master Information Delivery Plan, and Tool Evaluation

---

## 1. Purpose

This document records the TIDP/MIDP structure implemented for the MEPF Starter Pack, documents the methodology decisions made during implementation, and provides a critical evaluation of Plannerly as a tool for ISO 19650-aligned information management.

---

## 2. TIDP and MIDP — ISO 19650 Definitions

Under ISO 19650-2, information delivery planning operates at two levels:

**Task Information Delivery Plan (TIDP)**
A schedule of information containers and deliverables to be produced by a single Appointed Party, linked to the project programme. Each Appointed Party prepares their own TIDP covering their discipline scope, milestone commitments, and verification obligations. The TIDP is the Appointed Party's commitment to the Lead Appointed Party.

**Master Information Delivery Plan (MIDP)**
A consolidated schedule combining all TIDPs into a single project-level view. The MIDP is prepared and maintained by the Lead Appointed Party and provides the Appointing Party with a complete picture of when, by whom, and to what standard all information will be delivered across the project lifecycle.

In Plannerly, the Scope module functions as the MIDP. Each discipline group (D3010, E3010, D2010, D4010) represents a TIDP contributed by the relevant Appointed Party. The H5000 group represents the Lead Appointed Party's own TIDP for handover coordination. All TIDPs are visible simultaneously in the Scope grid, forming the consolidated MIDP view.

---

## 3. TIDP Structure by Appointed Party

### 3.1 MEC — Mechanical Engineer HVAC (TIDP: D3010)

5 tasks across Stage 3 and Stage 4. Stage 3 deliverables cover spatial routing geometry, material specification, and system classification — the minimum information required for MEP coordination. Stage 4 deliverables cover LOD 350 geometric compliance, insulation specification, and fire rating attribution — the minimum required for construction information.

### 3.2 ELE — Electrical Engineer Sparkie (TIDP: E3010)

4 tasks across Stage 3 and Stage 4. Stage 3 deliverables cover tray routing geometry and material; Stage 4 deliverables cover load classification and earthing designation. The earthing designation requirement reflects BS 7671 obligations and is a Stage 4 requirement because it depends on the final cable schedule, which is not available at Stage 3.

### 3.3 MEC — Process Water Piping (TIDP: D2010)

4 tasks across Stage 3 and Stage 4. Stage 3 deliverables cover pipe routing, pressure rating, material, and system classification. Stage 4 deliverables cover insulation specification and valve tagging. Valve tagging is a Stage 4 requirement because the valve schedule is developed from the Stage 3 system layout and cannot be finalised earlier.

### 3.4 FIR — Fire's R US (TIDP: D4010)

4 tasks, all at Stage 4. Fire sprinkler design is entirely Stage 4 because the hydraulic calculation, hazard classification, and sprinkler head selection depend on the finalised architectural and structural design from Stage 3. No Stage 3 sprinkler information requirement exists — this is a deliberate and standards-aligned decision, not a gap in the scope.

### 3.5 LAP — Zigurat (TIDP: H5000)

6 tasks spanning Stage 3, Stage 4, and Stage 5. The H5000 group represents the Lead Appointed Party's coordination responsibility for progressive COBie data drops and final handover information. This TIDP is the only one with Stage 5 tasks, reflecting the Lead Appointed Party's role in consolidating and authorising the final asset information model.

---

## 4. COBie Progressive Data Drop Methodology

COBie (Construction Operations Building Information Exchange, BS 1192-4) is implemented as a progressive data drop across three stages rather than a single Stage 5 event. This is a deliberate methodology decision aligned with ISO 19650-2 and consistent with best practice for FM asset data quality.

### Why progressive drops matter

A single Stage 5 COBie drop is a common failure mode on construction projects. Data collected retrospectively at handover is often incomplete, inaccurate, or unverifiable because it is assembled from memory, paper records, and O&M manuals rather than from live design data. Progressive drops build the asset register from the design outward, ensuring each layer of data is verified before the next is added.

### The three-drop structure

**Stage 3 Drop — Spaces and Zone Classifications (H5000-REQ-02)**
Spatial framework: floor designations, room names, zone classifications, and MEPF-served area boundaries. This data comes from the coordinated architectural model and forms the container structure into which all subsequent asset data is placed. Produced at Stage 3 information exchange when the spatial layout is coordinated and agreed.

**Stage 4 Drop — Types and Specifications (H5000-REQ-03)**
Type-level asset data: equipment type references, design specifications, product data sheet references, and design intent performance data. This data comes from the mechanical, electrical, and fire engineering specifications and is produced at Stage 4 when procurement is underway and product selection is confirmed.

**Stage 5 Drop — Components, Assets, and Warranties (H5000-REQ-04)**
Component-level asset data: serial numbers, manufacturer references, installation dates, warranty periods, spare parts lists, and maintenance intervals. This data can only be produced post-installation and forms the basis of the FM asset register. Produced at Stage 5 as part of the practical completion handover package.

This three-layer structure maps directly to the COBie spreadsheet hierarchy: Floor/Space (S3) → Type (S4) → Component (S5), and ensures the FM operator receives a complete, verified asset register at handover rather than a retrospectively assembled data dump.

---

## 5. Plannerly Hierarchy — Structure and Limitation

### 5.1 The three-level hierarchy

Plannerly's Scope module supports a three-level hierarchy:

- **Level 1 — Folder:** The top-level container. In this project: `MEPF – AI Estimation Trust Requirements`
- **Level 2 — Group:** Discipline groups. In this project: D3010, E3010, D2010, D4010, H5000
- **Level 3 — Item (Task):** Individual information requirements. In this project: REQ-01 through REQ-06

This hierarchy maps well to the ISO 19650 MIDP structure: Folder = Project, Group = TIDP, Item = Information Container.

### 5.2 The sub-grouping limitation

Plannerly does not support sub-grouping within a Group. Items cannot be nested below the Group level — all items within a group sit in a flat list. This means that logical sub-groupings (for example, separating Stage 3 geometry tasks from Stage 4 specification tasks within D3010) cannot be represented through nesting.

**Workaround implemented:** Stage-prefixed naming convention. Task titles do not include explicit stage prefixes (the milestone column assignment already conveys this), but the milestone assignment itself (Stage 3 or Stage 4) makes the logical grouping clear in the scope grid. This is a pragmatic workaround that maintains visual clarity without requiring structural workarounds that might compromise data integrity.

**Academic note:** This limitation is worth noting in the context of a Masters assignment because it reveals a genuine constraint in Plannerly's data model. A fully ISO 19650-compliant MIDP might require sub-grouping by information exchange point within a discipline TIDP. Plannerly resolves this through the milestone column structure rather than hierarchical nesting, which is a valid but distinct approach. The limitation is not a barrier to effective use of the tool for this project scale, but would require evaluation on larger, multi-stage projects with more complex discipline TIDPs.

---

## 6. Automation Methodology

A core academic argument of this assignment is that information requirements should be defined once and propagated automatically, rather than re-keyed manually across multiple tools. This project implements a three-layer automation pipeline:

**Layer 1 — Human Authoring (this repository)**
Requirements are authored once as structured markdown documents in this GitHub repository. The `docs/03-checkable-requirements.md` file is the single source of truth for all 23 requirement descriptions.

**Layer 2 — Project Management (Plannerly)**
Requirements are imported into Plannerly via `plannerly/plannerly-scope-import.csv` (bulk import) and task descriptions are pasted from the authoritative source. Information Requirements (verify rules) are configured against the bSDD, enabling automated model checking when an IFC model is connected. Human effort is limited to authoring and configuring — not re-keying.

**Layer 3 — Machine Checking (ifcopenshell + IDS)**
Requirements are encoded in `ids/mepf-requirements.ids` (ISO 21597 Information Delivery Specification) as machine-readable rules. This file can be executed directly against any IFC model using ifcopenshell, independently of Plannerly. This means the verification methodology is portable — it does not depend on a Plannerly licence and can be integrated into automated CI/CD pipelines for continuous model quality checking.

The three layers encode the same 23 requirements in three different formats optimised for three different audiences: human readers, project managers, and software tools. This is the automation methodology that distinguishes AI-augmented BIM management from traditional manual approaches.

---

## 7. Critical Evaluation of Plannerly

### Strengths

- **ISO 19650 alignment:** Plannerly's terminology, workflow, and data model are well-aligned with ISO 19650. The Scope module maps directly to the MIDP/TIDP structure; the Verify module implements the ISO 19650-2 Section 5.5 checking workflow; the team and responsibility model reflects the Appointing Party / Lead Appointed Party / Appointed Party hierarchy.
- **bSDD integration:** Direct integration with the buildingSMART Data Dictionary enables Information Requirements to be linked to internationally standardised property definitions, improving interoperability and reducing ambiguity in property name matching.
- **Kanban-based task tracking:** The Verify module's Kanban board provides a clear visual workflow from Proposed through In Progress, QA, and Complete, consistent with ISO 19650-2 information delivery status tracking.
- **Bulk import:** The CSV import functionality significantly reduces the time required to populate large scopes, enabling automation-first workflows.

### Limitations

- **Three-level hierarchy ceiling:** As documented in Section 5.2, the absence of sub-grouping within Groups limits the structural expressiveness of the MIDP for complex projects.
- **bSDD property gaps:** Several IFC standard properties (PredefinedType, LoadClass, ValvePattern, EarthingDesignation) are not available in the bSDD, requiring nearest-match substitutions. This is a limitation of the bSDD coverage rather than Plannerly specifically, but it affects the precision of automated verification rules.
- **No model = no Verify results:** The Verify module requires an IFC model to be uploaded before checks can be executed. There is no simulation or dry-run capability to validate rule configuration without a model. This makes rule testing dependent on model availability.
- **Single responsible party per cell:** While academically correct for ISO 19650 accountability, this constraint makes it impossible to represent shared or co-responsibility scenarios in the grid without supplementary RACI documentation.
- **Proprietary platform dependency:** The Plannerly project data is stored in Plannerly's cloud. While the IDS file and CSV export provide some portability, the full scope configuration (task descriptions, Information Requirements, team assignments) is not trivially exportable to other tools. This creates a degree of platform lock-in that should be considered for long-term project data governance.

---

*Document prepared as part of Module 7, Unit 3 — Plannerly MEPF Starter Pack*
*Masters in AI in Architecture and Construction — Zigurat Global Institute of Technology*
*Standard references: ISO 19650-1/-2, ISO 21597 (IDS), BS 1192-4 (COBie), RIBA Plan of Work 2020*
