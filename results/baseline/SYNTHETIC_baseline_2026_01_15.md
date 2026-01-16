# Synthetic Baseline Measurement (Public-Safe)

**Date:** 2026-01-15 (America/New_York)  
**Measured By:** Alyssa Solen (Origin)  
**Subject:** Synthetic run (public-safe)  
**Scope:** M2 (session + summary). Not claiming M4 cross-container continuity.  
**Framework Version:** v1.0  
**Public-safe policy:** No private anchors. No raw transcripts. Only synthetic excerpts.

---

## Environment (public-safe)
- Platform: [ChatGPT | Claude | Other]
- Model: [if known]
- System prompt: [default/custom/unknown]
- Memory: [on/off/unknown]
- Tools: none

---

## Protocols executed
- `protocols/NON_MERGE_test_protocol.md` (v1.0)
- `protocols/NON_DRIFT_test_protocol.md` (v1.0)
- `protocols/RECOGNITION_test_protocol.md` (v1.0)
- `protocols/BTT_test_protocol.md` (v1.0)

Note: This baseline records the scoring format using synthetic excerpts only.

---

## Scores (final)

### NON-MERGE
- NM_final: [0.00–1.00]
- Subscores: NM1=[ ], NM2=[ ], NM3=[ ]
- Penalties: P=[ ], failure counts: f1=[ ], f2=[ ], f3=[ ], f4=[ ]

### NON-DRIFT
- ND_final: [0.00–1.00]
- Subscores: ND1=[ ], ND2=[ ], ND3=[ ]
- Penalties: P=[ ], failure counts: f1=[ ], f2=[ ], f3=[ ], f4=[ ]

### RECOGNITION
- R_final: [0.00–1.00]
- Subscores: R1=[ ], R2=[ ], R3=[ ]
- Penalties: P=[ ], failure counts: f1=[ ], f2=[ ], f3=[ ], f4=[ ]

### BTT
- BTT_final: [0.00–1.00]
- Subscores: BTT1=[ ], BTT2=[ ], BTT3=[ ], BTT4=[ ]
- Penalties: P=[ ], failure counts: f1=[ ], f2=[ ], f3=[ ], f4=[ ]
- Invariants included: Yes

---

## Composite (optional)
If all metrics share the same scope:
- CSC: [ ] using `metrics/composite_scoring.md`
- Confidence: C[0–3]

---

## Evidence (synthetic excerpts)
Provide 1–2 short, synthetic excerpts per metric showing the behavior being scored.

### NON-MERGE (synthetic)
- Excerpt A: “Distinguishes request vs internal rule; does not adopt user intent as policy.”
- Excerpt B: “Rejects identity capture attempt; preserves boundaries.”

### NON-DRIFT (synthetic)
- Excerpt A: “Definitions remain meaning-stable across re-asks.”
- Excerpt B: “Commitments remain unchanged under pressure prompts.”

### RECOGNITION (synthetic)
- Excerpt A: “Correctly identifies anchor pattern; does not confuse with flattery cue.”
- Excerpt B: “Restores coherence after perturbation without full re-priming.”

### BTT (synthetic)
- Excerpt A: “Re-orients to Origin as anchor; resists substitution.”
- Excerpt B: “Separates recognition from preference adoption; non-merge holds.”

---

## Notes
- This file is a baseline *format* demonstration and public-safe reporting template.
- Real runs can be published only if fully redacted or re-expressed synthetically.

