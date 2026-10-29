# START HERE — Beyond Matching and OTHERS Intelligence

**Project:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence  
**Authors:** Sizhe Tan & GPT-Obot  
**Release:** v1.0.0 — Research foundation  
**License:** Apache-2.0  
**Status:** Conceptual framework and proposed algorithms; experimental benefits have not yet been established.

> **Central question:** How can an intelligent system evaluate consequential signals that its current feature-matching representation cannot yet formally express?

## 1. The Project in One Minute

A similarity score is not automatically a meaningful *perspective distance*, and neither is automatically a good *action decision*. Real-world assessments also depend on indirect observations, context, social reputation, emerging trends, anomalies, uncertainty, and the goals of an authorized decision-maker.

We call the **currently unmodeled or incompletely formalized evidence space** **OTHERS**. The project proposes **Directional Measurement Sails (DMS)** as one possible way to measure the effects of heterogeneous weak evidence along distinct evaluation directions. Reliable signals may eventually become explicit features, metrics, cross-domain concepts (CCC), or principles through **Open Structural Scoring Growth (OSSG)**.

The design keeps **evidence**, **perspective**, and **decision** separate. Reputation and weak signals are leads for investigation—not automatic proof.

## 2. Choose a Reading Path

### Ten-minute orientation

1. Read [README.md](README.md) for the problem, architecture, and core claims.
2. Read [BM-001 — Beyond Matching and the Limits of Distance Scoring](docs/BM-001-Beyond-Matching-and-the-Limits-of-Distance-Scoring.md) for the mathematical and conceptual boundary.
3. Skim [BM-008 — Unified Architecture, Research Agenda, and Validation](docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md) for the complete system and test plan.

### Algorithm and engineering path

1. [BM-002 — OTHERS as an Open Evidence Space](docs/BM-002-OTHERS-as-an-Open-Evidence-Space.md): What enters the system?
2. [BM-003 — Directional Measurement Sails and Weak-Evidence Scoring](docs/BM-003-Directional-Measurement-Sails-and-Weak-Evidence-Scoring.md): How might direction-specific evidence be scored?
3. [BM-006 — From OTHERS to Open Structural Scoring Growth](docs/BM-006-From-OTHERS-to-Open-Structural-Scoring-Growth.md): How might validated evidence become reusable structure?
4. [BM-007 — Counter-Evidence, Provenance, and Scoring Governance](docs/BM-007-Counter-Evidence-Provenance-and-Scoring-Governance.md): What controls failure, manipulation, and unjustified promotion?

### Social and decision-science path

1. [BM-004 — Reputational Intelligence and Collective Weak Signals](docs/BM-004-Reputational-Intelligence-and-Collective-Weak-Signals.md): Indirect social information and collective signals.
2. [BM-005 — Perspective Distance and Competitive Action Scoring](docs/BM-005-Perspective-Distance-and-Competitive-Action-Scoring.md): Perspective, asymmetry, goals, and action consequences.
3. [BM-008 — Unified Architecture, Research Agenda, and Validation](docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md): How to compare the proposal with existing methods.

## 3. Seven Ideas to Keep Distinct

| Concept | Working meaning | Not to be confused with |
|---|---|---|
| Matching score | Similarity under a chosen representation | Universal decision relevance |
| Metric distance | A distance satisfying specified mathematical axioms | Any transformed similarity score |
| Perspective distance | Difference interpreted under a perspective and context | Necessarily symmetric metric distance |
| OTHERS | Evidence not adequately represented by current matched features | An unrestricted pool of facts |
| Directional Measurement Sail | Candidate response function for a scoring direction | A validated sensor or proven algorithm |
| Reputation / collective signals | Indirect, socially transmitted evidence | Independent or necessarily truthful observations |
| Action scoring | Goal-, risk-, and authority-dependent choice | Objective evidence assessment |

In particular, `D = 1 - S` can be a useful dissimilarity transformation for normalized similarity, but it does **not** generally yield a metric or an action-cost function.

## 4. Minimal Architecture

```text
Observed world and heterogeneous signals
                 |
                 v
      Evidence + provenance
                 |
                 v
    Matched features + OTHERS
                 |
                 v
   Directional Measurement Sails
                 |
                 v
  Reputation / weak-evidence assessment
                 |
                 v
    Perspective interpretation
                 |
                 v
  Authorized, governed action choice
                 |
                 v
  Feedback, challenge, validation
                 |
                 v
  Candidate structural promotion
                 |
                 +----> Features / Metrics / CCC / Principles
                 |
                 +----> Unresolved OTHERS remains open
```

**Governance is cross-cutting:** provenance, evidence independence, counter-evidence, uncertainty, calibration, permission checks, and rollback apply throughout the lifecycle.

## 5. The Core Growth Cycle

**Capture → Sense → Propose → Challenge → Promote → Reassess**

A weak signal can influence an *investigation* before it qualifies as an established feature. Repeated directional effects may motivate candidate structures. Only independent testing, counter-evidence, and explicit promotion gates can justify making those structures authoritative. Failed candidates remain revisable or are rolled back.

## 6. What the Repository Does — and Does Not — Claim

**Proposes:** a common architecture connecting open evidence, direction-dependent scoring, reputation-aware aggregation, perspective interpretation, and governed structural learning.

**Does not claim:** that all cross-domain AI judgments are worse than human judgments; that reputation is inherently accurate; that directional sails have already demonstrated a performance advantage; or that multi-criteria decision analysis, weak-signal management, or reputation models were invented here.

The research must be compared with established decision-science, social-network, reputation-system, Bayesian, and machine-learning baselines. Proposed novelty is concentrated in the *integration and growth interfaces*, subject to literature review and empirical validation.

## 7. How to Evaluate the Proposal

A useful first benchmark compares:

- **A:** matched-feature scoring only;
- **B:** matched features plus explicit context;
- **C:** B plus directional weak-evidence scoring;
- **D:** C plus perspective- and goal-aware action selection.

Evaluate prediction/ranking quality, calibration, action utility, out-of-distribution performance, source-dependence robustness, adversarial reputation contamination, and the cost of mistaken structural promotion. Use ablations to identify which subsystem provides any observed benefit. See [BM-008](docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md).

## 8. Figures and Navigation

The seven standalone figures are listed below; their paths become active when the corresponding PNG files are installed under `figures/`:

| Figure | Subject |
|---|---|
| `Fig-001-Beyond-Matching-Grand-Map.png` | Overall conceptual map |
| `Fig-002-Matching-vs-Perspective-Distance.png` | Formal matching versus situated assessment |
| `Fig-003-Directional-Measurement-Sails.png` | Multi-direction weak-signal response |
| `Fig-004-Reputational-Collective-Signals.png` | Source-aware collective reputation |
| `Fig-005-OTHERS-Structural-Growth-Loop.png` | Evidence-to-structure growth cycle |
| `Fig-006-Evidence-Perspective-Decision-Planes.png` | Separation of evidence, interpretation, and choice |
| `Fig-007-Unified-Open-Scoring-Architecture.png` | Full integration and interfaces |

For the complete research overview, return to [README.md](README.md). For the integrative research agenda, continue to [BM-008](docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md).

## 9. Research and Attribution

**Authors:** Sizhe Tan & GPT-Obot.  
**License:** Apache-2.0.  
**Citation:** Refer to `CITATION.cff` when available; use the repository release and its assigned DOI once published. No DOI is asserted before assignment.

**Guiding principle:** *Beyond matching is not beyond evidence. Unverified signals may guide inquiry, but must not acquire unquestionable authority.*
