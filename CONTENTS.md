# CONTENTS — Beyond Matching and OTHERS Intelligence

**Full title:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** v1.0.0 — Research Foundation  
**License:** Apache-2.0  
**Status:** Conceptual and algorithmic research proposals; empirical performance claims require validation.

> **Research question:** How can intelligence evaluate consequential signals that cannot yet be formally matched, while preserving evidence quality, perspective boundaries, and accountable choice?

## 1. Quick Navigation

| Entry | Purpose |
|---|---|
| [README.md](README.md) | Project vision, core contributions, architecture, and research positioning |
| [START-HERE.md](START-HERE.md) | Guided reading paths for new readers, algorithm designers, and social-science researchers |
| **CONTENTS.md** | Canonical map of papers, figures, concepts, and release resources |
| [GLOSSARY.md](GLOSSARY.md) | Shared terminology and definitions |
| [FIGURE-INDEX.md](FIGURE-INDEX.md) | Figure descriptions and placement guide |
| [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md) | Open questions and next-phase research |

## 2. Research Papers — Canonical Reading Order

All eight papers belong in the `docs/` directory.

### Part I — Problem and Evidence Space

**[BM-001 — Beyond Matching and the Limits of Distance Scoring](docs/BM-001-Beyond-Matching-and-the-Limits-of-Distance-Scoring.md)**  
Distinguishes similarity, mathematical metric distance, perspective distance, and action scoring. Explains why `distance = 1 - similarity` does not automatically provide a metric or an adequate decision model. Frames cross-domain scoring as a research problem rather than a presumed universal failure of AI.

**[BM-002 — OTHERS as an Open Evidence Space](docs/BM-002-OTHERS-as-an-Open-Evidence-Space.md)**  
Defines OTHERS as the revisable space of contextual, relational, reputational, prospective, subjective/competitive, and anomalous signals not adequately captured by existing matching features. Introduces provenance-aware evidence interfaces and the boundary between evidence and preference.

### Part II — Scoring Mechanisms and Collective Signals

**[BM-003 — Directional Measurement Sails and Weak-Evidence Scoring](docs/BM-003-Directional-Measurement-Sails-and-Weak-Evidence-Scoring.md)**  
Develops the Directional Measurement Sails (DMS) hypothesis: heterogeneous signals may affect distinct evaluation directions through learnable response functions. Discusses weighting, reliability, dependence, uncertainty, and the possibility of discovering new sails.

**[BM-004 — Reputational Intelligence and Collective Weak Signals](docs/BM-004-Reputational-Intelligence-and-Collective-Weak-Signals.md)**  
Examines social reputation, indirect observations, weak signals, source independence, and collective learning. Distinguishes useful collective information from repetition, information cascades, coordinated manipulation, and unverified claims.

### Part III — Situated Decision and Structural Growth

**[BM-005 — Perspective Distance and Competitive Action Scoring](docs/BM-005-Perspective-Distance-and-Competitive-Action-Scoring.md)**  
Separates evidence scoring from perspective-dependent interpretation and utility-based action. Treats asymmetric risks, goals, competition, authorization, and the interface with Subjective Structural Intelligence (SSI).

**[BM-006 — From OTHERS to Open Structural Scoring Growth](docs/BM-006-From-OTHERS-to-Open-Structural-Scoring-Growth.md)**  
Proposes Open Structural Scoring Growth (OSSG): **Capture → Sense → Propose → Challenge → Promote → Reassess**. Explores how independently validated weak signals may become explicit features, metrics, Cross-Domain Concepts (CCC), or principles, while unresolved OTHERS remain open to revision.

### Part IV — Governance, Synthesis, and Validation

**[BM-007 — Counter-Evidence, Provenance, and Scoring Governance](docs/BM-007-Counter-Evidence-Provenance-and-Scoring-Governance.md)**  
Specifies evidence provenance, counter-evidence records, scoring auditability, independence checks, promotion gates, policy boundaries, and rollback. Addresses rumor amplification, Goodhart effects, and unauthorized transfer of decision authority.

**[BM-008 — Unified Architecture, Research Agenda, and Validation](docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md)**  
Integrates the full framework and proposes research hypotheses, baseline comparisons, ablations, robustness tests, calibration measures, and phased implementation. Locates the work relative to existing decision science, weak-signal analysis, reputation systems, and AI methods.

## 3. Figure Catalog

The figure plan uses **seven standalone PNG files** under `figures/`. The previously generated seven-panel composite must be split/exported before these individual links will resolve.

