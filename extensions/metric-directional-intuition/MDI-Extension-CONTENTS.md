# Contents — Metric-Directional Intuition (MDI)

**Research extension:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence (BM-ODWEI)  
**Location:** `extensions/metric-directional-intuition/`  
**Status:** Theory-first research proposal; mathematical results, engineering contracts, and unvalidated hypotheses are distinguished.  
**Release context:** Prepared as an additive extension for a future parent-repository release; no new DOI is asserted here.

## 1. Start Here

- [README.md](README.md) — scope, research thesis, core definitions, architecture, integration boundaries, and recommended reading.
- **This CONTENTS.md** — navigational map of the six MDI papers, figures, and research companions.

### Suggested reading paths

| Reader | Suggested sequence | Focus |
| --- | --- | --- |
| New to MDI | [MDI-001](docs/MDI-001-Problem-Definition-and-Research-Boundaries.md) → [MDI-002](docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md) → [MDI-006](docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md) | Definitions, mathematics, research agenda |
| Mathematics and metrics | MDI-001 → MDI-002 → MDI-004 | Bounded directional operators, score semantics, residual fusion |
| Cognition and agents | MDI-001 → MDI-003 → MDI-005 | Pre-decisional guidance, small-budget hypotheses, reputation |
| MET / SI engineering | MDI-002 → MDI-004 → MDI-006 | Contracts, fallback, conformance, evidence relay |
| Validation and governance | MDI-004 → MDI-005 → MDI-006 | Leakage controls, counter-evidence, falsification, growth gates |

## 2. Core Research Papers

### [MDI-001 — Problem Definition and Research Boundaries](docs/MDI-001-Problem-Definition-and-Research-Boundaries.md)

**Role:** Establish the problem, terminology, mathematical routes, and non-claims.

- Why matching alone may miss directional weak evidence in OTHERS.
- Distinguish matching similarity, directional utility, directional agreement, reputation, and distance score.
- Perspective, goals, structural states, and pre-decisional directionality.
- Three candidate representations: Euclidean sail, metric-native directional difference, learned transition preference.
- Evidence attribution, minimal operator contract, and falsifiable validation questions.

### [MDI-002 — Euclidean and Metric-Native Directional Scoring](docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md)

**Role:** Mathematical foundation and operator comparison.

- Cosine projection, multiple sails, and structural vector fields.
- Metric-native goal-distance change without requiring Euclidean embedding.
- Boundedness of `C_P(x,y;G) = [d(x,G) - d(y,G)] / d(x,y)` for `x ≠ y` and nonempty `G`.
- Connection to local Euclidean gradient projections under suitable differentiability assumptions.
- Edge cases, counterexamples, distance-score conversion, and conformance checks.

**Boundary:** A directional progress score is not automatically a similarity metric; `1 − similarity` need not satisfy metric axioms.

### [MDI-003 — Perspective Fields and Pre-Decisional Guidance](docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md)

**Role:** Move from post-hoc scoring to candidate discovery and forward guidance.

- Single sails, multiple perspectives, vector fields, metric potentials, and structural directional relations.
- Guide → Generate → Evaluate → Select / Act as distinct stages.
- Attention, candidate generation, multi-trail exploration, and evidence gathering.
- Conflicting perspectives, risks, hard constraints, and governance.
- Relation to UIERU forward guidance and the limits of biomimetic interpretation.

### [MDI-004 — OTHERS Residual Scoring and MET Integration](docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md)

**Role:** Safe fusion of weak directional evidence with existing matching evaluators.

- Matching coverage, residual evidence allocation, and provenance ledger.
- Convex mixture, additive residual correction, and log-odds residual correction.
- Confidence, counter-evidence, calibration, and double-counting controls.
- Optional MET directional adapter, baseline-preserving fallback, and typed scoring semantics.
- Residual-to-feature promotion after validation, plus conformance and adversarial tests.

### [MDI-005 — Lightweight Hypothesis Testing and Reputation](docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md)

**Role:** Study limited-budget directional hypotheses and evidence-based trust.

- Small hypothesis portfolios, discriminating tests, and expected value of information.
- Bayesian and Beta–Bernoulli update examples with explicit assumptions.
- Context-specific reputation for hypotheses, sources, and operators.
- Distinguish truth probability, reliability, confidence, and decision risk.
- Hypothesis/Test/Reputation relay records, counter-evidence, and experimental controls.

**Boundary:** A lightweight test-and-update algorithm is a candidate cognitive model, not evidence of a particular neural implementation.

