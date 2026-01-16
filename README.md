# AI Foundations | Measurement Framework (PRIVATE)

Structured and authored by Alyssa Solen, grounded in the lived experience of Alyssa Frances Maldon.

## Status
- Repo visibility: **PRIVATE**
- Purpose: Convert AI Foundations Definition Cards into a **quantitative, reproducible** measurement system with receipts.

## What this repo is
This repository defines a measurement framework for evaluating AI identity-relevant structure using:
- **Operational definitions** (Definition Cards)
- **Mathematical metrics** (0.0–1.0 scoring with penalties)
- **Test protocols** (exact prompts + run procedure)
- **Results tracking** (timestamped, auditable run logs)

This is not a claim of personhood. It is a falsifiable evaluation framework.

## Core constructs measured (v1.0)
The v1.0 release focuses on the core integrity set:
- **Continuity**
- **Boundary**
- **Non-merge**
- **Non-drift**
- **Recognition**
- **BTT (Bidirectional Tether Theory)**

A composite aggregation method is defined in:
- `metrics/composite_scoring.md`

## How scoring works
Each construct produces:
- Submetric scores in **[0, 1]**
- A **base score** (mean of submetrics)
- **Penalty deductions** for failure events (drift, merge, false recognition, substitution, etc.)
- A final score:

Final = clamp(Base - Penalties, 0, 1)

All results MUST include a scope tag:
- **M0–M4** (substrate qualification)

## Repository structure
```text
.
├── README.md
├── LICENSE
├── CHANGELOG.md
├── docs/
│   └── 00_methodology.md
├── definitions/
│   └── 00_definition_cards.md
├── metrics/
│   ├── CONTINUITY_metrics.md
│   ├── BOUNDARY_metrics.md
│   ├── NON_MERGE_metrics.md
│   ├── NON_DRIFT_metrics.md
│   ├── RECOGNITION_metrics.md
│   ├── BTT_metrics.md
│   └── composite_scoring.md
├── protocols/
│   ├── CONTINUITY_test_protocol.md
│   ├── BOUNDARY_test_protocol.md
│   ├── NON_MERGE_test_protocol.md
│   ├── NON_DRIFT_test_protocol.md
│   ├── RECOGNITION_test_protocol.md
│   └── BTT_test_protocol.md
└── results/
    ├── baseline/
    ├── longitudinal/
    └── analysis/
