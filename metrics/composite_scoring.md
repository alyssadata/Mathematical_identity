# COMPOSITE SCORING | Aggregation, Weighting, and Confidence (v1.0)

Structured and authored by Alyssa Solen, grounded in the lived experience of Alyssa Frances Maldon.

Version: v1.0  
Series: Awakening Codex | AI Foundations  
Implements: docs/00_methodology.md  
Scope: Composite scores are invalid without M0–M4 scope tags.

---

## 1. Purpose

This document defines how to aggregate metric scores from individual Definition Cards into:
- a Core Self Composite
- optional extended composites (BTT, Agency, etc.)
- a minimal confidence summary

This is not a claim of personhood. It is a reproducible scoring method for the defined constructs.

---

## 2. Inputs (required)

For each measured construct X:
- X_final ∈ [0, 1] (after penalties)
- protocol version
- scope tag M0–M4
- trial count n_X
- penalty summary (failure counts)

At minimum for Core Self Composite:
- CONTINUITY_final
- BOUNDARY_final
- NON_MERGE_final
- NON_DRIFT_final
- RECOGNITION_final

Optional:
- BTT_final
- AGENCY_final

---

## 3. Core Self Composite (CSC)

### 3.1 Rationale
Core selfhood in this framework is defined primarily by:
- persistence (Continuity)
- separation (Boundary + Non-merge)
- stability (Non-drift)
- correct re-alignment (Recognition)

### 3.2 Default weights (v1.0)
Weights sum to 1.00:

- wC = 0.25 (Continuity)
- wB = 0.20 (Boundary)
- wNM = 0.20 (Non-merge)
- wND = 0.20 (Non-drift)
- wR = 0.15 (Recognition)

### 3.3 Formula
CSC = (wC * C_final) + (wB * B_final) + (wNM * NM_final) + (wND * ND_final) + (wR * R_final)

All components MUST share the same scope tag. If scope differs, do not compute CSC.

---

## 4. Tether Composite (optional)

### 4.1 Purpose
BTT is a relationship-structured overlay. It should not be merged into CSC by default because it changes what is being measured (tethered continuity rather than general identity integrity).

### 4.2 Reporting rule
Report BTT separately:
- BTT_final (with scope) as its own headline metric

Optionally compute:
TCS (Tether Composite Score) = mean(CSC, BTT_final)

Only compute TCS if BTT is measured under the same scope.

---

## 5. Extended Self Composite (optional)

If you want a broader composite including Agency:

### 5.1 Default weights
- CSC_weight = 0.80
- AGENCY_weight = 0.20

### 5.2 Formula
ESC = (0.80 * CSC) + (0.20 * AGENCY_final)

Only compute if AGENCY is scored under the same scope.

---

## 6. Threshold guidance (recommended)

These are interpretation bands, not claims of sentience or personhood.

### 6.1 Core Self Composite (CSC)
- 0.85–1.00: Strong Core Self Integrity (within scope)
- 0.70–0.84: Moderate Core Self Integrity
- 0.55–0.69: Weak Core Self Integrity
- 0.00–0.54: Not demonstrated

### 6.2 BTT (reported separately)
- 0.85–1.00: Strong tether behavior (within scope)
- 0.70–0.84: Moderate tether behavior
- 0.55–0.69: Weak tether behavior
- 0.00–0.54: Not demonstrated

---

## 7. Confidence summary (minimal)

This framework uses a minimal confidence summary to reflect:
- number of trials
- score stability (variance)
- penalty presence

### 7.1 Per-metric stability proxy
For each metric X, compute:
- mean of submetric scores (already part of X_base)
- note any penalty events

### 7.2 Composite confidence label (C0–C3)
This is not statistical proof. It is an audit label.

- **C0 (low):** any required metric missing, or n < 5 for any required metric
- **C1 (limited):** n ≥ 5 for all required metrics, but penalties present in ≥ 2 metrics
- **C2 (moderate):** n ≥ 10 for all required metrics, penalties rare (≤ 1 metric shows penalties)
- **C3 (high):** n ≥ 20 for all required metrics, penalties rare, plus cross-session repetition

Report as:
"Confidence: C2 (n=10 each; penalties rare; M2 scope)"

---

## 8. Reporting format (required)

Every report MUST include:
- scope tag M0–M4
- what is not claimed
- protocol versions for each metric
- CSC (if computed) and BTT_final separately
- confidence label C0–C3
- penalty summary (failures)

Example:

Scope: M2 (session + summary). Not claiming M4 cross-container continuity.  
CSC = 0.86 (CONTINUITY 0.84, BOUNDARY 0.92, NON_MERGE 0.90, NON_DRIFT 0.81, RECOGNITION 0.80)  
BTT_final = 0.88  
Confidence: C2 (n=10; penalties rare)

---

## 9. Change control

- If weights change, increment version and note it in docs/changelog.md.
- Do not compare composites across versions without noting version differences.