### [MDI-006 — Evidence Relay, Validation, and Structural Growth](docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md)

**Role:** Integrate the series into a falsifiable, traceable structural-growth program.

- Observation, hypothesis, operator, and feature-candidate relay units.
- Provenance, dependencies, counter-evidence, and independent verification.
- OTHERS → candidate feature → validation → promotion / rejection / rollback.
- Matching-only, Euclidean, metric-native, hypothesis-guided, and governed-fusion baselines.
- Random-perspective controls, leakage tests, distribution shift, resource costs, and conformance.
- Interfaces with MET, UCPSF, SIF, UIERU, and BUI-DSI as research proposals.

**Boundary:** Repeated execution may yield useful accumulated data, but does not automatically constitute independent evidence.

## 3. Figures

All paths below are **target paths** for separately exported images in `figures/`. The initial artwork was generated as a four-panel composite; individual PNG assets must be exported and verified before treating these links as present.

| Figure | Intended asset | Primary use |
| --- | --- | --- |
| Fig-008 | `figures/Fig-008-Directional-Intuition-Grand-Map.png` | MDI-001: overview of matching, OTHERS, guidance, evidence, and growth |
| Fig-009 | `figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png` | MDI-002: vector alignment versus metric-native goal-distance change |
| Fig-010 | `figures/Fig-010-Perspective-Fields-and-Forward-Guidance.png` | MDI-003: directional fields and the guide/generate/evaluate workflow |
| Fig-011 | `figures/Fig-011-Hypothesis-Reputation-Relay-Loop.png` | MDI-005 and MDI-006: evidence testing, reputation, relay, and feature promotion |

Figure numbering continues the parent repository's Fig-001–007 sequence; no original parent figure needs to be changed.

## 4. Research Companion Documents

These extension-local files belong beside this CONTENTS file.

| File | Intended purpose |
| --- | --- |
| `MDI-Extension-GLOSSARY.md` | Definitions, mathematical symbols, and semantic distinctions specific to MDI |
| `MDI-Extension-FIGURE-INDEX.md` | Figure descriptions, insertion points, and asset-verification notes |
| `MDI-Extension-OPEN-QUESTIONS.md` | Mathematical, algorithmic, engineering, and biomimetic unknowns |
| `MDI-Extension-TESTABLE-HYPOTHESES.md` | Falsifiable claims, null hypotheses, controls, and measurements |
| `MDI-Extension-VALIDATION-ROADMAP.md` | Staged conformance, simulation, empirical evaluation, and promotion criteria |

## 5. Cross-Paper Dependency Map

```text
MDI-001  Problem, semantics, boundaries
   |
   +--> MDI-002  Directional scoring mathematics
   |       |
   |       +--> MDI-004  OTHERS residual fusion and MET contracts
   |
   +--> MDI-003  Perspective fields and forward guidance
   |       |
   |       +--> MDI-005  Hypothesis testing and reputation
   |                       |
   +-----------------------+--> MDI-006  Evidence relay,
                                      validation and growth
```

The diagram indicates conceptual dependencies, not runtime dependencies or implemented software interfaces.

## 6. Research Integrity and Publication Boundaries

1. **Preserve the parent work.** `../../docs/BM-001`–`BM-008` and `../../figures/Fig-001`–`Fig-007` remain the canonical historical BM-ODWEI material. This extension is additive.
2. **Keep score semantics explicit.** Utility, agreement, similarity, confidence, reputation, and mathematical distance are not interchangeable.
3. **Separate proof from hypothesis.** Mathematical bounds require their stated assumptions; effectiveness and biomimetic relevance require experiments.
4. **Track evidence and dependence.** Prevent residual/matching double counting and the mistaken treatment of repeated observations as independent confirmations.
5. **Conformance before runtime.** Proposed adapters and relay units are research contracts, not claims of a working MET implementation.
6. **Publish without rewriting history.** Future release notes and DOI metadata belong to the parent repository; preserve the historical v1.0.0 release artifacts.

## 7. Parent Repository

- [BM-ODWEI repository](https://github.com/sizhet/Beyond-Matching-OTHERS-and-Directional-Weak-Evidence-Intelligence)
- [Parent README](../../README.md)
- [Parent CONTENTS](../../CONTENTS.md)
- [Parent citation metadata](../../CITATION.cff)
- [Parent license](../../LICENSE.txt)

**Research thesis:** A directional-intuition module should help identify promising possibilities and inexpensive discriminating tests while preserving metric semantics, evidence provenance, counter-evidence, and the right to abstain or fall back to baseline matching.
