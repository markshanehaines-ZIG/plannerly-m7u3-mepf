# 07 — Final Submission Summary
## Plannerly M7U3 MEPF Starter Pack
### Module 7, Unit 3 — Masters in AI in Architecture and Construction
### Zigurat Global Institute of Technology

---

## 1. Assignment Overview

This repository documents the design, configuration, and critical evaluation of a Plannerly MEPF Starter Pack produced for Module 7, Unit 3 of the Masters in AI in Architecture and Construction programme at Zigurat Global Institute of Technology.

The deliverable is a fully configured Plannerly project demonstrating ISO 19650-aligned BIM information management for four MEPF discipline groups, supported by machine-readable verification rules (IDS), automated scope import (CSV), and structured documentation.

**Plannerly Project URL:**
`https://app.plannerly.com/projects/fb0a668b-7754-496e-939a-04bdc2812fa2/scope`

**GitHub Repository:**
`https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf`

---

## 2. Deliverables Summary

### 2.1 Plannerly Configuration

| Component | Status | Details |
|---|---|---|
| Project created | ✅ Complete | MEPF – AI Estimation Trust Requirements |
| Scope groups imported | ✅ Complete | 5 groups, 23 tasks via CSV bulk import |
| Milestones created | ✅ Complete | Stage 3 – Spatial Coordination, Stage 4 – Technical Design, Stage 5 – Construction |
| Empty milestone deleted | ✅ Complete | Milestone 4 (unused) removed |
| Teams created | ✅ Complete | 7 ISO 19650-aligned teams with colour coding |
| Responsibility matrix | ✅ Complete | All 5 groups assigned via Quick Assign, status PROPOSED |
| Task descriptions | ✅ Complete | All 23 tasks — full description text in Description field |
| Information Requirements | ✅ Complete | bSDD-linked verify rules configured on all 17 model-checkable tasks |
| H5000 verify rules | ✅ N/A | Document delivery tasks — verified manually, not via model check |

### 2.2 GitHub Repository

| File | Status | Description |
|---|---|---|
| `plannerly/plannerly-scope-import.csv` | ✅ Complete | Bulk import CSV in Plannerly column format |
| `ids/mepf-requirements.ids` | ✅ Complete | ISO 21597 IDS file — machine-readable verification rules |
| `docs/02-purpose-and-scope.md` | ✅ Complete | Project purpose and scope definition |
| `docs/03-checkable-requirements.md` | ✅ Complete | All 23 task descriptions — authoritative source |
| `docs/04-verify-rules.md` | ✅ Complete | Full verify rules with IFC entity, Pset, bSDD mapping |
| `docs/05-responsibility-matrix.md` | ✅ Complete | ISO 19650 party definitions, RACI, task assignments |
| `docs/06-tidp-midp-notes.md` | ✅ Complete | TIDP/MIDP structure, COBie drops, Plannerly evaluation |
| `docs/07-final-submission.md` | ✅ Complete | This document |
| `assets/screenshots/` | ✅ Complete | Evidence screenshots committed throughout |

---

## 3. Standards Compliance

| Standard | Application in this project |
|---|---|
| ISO 19650-1 | Terminology — Appointing Party, Lead Appointed Party, Appointed Party throughout |
| ISO 19650-2 | MIDP/TIDP structure, information exchange points, CDE workflow, status codes |
| ISO 21597 | IDS file format — machine-readable information delivery specification |
| ISO 16739-1 (IFC) | IFC entity types and property sets referenced in all verify rules |
| BS 1192-4 (COBie) | Progressive data drop methodology — S3 Spaces, S4 Types, S5 Components |
| RIBA Plan of Work 2020 | Stage 3, Stage 4, Stage 5 milestone definitions |
| BS EN 12845 / LPC Rules | Fire sprinkler design standard — Stage 4 assignment rationale |
| BS 7671 | Electrical earthing — E3010-REQ-04 rationale |
| buildingSMART bSDD | Information Requirements linked to international property dictionary |
| buildingSMART BCF 2.1 | Referenced in verify methodology for future issue tracking integration |

---

## 4. Key Academic Arguments

### 4.1 Automation methodology — define once, propagate everywhere

The central academic contribution of this project is the demonstration that information requirements should be authored once and propagated automatically across all project management and verification tools, rather than re-keyed manually. The three-layer pipeline (Markdown → Plannerly → IDS) implements this principle concretely:

- Requirements are authored in `docs/03-checkable-requirements.md` as the single source of truth
- Propagated into Plannerly via `plannerly-scope-import.csv` for project management
- Encoded in `ids/mepf-requirements.ids` for automated IFC model checking

This approach reduces human error, maintains consistency across tools, and creates an auditable chain from requirement definition to model verification — directly aligned with the ISO 19650 information management philosophy.

### 4.2 Progressive information delivery — COBie as a designed data flow

The implementation of COBie as three progressive data drops (Stage 3 Spaces, Stage 4 Types, Stage 5 Components) rather than a single Stage 5 event demonstrates an understanding of why retrospective data collection at handover fails in practice. Each drop is designed to capture data at the point it is most accurate and verifiable — from the design model, not from memory or paper records. This is a deliberate methodology decision with direct FM asset quality implications.

### 4.3 Critical evaluation — Plannerly's hierarchy limitation

The three-level hierarchy ceiling in Plannerly (Folder → Group → Item, no sub-grouping) is documented as a genuine structural constraint relevant to ISO 19650 MIDP design at scale. The workaround implemented (milestone column assignment as the logical grouping mechanism) is valid for this project scope but would require re-evaluation on larger projects with more complex discipline TIDPs. This critical evaluation demonstrates tool literacy beyond basic platform operation.

### 4.4 OpenBIM verification pipeline

The IDS file is vendor-neutral and executable against any IFC model from any BIM authoring tool using ifcopenshell. This means the verification methodology is not dependent on Plannerly, can be integrated into automated pipelines, and aligns with the openBIM principle that compliance checking should operate on open standards rather than proprietary formats. This argument is directly relevant to the AI in Architecture and Construction programme context.

---

## 5. Git Commit History

The following commits document the progressive development of this assignment, providing an auditable record of work completed between 11–13 May 2026:

| Commit | Description |
|---|---|
| Initial commit | Repository structure created |
| Add folder structure | 22 files, full directory layout |
| Add purpose and scope | `docs/02-purpose-and-scope.md` |
| Add checkable requirements | `docs/03-checkable-requirements.md` with all 23 task descriptions |
| Add Plannerly import CSV | `plannerly/plannerly-scope-import.csv` |
| Add IDS file | `ids/mepf-requirements.ids` — ISO 21597 machine-readable rules |
| Add verify rules | `docs/04-verify-rules.md` |
| Add responsibility matrix | `docs/05-responsibility-matrix.md` |
| Add TIDP/MIDP notes | `docs/06-tidp-midp-notes.md` |
| Add screenshots | Evidence screenshots — scope grid, milestones, responsibility matrix, verify rules |
| Add final submission | `docs/07-final-submission.md` |

Full commit history with hashes is available at:
`https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf/commits/main`

---

## 6. How to Reproduce This Work

### Prerequisites

- Plannerly account with editor access to the project
- Git Bash or equivalent terminal
- Python 3.x with ifcopenshell installed (`pip install ifcopenshell`)

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf
   cd plannerly-m7u3-mepf
   ```

2. Review the scope import file:
   ```bash
   cat plannerly/plannerly-scope-import.csv
   ```

3. Validate the IDS file against a sample IFC model:
   ```python
   import ifcopenshell
   # Load IDS and validate against IFC model
   # See ids/mepf-requirements.ids for rule definitions
   ```

4. Open the Plannerly project to review the live scope, teams, and verify configuration:
   `https://app.plannerly.com/projects/fb0a668b-7754-496e-939a-04bdc2812fa2/scope`

---

## 7. Future Development

The following extensions would strengthen this MEPF Starter Pack for live project use:

- **Connect an IFC model to Plannerly Verify** — execute the configured Information Requirements against a real MEPF model and capture colour-coded pass/fail results as evidence (Route A)
- **Extend the IDS file** — add geometry facets (LOD checks) and cardinality rules (all elements must have the property, not just some)
- **Add COBie validation** — integrate a COBie validator into the Stage 5 workflow to automate H5000 data drop verification
- **BEP document in Plannerly Docs** — produce the full BIM Execution Plan as a structured Plannerly Docs document, linking scope tasks to BEP clauses
- **Extend to additional disciplines** — add structural (S-series), architectural (A-series), and civil (C-series) groups to create a full project MIDP

---

*Submitted as part of Module 7, Unit 3 — Plannerly MEPF Starter Pack*
*Masters in AI in Architecture and Construction — Zigurat Global Institute of Technology*
*Repository: https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf*
