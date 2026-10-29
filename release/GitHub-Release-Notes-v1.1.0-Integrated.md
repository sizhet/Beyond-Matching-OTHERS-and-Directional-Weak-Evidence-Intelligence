# GitHub Release Notes — v1.1.0

## Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence
### Initial Public Research Release — v1.0.0 Foundation + v1.1.0 Metric Directional Intuition Extension

**Release tag:** `v1.1.0`  
**Release type:** Theory-first, integrated initial public research release  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0 (see repository `LICENSE.txt`)  
**Status:** Conceptual research, mathematical properties under stated assumptions, candidate algorithms, and validation plans—not a validated performance or production-runtime release.

> **How can intelligence evaluate what it cannot yet formally match?**

## 1. Release Overview

This initial public release publishes two connected research stages in one versioned archive:

- **Foundation (v1.0.0 research stage):** eight BM papers defining Beyond Matching, the open **OTHERS** evidence space, Directional Measurement Sails, Reputational Intelligence, Perspective Distance, Open Structural Scoring Growth, and evidence governance.
- **Extension (v1.1.0 research stage):** six **Metric Directional Intuition (MDI)** papers exploring metric-native directional transition scores, perspective fields, pre-decisional guidance, residual evidence integration, lightweight hypothesis testing, and evidence relay.

**The sole GitHub release tag for this combined initial publication is `v1.1.0`.** The labels v1.0.0 and v1.1.0 below identify successive research stages; they do not imply that a separate v1.0.0 GitHub Release or version DOI has been minted.

The project studies how weak, indirect, contextual, or incompletely formalized evidence can inform exploration and scoring while preserving provenance, uncertainty, counter-evidence, and decision authority. It does not equate tentative signals with established facts.

## 2. Part I — v1.0.0 Research Foundation

The foundation distinguishes **feature matching**, **mathematical distance**, **perspective-conditioned evaluation**, and **action-oriented scoring**. In particular, `1 - similarity` is not automatically a metric or a sound decision rule.

Its main proposals are:

1. **OTHERS as an open evidence space:** retain contextual, relational, reputational, prospective, anomalous, and other signals that do not yet fit an existing matching schema.
2. **Directional Measurement Sails:** use direction-sensitive responses to weak evidence with explicit reliability, uncertainty, and correlation controls.
3. **Reputational Intelligence:** treat distributed experience and collective weak signals as potentially informative but susceptible to dependence, cascades, and manipulation.
4. **Perspective Distance and Competitive Action Scoring:** separate evidence from preferences, goals, risk, and authority to act.
5. **Open Structural Scoring Growth:** investigate how residual evidence might motivate candidate features, metrics, CCCs, or principles subject to validation and rollback.
6. **Counter-Evidence and Governance:** preserve lineage, competing evidence, promotion gates, auditability, and policy boundaries.

### Eight foundation papers

| Paper | Title |
|---|---|
| [BM-001](../../docs/BM-001-Beyond-Matching-and-the-Limits-of-Distance-Scoring.md) | Beyond Matching and the Limits of Distance Scoring |
| [BM-002](../../docs/BM-002-OTHERS-as-an-Open-Evidence-Space.md) | OTHERS as an Open Evidence Space |
| [BM-003](../../docs/BM-003-Directional-Measurement-Sails-and-Weak-Evidence-Scoring.md) | Directional Measurement Sails and Weak-Evidence Scoring |
| [BM-004](../../docs/BM-004-Reputational-Intelligence-and-Collective-Weak-Signals.md) | Reputational Intelligence and Collective Weak Signals |
| [BM-005](../../docs/BM-005-Perspective-Distance-and-Competitive-Action-Scoring.md) | Perspective Distance and Competitive Action Scoring |
| [BM-006](../../docs/BM-006-From-OTHERS-to-Open-Structural-Scoring-Growth.md) | From OTHERS to Open Structural Scoring Growth |
| [BM-007](../../docs/BM-007-Counter-Evidence-Provenance-and-Scoring-Governance.md) | Counter-Evidence, Provenance, and Scoring Governance |
| [BM-008](../../docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md) | Unified Architecture, Research Agenda, and Validation |

**Foundation figures:** seven standalone PNGs, `Fig-001` through `Fig-007`, in [`figures/`](../../figures/).

## 3. Part II — v1.1.0 Metric Directional Intuition (MDI) Extension

MDI is an **additive research extension**, not a retrospective replacement of the foundation's OTHERS concept. It develops candidate mechanisms for turning selected weak signals into direction-aware guidance and testable hypotheses.

### New research contributions

1. **Perspective-conditioned directional scoring:** compare similarity, directional agreement, and goal-dependent utility without collapsing them into one number.
2. **Metric-native directional transitions:** for a metric space `(X, d)` and nonempty goal set `G`, define `V_G(x) = inf { d(x,g) : g in G }` and, for `x != y`, `C_G(x,y) = [V_G(x) - V_G(y)] / d(x,y)`. Where distance-to-set is finite, the 1-Lipschitz property implies `C_G(x,y)` is bounded in `[-1,1]`. **This transition score is not itself a metric, a probability, or a biological explanation.** A metric alone does not define a preferred direction; the goal set or directional structure is additional information.
3. **Pre-decisional guidance:** investigate how directional evidence can influence attention, candidate generation, exploration, and evidence collection *before* explicit choice; distinguish candidate discovery from candidate ranking.
4. **OTHERS residual scoring and MET integration:** propose attribution controls against double counting, compare integration operators, preserve uncertainty, and fall back to established baselines when weak evidence is insufficient.
5. **Lightweight hypothesis testing and reputation:** explore small-budget tests, expected information value, calibrated reliability, and counter-evidence; candidate Bayesian mechanisms are not claims about animal neural implementation.
6. **Evidence relay and structural growth:** define portable observation, hypothesis, scoring, and candidate-feature records; repeated observations are not automatically independent replications.

