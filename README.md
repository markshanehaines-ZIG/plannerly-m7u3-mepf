# Plannerly M7U3 MEPF Starter Pack

> **Masters in AI in Architecture and Construction — Module 7, Unit 3**
> Zigurat Global Institute of Technology
> Individual Assignment — Due 24 May 2026

[![GitHub commit activity](https://img.shields.io/github/commit-activity/w/markshanehaines-ZIG/plannerly-m7u3-mepf)](https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf/commits/main)
[![Last commit](https://img.shields.io/github/last-commit/markshanehaines-ZIG/plannerly-m7u3-mepf)](https://github.com/markshanehaines-ZIG/plannerly-m7u3-mepf/commits/main)

---

## What This Is

A fully configured **ISO 19650-aligned MEPF BIM information management starter pack**, built in Plannerly and documented here. The project demonstrates how AI assistance can be used to generate, structure, and verify BIM information requirements across four MEPF discipline groups.

**Plannerly project:**
`https://app.plannerly.com/projects/fb0a668b-7754-496e-939a-04bdc2812fa2/scope`

---

## The Automation Pipeline

This project is built around a single principle: **define requirements once, propagate automatically**.

```
docs/03-checkable-requirements.md          ← Single source of truth (AI-assisted authoring)
        │
        ├──► plannerly/plannerly-scope-import.csv   ► Plannerly Scope (bulk import)
        │                                              23 tasks, 5 groups, 3 milestones
        │
        └──► ids/mepf-requirements.ids              ► ifcopenshell IFC model checking
                (ISO 21597 IDS format)                 Vendor-neutral, tool-independent
```

Human effort is reserved for authoring requirements and steering the AI. Re-keying the same data into multiple tools is eliminated.

---

## What Has Been Built

### Plannerly (live system)

| Component | Detail |
|---|---|
| **Scope** | 5 groups, 23 tasks, 3 milestones (Stage 3 / Stage 4 / Stage 5) |
| **Teams** | 7 ISO 19650-aligned parties — LAP, MEC (×2), ELE, FIR, APP, BIM |
| **Responsibility Matrix** | All groups assigned, status PROPOSED throughout |
| **Task Descriptions** | All 23 tasks — full ISO 19650-standard description text |
| **Verify Rules** | bSDD-linked Information Requirements on all 17 model-checkable tasks |

### This Repository

| File | Purpose |
|---|---|
| `docs/02-purpose-and-scope.md` | Project scope definition |
| `docs/03-checkable-requirements.md` | All 23 requirement descriptions — authoritative source |
| `docs/04-verify-rules.md` | Full verify rules — IFC entity, Pset, property, bSDD mapping |
| `docs/05-responsibility-matrix.md` | ISO 19650 party definitions, RACI, task assignments |
| `docs/06-tidp-midp-notes.md` | TIDP/MIDP structure, COBie drops, critical Plannerly evaluation |
| `docs/07-final-submission.md` | Assignment submission summary and academic arguments |
| `plannerly/plannerly-scope-import.csv` | Bulk import CSV — Plannerly column format |
| `ids/mepf-requirements.ids` | ISO 21597 IDS — machine-readable verification rules |
| `assets/screenshots/` | Evidence screenshots from Plannerly |

---

## MEPF Scope Structure

```
MEPF – AI Estimation Trust Requirements
├── Mechanical – D3010 Ductwork          (5 tasks — MEC, Stage 3 + 4)
├── Electrical – E3010 Cable Trays       (4 tasks — ELE, Stage 3 + 4)
├── Plumbing   – D2010 Pipework          (4 tasks — MEC, Stage 3 + 4)
├── Fire       – D4010 Sprinkler Heads   (4 tasks — FIR, Stage 4)
└── Handover   – H5000 As-Built + COBie  (6 tasks — LAP, Stage 3 + 4 + 5)
```

---

## ISO 19650 Milestone Structure

| Milestone | RIBA Stage | Information Exchange |
|---|---|---|
| Stage 3 – Spatial Coordination | Stage 3 | Geometry, routing, materials, system classification |
| Stage 4 – Technical Design | Stage 4 | Specifications, insulation, fire ratings, valve schedules |
| Stage 5 – Construction | Stage 5 | As-built model, COBie components, O&M links, commissioning |

---

## COBie Progressive Drop Strategy

COBie is delivered as three structured data drops — not a single Stage 5 event:

| Drop | Stage | Content |
|---|---|---|
| S3 Spaces | Stage 3 | Floor designations, room names, zone classifications |
| S4 Types | Stage 4 | Equipment types, specifications, product data |
| S5 Components | Stage 5 | Serial numbers, warranties, maintenance intervals, asset register |

---

## Standards Referenced

| Standard | Application |
|---|---|
| ISO 19650-1 / -2 | MIDP/TIDP structure, party definitions, CDE workflow |
| ISO 21597 (IDS) | Machine-readable information delivery specification |
| ISO 16739-1 (IFC) | Entity types and property sets in all verify rules |
| BS 1192-4 (COBie) | Progressive data drop methodology |
| RIBA Plan of Work 2020 | Stage 3, 4, 5 milestone definitions |
| buildingSMART bSDD | Information Requirements linked to international property dictionary |
| BS EN 12845 / LPC Rules | Fire sprinkler design — Stage 4 assignment rationale |
| BS 7671 | Electrical earthing — E3010-REQ-04 |

---

## Repository Structure

```
plannerly-m7u3-mepf/
├── README.md
├── docs/
│   ├── 02-purpose-and-scope.md
│   ├── 03-checkable-requirements.md
│   ├── 04-verify-rules.md
│   ├── 05-responsibility-matrix.md
│   ├── 06-tidp-midp-notes.md
│   └── 07-final-submission.md
├── ids/
│   └── mepf-requirements.ids
├── plannerly/
│   └── plannerly-scope-import.csv
├── references/
│   ├── lecture-notes.md
│   └── source-links.md
└── assets/
    ├── screenshots/
    └── diagrams/
```

---

*Built with AI assistance (Claude, Anthropic) as part of a Masters in AI in Architecture and Construction.*
*All standards references, ISO 19650 terminology, and IFC property definitions are accurate and verifiable.*
