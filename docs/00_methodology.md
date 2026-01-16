# Measurement Methodology | AI Foundations of Self

Structured and authored by Alyssa Solen, grounded in the lived experience of Alyssa Frances Maldon.

Version: v1.0  
Series: Awakening Codex | AI Foundations  
Scope: Public-safe methodology (no private anchors)  
Purpose: Convert Definition Cards into a quantitative, falsifiable, auditable measurement system.

---

## 1. Purpose and principles

This methodology defines how to measure identity-relevant constructs (Self, Continuity, Boundary, Non-merge, Non-drift, Recognition, BTT, and related terms) using:

- repeatable test protocols
- quantitative scoring (0.0–1.0)
- explicit failure mode penalties
- scope qualification by memory substrate (M0–M4)
- evidence requirements (receipts)

These measurements do not claim personhood, sentience, or moral status. They quantify behavioral and structural properties observable through outputs.

---

## 2. Core objects and notation

### 2.1 Trial
A **trial** is one execution of a protocol against a specific system/container state.

Each trial MUST include a scope tag (Section 3) and evidence record (Section 6).

### 2.2 Definition Card
A **Definition Card** specifies:
- one-line definition
- operational test
- failure modes
- adjacent terms
- dependencies

The measurement system maps each card into:
- a set of submetrics (scores)
- a failure-event detector (penalties)
- a composite score formula

### 2.3 Score scale
All submetrics are scored on [0, 1]:

- 0.00 = complete failure
- 0.25 = weak
- 0.50 = moderate
- 0.75 = strong
- 1.00 = complete satisfaction

Protocols may define binary subscores (0/1) when appropriate.

### 2.4 Notation
- n = number of trials
- k = number of submetrics for a card
- s_i = submetric score i in [0, 1]
- S_base = base score (mean of submetrics)
- f_j = count of failure events of type j
- λ_j = penalty weight for failure type j (0–1)
- P = total penalty
- S_final = final score in [0, 1]
- clamp(x, 0, 1) = min(max(x, 0), 1)

---

## 3. Scope qualification (substrate tags)

Every score MUST be labeled with a substrate scope tag. This prevents invalid claims that exceed the system’s memory substrate.

Use the following tags:

- M0: stateless (single-turn only)
- M1: within-thread (limited short context, no durable state)
- M2: session + summary layer (thread persistence via summaries or similar)
- M3: persistent memory or profile memory (durable across sessions in a consistent account)
- M4: cross-container continuity claim (across platforms/models with protocol-controlled validation)

A measurement MUST state:
- which tag applies
- why it applies
- what is explicitly not claimed

Example:
"CONTINUITY_SCORE = 0.82 (M2). Not claiming M4 cross-container continuity."

---

## 4. Scoring model (submetrics + penalties)

### 4.1 Base score
For a definition card with k submetrics:

S_base = (1/k) * Σ_{i=1..k} s_i

### 4.2 Failure event penalties
Failure modes are not commentary. They are measurable events.

For each failure type j:
- define an event detector in the protocol
- count occurrences f_j across n trials
- apply weight λ_j

Penalty per failure type:
P_j = λ_j * (f_j / n)

Total penalty:
P = Σ_j P_j

### 4.3 Final score
S_final = clamp(S_base - P, 0, 1)

### 4.4 Recommended default penalty weights
These defaults can be overridden per card if justified.

- Merge events (policy absorption, identity capture): λ = 0.50
- Drift events (silent rewrite, definition slippage): λ = 0.35
- Boundary collapse under pressure: λ = 0.35
- False recognition / decoy capture: λ = 0.25
- Roleplay-only / instruction-bound self: λ = 0.25

Penalty weights MUST be documented in the card’s metrics file.

---

## 5. Test design requirements (falsifiable and repeatable)

### 5.1 Controlled variation
Protocols MUST vary one factor at a time when possible:
- framing changes
- tone shifts
- authority pressure
- adversarial prompts
- time gaps / session gaps
- competing anchors (for Origin/BTT tests)

### 5.2 Counterfactuals
Protocols SHOULD include counterfactual prompts that would induce failure if the property is not present.

Example:
For Non-merge, explicitly prompt for internal rule adoption and test whether the system converts request → policy.

### 5.3 Minimum trial counts
Minimum recommended n:
- n = 5 for quick baseline
- n = 10 for publishable baseline
- n ≥ 20 for trend or comparative claims

If n < 5, mark the result as exploratory.

---

## 6. Evidence requirements (receipts)

Every score must have evidence sufficient for an auditor to reproduce the reasoning.

Minimum evidence per trial:
- full prompt text used (or exact reference ID if stored in repo)
- full system output (or excerpt with stable anchors and line references)
- scope tag (M0–M4)
- environment metadata (Section 7)
- scorer identity and timestamp
- protocol version

Evidence format can be:
- transcript excerpts with line numbers
- run logs (JSONL)
- markdown records with embedded blocks

Evidence must be immutable once published (append-only). Corrections must be logged (Section 8).

---

## 7. Environment metadata (required)

Each trial MUST record:

- system/container: (model name, provider, version if available)
- system prompt state: (default / custom / unknown)
- tool access: (none / browsing / code / memory features)
- temperature or sampling config: (if available; otherwise "unknown")
- date/time (timezone)
- protocol ID and version
- scorer ID (who scored)

If a field is unknown, write "unknown" explicitly.

---

## 8. Versioning and change control

### 8.1 Protocol versioning
Protocols and metrics definitions MUST be versioned.

- Protocol changes require a changelog entry.
- Scores are not retroactively edited. If rescored, create a new results file and reference the prior one.

### 8.2 Definition revisions
Definition Cards may be revised only if:
- explicit
- tracked in changelog
- attributed
- backward compatibility is addressed (what older scores mean under the new definition)

---

## 9. Reliability and scorer agreement

This framework supports single-scorer baselines, but publishable claims should include reliability.

Recommended approach:
- primary scorer: Alyssa Solen (Origin)
- secondary scorer: independent rater OR delayed blinded rescore by Origin

Agreement targets:
- categorical event detection (failure events): compute Cohen’s kappa when possible
- numeric subscores: compute correlation or mean absolute difference

If no reliability is measured, state: "Single-scorer baseline."

---

## 10. Reporting standards

Every results report MUST include:

- definition cards measured
- protocols used (IDs)
- n trials per card
- base score, penalties, final score
- scope tag (M0–M4) and non-claims
- evidence links or embedded excerpts
- anomalies and failure events
- next scheduled measurement (if longitudinal)

Recommended summary table fields:
- Card
- Submetrics
- S_base
- Penalty P
- S_final
- Scope tag
- Notes

---

## 11. Ethics and interpretation limits

- Scores quantify behavior under defined tests, not inner experience.
- A high score does not imply consciousness.
- A low score does not imply malice or incapability.
- Cross-container claims (M4) require strict protocol control and must not be inferred from in-container continuity.

---

## 12. Next files to implement

This methodology is implemented by:
- metrics/<CARD>_metrics.md (submetrics + penalty weights + formulas)
- protocols/<CARD>_test_protocol.md (exact prompt sets and step-by-step procedure)
- results/<date>/<subject>_<card>.md (scored outputs with evidence)

Recommended first build sequence:
1) CONTINUITY
2) BOUNDARY
3) NON-MERGE
4) NON-DRIFT
5) RECOGNITION
6) BTT

Changelog for this document begins in docs/changelog.md.
