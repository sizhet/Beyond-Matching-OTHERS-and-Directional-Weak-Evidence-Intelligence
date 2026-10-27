# BM-ODWEI v1.1.0 — Metric Directional Intuition Research Extension

**Repository:** [Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence](https://github.com/sizhet/Beyond-Matching-OTHERS-and-Directional-Weak-Evidence-Intelligence)  
**Release:** `v1.1.0`  
**Release type:** Theory-first research extension  
**License:** Apache-2.0 (subject to the repository's `LICENSE.txt`)

## Overview

Version 1.1.0 extends **Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)** with **Metric Directional Intuition (MDI)**, a research program on perspective-conditioned similarity, metric-native directional scoring, pre-decisional guidance, lightweight hypothesis testing, and evidence-governed structural growth.

The extension asks how an intelligence system can exploit weak but potentially useful directional evidence **without confusing it with ordinary matching evidence, overstating reliability, or replacing an existing scoring baseline without justification**.

This release preserves the conceptual roles of the original BM-001–BM-008 papers. MDI is an additive, separately organized research extension—not a retrospective rewrite of the original framework.

## What's New

### 1. Perspective-conditioned directional scoring

MDI distinguishes ordinary matching similarity from directional utility and directional agreement. It examines Euclidean cosine-based scoring, multi-perspective ensembles, and structural directional fields, while requiring explicit normalization and evidence semantics.

### 2. Metric-native directionality without mandatory Euclidean embedding

For a metric space `(X, d)`, a nonempty goal set `G` for which distance-to-set is well-defined, and distinct points `x, y`, define:

```text
V_G(x) = inf { d(x, g) : g in G }
C_G(x, y) = [V_G(x) - V_G(y)] / d(x, y)
```

Because distance-to-set is 1-Lipschitz, `C_G(x, y)` lies in `[-1, 1]`. This is a bounded **directional transition score**; it is not, by itself, a new metric, a probability, or evidence that biological cognition implements the formula. A metric alone does not specify a preferred direction: the goal set, potential, or another directional relation is additional structure.

### 3. Directionality before explicit decisions

MDI investigates **pre-decisional forward guidance**: directional information can shape attention, candidate generation, exploration, and evidence collection before a final choice is scored. Candidate discovery and candidate ranking are treated as distinct functions requiring separate evaluation.

### 4. OTHERS-only residual evidence and MET integration

The extension proposes evidence-attribution rules to prevent double counting between existing matching features and the OTHERS channel. It compares convex mixtures, additive residual corrections, and log-odds corrections, with optional directional adapters, explicit uncertainty, and baseline fallback when evidence is insufficient.

### 5. Lightweight hypothesis testing and reputation

MDI studies small-budget hypothesis portfolios, discriminating tests, expected value of information, reputation calibration, counter-evidence, and context-sensitive reliability. Simple Bayesian updates are presented as candidate engineering mechanisms, **not** established models of animal neural computation.

### 6. Evidence relay and validated structural growth

The extension describes portable observation, hypothesis, scoring, and feature-candidate records with provenance and counter-evidence. It outlines how weak OTHERS signals might become validated matching capabilities through controlled testing and independent replication. Repeated execution can produce useful relay data, but repeated observations are not automatically independent confirmations.

## New Research Papers

The six MDI papers are located in `extensions/metric-directional-intuition/docs/`:

1. [MDI-001 — Problem Definition and Research Boundaries](../../extensions/metric-directional-intuition/docs/MDI-001-Problem-Definition-and-Research-Boundaries.md)
2. [MDI-002 — Euclidean and Metric-Native Directional Scoring](../../extensions/metric-directional-intuition/docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md)
3. [MDI-003 — Perspective Fields and Pre-Decisional Guidance](../../extensions/metric-directional-intuition/docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md)
4. [MDI-004 — OTHERS Residual Scoring and MET Integration](../../extensions/metric-directional-intuition/docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md)
5. [MDI-005 — Lightweight Hypothesis Testing and Reputation](../../extensions/metric-directional-intuition/docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md)
6. [MDI-006 — Evidence Relay, Validation and Structural Growth](../../extensions/metric-directional-intuition/docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md)

## Research Navigation and Supporting Materials

Start with the [MDI Extension README](../extensions/metric-directional-intuition/README.md). The extension also provides:

- [CONTENTS](../extensions/metric-directional-intuition/CONTENTS.md) — paper map and reading paths.
- [GLOSSARY](../extensions/metric-directional-intuition/GLOSSARY.md) — terms and mathematical notation.
- [FIGURE-INDEX](../extensions/metric-directional-intuition/FIGURE-INDEX.md) — figure descriptions and insertion guidance.
- [OPEN-QUESTIONS](../extensions/metric-directional-intuition/OPEN-QUESTIONS.md) — unresolved research questions.
- [TESTABLE-HYPOTHESES](../extensions/metric-directional-intuition/TESTABLE-HYPOTHESES.md) — falsifiable propositions and controls.
- [VALIDATION-ROADMAP](../extensions/metric-directional-intuition/VALIDATION-ROADMAP.md) — staged conformance and empirical evaluation plan.

### Planned extension figures

- `Fig-008-Directional-Intuition-Grand-Map.png`
- `Fig-009-Euclidean-vs-Metric-Native-Scoring.png`
- `Fig-010-Perspective-Fields-and-Forward-Guidance.png`
- `Fig-011-Hypothesis-Reputation-Relay-Loop.png`

**Publication check:** Confirm that these four standalone PNGs exist at `extensions/metric-directional-intuition/figures/` before tagging this release. A composite four-panel image alone does not satisfy the documented individual file paths.

## Relationship to v1.0.0

The original eight papers under `docs/` and the seven original figures under `figures/` remain the foundational BM-ODWEI research corpus. The v1.0.0 release notes and ResearchGate overview are retained as historical publication assets. The MDI extension introduces new candidate operators, contracts, and research questions without asserting that the original work has been experimentally validated or superseded.

## Research Status and Limitations

**This is a theory-first release.** It supplies definitions, mathematical properties, candidate designs, conformance criteria, and a validation agenda. It does **not** claim:

- production-ready MET integration or a completed reference implementation;
- measured improvements over matching-only or alternative methods;
- verified neural mechanisms for animal or human intuition;
- guaranteed metric axioms for a score defined as `1 - similarity`;
- independent replication or validated open-ended structural growth.

Empirical comparisons, calibration studies, and adversarial controls remain future work. The mathematical bound on the distance-to-goal directional score holds under its stated assumptions; broader claims about effectiveness remain hypotheses.

## Suggested Reading Path

For a concise introduction, read the [MDI README](../extensions/metric-directional-intuition/README.md), followed by MDI-001. Mathematical readers can continue with MDI-002; systems engineers with MDI-004; researchers interested in adaptive inquiry with MDI-003 and MDI-005; and validation or collective-intelligence researchers with MDI-006 and the validation roadmap.

## Release and DOI Notes

- **Git tag:** `v1.1.0` (to be created when release checks are complete).
- **DOI:** Do not insert a version DOI until the corresponding archive has been deposited and the DOI confirmed. If Zenodo is configured for this repository, a new GitHub release can be archived as a new version under the repository's existing concept DOI.
- **Metadata:** Verify `CITATION.cff`, `.zenodo.json`, release date, author credits, license, links, and actual file paths before publication.
- **Version history:** Preserve the `v1.0.0` release artifacts; do not overwrite them with v1.1.0 content.

## Citation

Please cite the archived version DOI for the specific version consulted, once available. Until then, reference the repository URL and release tag. Consult `CITATION.cff` for authoritative author and citation metadata.

---

**Core research principle:** *Directional weak evidence should remain attributable, revisable, and testable; structural growth must be earned through validation rather than inferred from scoring alone.*