| Figure | File | Main role |
|---|---|---|
| Fig-001 | `figures/Fig-001-Beyond-Matching-Grand-Map.png` | Project-wide transition from formal matching to open structural scoring |
| Fig-002 | `figures/Fig-002-Matching-vs-Perspective-Distance.png` | Distinguishing feature-space distance from situated interpretation |
| Fig-003 | `figures/Fig-003-Directional-Measurement-Sails.png` | Core directional weak-evidence scoring concept |
| Fig-004 | `figures/Fig-004-Reputational-Collective-Signals.png` | Collective sources, propagation, and reputational dimensions |
| Fig-005 | `figures/Fig-005-OTHERS-Structural-Growth-Loop.png` | Six-stage evidence-to-structure lifecycle |
| Fig-006 | `figures/Fig-006-Evidence-Perspective-Decision-Planes.png` | Separation of belief, interpretation, and action |
| Fig-007 | `figures/Fig-007-Unified-Open-Scoring-Architecture.png` | Unified architecture and SI/SSI ecosystem interfaces |

Suggested primary placements: Fig-001 in BM-002; Fig-002 in BM-001; Fig-003 in BM-003; Fig-004 in BM-004; Fig-005 in BM-006; Fig-006 in BM-005 and/or BM-007; Fig-007 in BM-008. Refer to the future `FIGURE-INDEX.md` for precise insertion instructions.

## 4. Concept and Interface Map

| Concept | Main paper(s) | Key distinction |
|---|---|---|
| Matching / similarity | BM-001 | Representation-dependent resemblance, not universal relevance |
| Metric vs. perspective distance | BM-001, BM-005 | Mathematical distance axioms vs. contextual, possibly asymmetric assessments |
| OTHERS / Open Evidence Space | BM-002 | Unmodeled evidence, not automatically credible evidence |
| Directional Measurement Sails (DMS) | BM-003 | Direction-specific responses, not a proven general-purpose sensor |
| Reputational / collective weak signals | BM-004 | Source-aware indirect evidence, not consensus-as-truth |
| Evidence–Perspective–Decision planes | BM-005, BM-007 | Facts, interpretations, and authorized choices remain distinguishable |
| Open Structural Scoring Growth (OSSG) | BM-006 | Evidence can inspire candidates; promotion requires validation |
| Counter-evidence and provenance | BM-007 | Auditable correction and independent-source controls |
| Unified validation program | BM-008 | Testable hypotheses rather than presumed performance advantages |

## 5. Suggested Reading Paths

**Fast orientation (15–20 minutes):** README → START-HERE → BM-001 introduction → BM-008 overview.

**Algorithms and structural intelligence:** BM-002 → BM-003 → BM-006 → BM-007 → BM-008.

**Social science and reputation:** BM-004 → BM-002 → BM-003 → BM-007 → BM-008.

**Perspective, competition, and SSI:** BM-001 → BM-005 → BM-007 → BM-008.

**Validation and engineering planning:** BM-003 → BM-006 → BM-007 → BM-008.

## 6. Research Boundaries

This repository proposes a **unified open-scoring architecture**, not the invention of multi-criteria decision-making, reputation systems, weak-signal management, or preference learning. It does not assume that human cross-domain judgments are universally superior to AI, or that reputation is reliable merely because it is widespread. Directional sails and structural promotion remain hypotheses to be compared with established baselines.

The framework connects to the broader Structural Intelligence (SI) program, including Metric Differential Trees (MDT), Cross-Domain Concepts (CCC), Principle Intelligence, PIRP/PIRU, Collective Structural Learning, and SSI. These are proposed interfaces, not claims of demonstrated runtime interoperability.

## 7. Repository and Release Resources

| Resource | Role |
|---|---|
| `CHANGELOG.md` | Version history |
| `CITATION.cff` | Citation metadata |
| `.zenodo.json` | Zenodo deposition metadata |
| `LICENSE.txt` | Apache License 2.0 |
| `release/GitHub-Release-Notes-v1.0.0.md` | GitHub release narrative |
| `release/ResearchGate-Description.txt` | Short ResearchGate description |
| `release/BM-ODWEI-v1.0.0-ResearchGate-Overview.pdf` | One-page ResearchGate overview |

## 8. Version Roadmap

- **v1.0.0 — Foundation:** eight research papers, seven figures, conceptual architecture, and validation agenda.
- **v1.1.0 — Controlled validation:** reproducible datasets, baseline comparisons, ablations, calibration, robustness, and error analysis.
- **v2.0.0 — Structural integration:** adaptive sails, validated structural promotion, cross-node learning, and governed runtime interfaces.

---

**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0  
**Citation:** Use `CITATION.cff` once prepared. Add the permanent DOI only after it is officially assigned.

**Guiding principle:** *Beyond matching is not beyond evidence. Weak signals may guide inquiry, but only validated evidence should acquire structural authority.*