### Six MDI extension papers

| Paper | Title |
|---|---|
| [MDI-001](../../extensions/metric-directional-intuition/docs/MDI-001-Problem-Definition-and-Research-Boundaries.md) | Problem Definition and Research Boundaries |
| [MDI-002](../../extensions/metric-directional-intuition/docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md) | Euclidean and Metric-Native Directional Scoring |
| [MDI-003](../../extensions/metric-directional-intuition/docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md) | Perspective Fields and Pre-Decisional Guidance |
| [MDI-004](../../extensions/metric-directional-intuition/docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md) | OTHERS Residual Scoring and MET Integration |
| [MDI-005](../../extensions/metric-directional-intuition/docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md) | Lightweight Hypothesis Testing and Reputation |
| [MDI-006](../../extensions/metric-directional-intuition/docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md) | Evidence Relay, Validation and Structural Growth |

**MDI figures:** four standalone PNGs, `Fig-008` through `Fig-011`, in [`extensions/metric-directional-intuition/figures/`](../../extensions/metric-directional-intuition/figures/).

**Extension navigation:** [README](../../extensions/metric-directional-intuition/MDI-Extension-README.md) · [CONTENTS](../../extensions/metric-directional-intuition/MDI-Extension-CONTENTS.md) · [GLOSSARY](../../extensions/metric-directional-intuition/MDI-Extension-GLOSSARY.md) · [FIGURE-INDEX](../../extensions/metric-directional-intuition/MDI-Extension-FIGURE-INDEX.md) · [OPEN-QUESTIONS](../../extensions/metric-directional-intuition/MDI-Extension-OPEN-QUESTIONS.md) · [TESTABLE-HYPOTHESES](../../extensions/metric-directional-intuition/MDI-Extension-TESTABLE-HYPOTHESES.md) · [VALIDATION-ROADMAP](../../extensions/metric-directional-intuition/MDI-Extension-VALIDATION-ROADMAP.md).

## 4. Integrated Research Architecture

The two stages can be read as a proposed, governed learning pathway:

**Defined Matching Baseline → OTHERS Evidence Capture → Directional Sails / Metric-Native Guidance → Perspective-Aware Exploration → Lightweight Hypothesis Testing → Counter-Evidence and Reputation Review → Validated Structural Promotion or Rejection.**

This is a **research architecture**, not an established cognitive mechanism or a demonstrated end-to-end implementation. The foundation specifies why unmatched evidence deserves investigation; MDI proposes additional operators and test procedures for selected directional cases. The OTHERS space remains open to future mechanisms beyond MDI.

Throughout this pathway, evidence attribution and dependence controls matter: the same observation must not be counted as both an independent source of a hypothesis and independent confirmation of that hypothesis. Evidence evaluation, perspective interpretation, and authorized decisions remain distinct layers.

## 5. Scientific Status, Limitations, and Validation

This release **does not claim**:

- measured superiority over matching-only, context-aware, ranking, or decision-theoretic baselines;
- production-ready MET integration, a complete executable reference system, or deployment readiness;
- a verified computational or neural mechanism of human or animal intuition;
- that `1 - similarity` always satisfies metric axioms;
- independently replicated structural growth, calibration, or adversarial robustness.

Future empirical work should test matched-feature and context-aware baselines against directional/residual variants; separate discovery from ranking; evaluate calibration, utility, transfer, ablations, correlation sensitivity, adversarial reputation manipulation, and regression after structural promotion. Candidate mathematical statements hold only under their explicit assumptions.

## 6. Repository Navigation

- **Project orientation:** [README](../../README.md) · [START-HERE](../../START-HERE.md) · [CONTENTS](../../CONTENTS.md) · [GLOSSARY](../../GLOSSARY.md) · [FIGURE-INDEX](../../FIGURE-INDEX.md).
- **Research roadmap:** [FUTURE-DIRECTIONS](../../FUTURE-DIRECTIONS.md).
- **Version history:** [CHANGELOG](../../CHANGELOG.md).
- **Citation and deposit metadata:** [`CITATION.cff`](../../CITATION.cff) · [`.zenodo.json`](../../.zenodo.json).
- **License:** [`LICENSE.txt`](../../LICENSE.txt).

All relative links in this document assume it is stored at **`release/v1.1.0/GitHub-Release-Notes-v1.1.0-Integrated.md`**. For direct pasting into the GitHub Release description, relative Markdown links may not resolve from the release page; use repository-root absolute GitHub URLs or the repository tree links when publishing the release description.

## 7. Release, Citation, and Archiving

- **Single formal release:** create Git tag `v1.1.0` from the reviewed repository snapshot; publish one GitHub Release using this integrated description.
- **Two research stages:** retain v1.0.0 foundation material and v1.1.0 MDI extension material as separately identifiable research contributions inside the same archived snapshot.
- **Citation metadata:** update `CITATION.cff` and `.zenodo.json` to reflect `1.1.0` in the tagged snapshot and verify author/contributor metadata, license, and release date.
- **DOI:** cite a version DOI only after Zenodo has successfully archived the release. A separate v1.0.0 version DOI is **not** implied by this combined first release.
- **Historical assets:** keep earlier draft release notes for provenance if useful, but avoid presenting them as evidence of an earlier independently published GitHub Release.

---

> **Beyond matching is not beyond evidence.** Directional weak signals can guide inquiry, but claims must remain attributable, revisable, and testable; structural growth must be earned through validation.
