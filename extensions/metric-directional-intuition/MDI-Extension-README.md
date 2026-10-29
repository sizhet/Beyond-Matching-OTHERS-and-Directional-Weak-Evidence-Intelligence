# Metric-Directional Intuition (MDI)

**A research extension of Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence (BM-ODWEI)**

**Status:** Theory-first research extension; candidate operators and validation proposals, not a validated biological model or production MET implementation.  
**Repository:** [Beyond-Matching-OTHERS-and-Directional-Weak-Evidence-Intelligence](https://github.com/sizhet/Beyond-Matching-OTHERS-and-Directional-Weak-Evidence-Intelligence)  
**Location:** `extensions/metric-directional-intuition/`  
**Version context:** Proposed for a subsequent BM-ODWEI release; the extension does not alter the historical v1.0.0 research record.

## 1. Why This Extension Exists

Conventional matching-based similarity can overlook weak, contextual, directional, and as-yet-unmodeled evidence. The parent BM-ODWEI research program calls this open evidence space **OTHERS** and studies directional measurement sails, perspective distance, reputation, counter-evidence, and structural scoring growth.

MDI develops one focused question:

> How can a structural intelligence system assess whether an observed or candidate structure is directionally promising relative to a perspective, even when ordinary feature matching is incomplete—and how can it do so with bounded scores, explicit evidence provenance, low-cost hypothesis tests, and falsifiable validation?

The extension connects **intuitive similarity**, **directional guidance**, **metric-native scoring**, **reputational evidence**, and **structural relay**. It treats the proposed connection to animal intuition as a research hypothesis, not as an established account of neural computation.

## 2. Research Contributions and Boundaries

MDI distinguishes five concepts that must not be collapsed:

1. **Matching similarity:** agreement among features already represented and evaluated by a baseline matcher.
2. **Directional utility:** whether a candidate transition advances a particular perspective or goal.
3. **Directional agreement:** whether two structures or transitions exhibit similar directional properties; this is not identical to utility.
4. **Reputational reliability:** confidence in a hypothesis, evidence source, or operator in a specified context, supported by provenance and counter-evidence.
5. **Distance score versus mathematical metric:** a bounded score such as `1 - similarity` does not automatically satisfy metric axioms.

A Euclidean cosine sail is one candidate implementation, not a prerequisite for directional intelligence. MDI also studies directional differences derived directly from a metric and more general structural transition relations. A metric alone does **not** determine a goal or preference; perspective information must be supplied separately.

### 2.1 Two illustrative operator families

**Euclidean directional alignment**, for nonzero vectors `v` and `p`:

$$
C_{P}^{\mathrm{Euc}}(v,p)=\frac{\langle v,p\rangle}{\|v\|\,\|p\|}\in[-1,1].
$$

**Metric-native goal-directed transition**, for a metric space `(X,d)`, a nonempty goal set `G`, `x ≠ y`, and `V_G(z)=d(z,G)`:

$$
C_{P}^{\mathrm{metric}}(x,y;G)=\frac{V_G(x)-V_G(y)}{d(x,y)}\in[-1,1].
$$

The bound follows from the reverse triangle inequality for distance-to-set. This operator measures goal-directed progress along a transition; it does **not** by itself measure pairwise structural similarity. Zero-length transitions require an explicit policy. In contexts where a potential is not appropriate, learned pairwise directional relations may be explored, with their own consistency and calibration requirements.

## 3. Research Architecture

```text
World / Context / Perspective / Constraints
                    |
                    v
        Representation + Baseline Matching
                    |
                    +----> OTHERS residual evidence
                    |               |
                    |               v
                    |      Directional operator family
                    |      (Euclidean / Metric-native /
                    |       structural relation)
                    |               |
                    v               v
            Pre-decisional guidance
       (attention, hypotheses, candidate trails)
                    |
                    v
      Evidence tests + contextual reputation
                    |
                    v
     Governed scoring / uncertainty / fallback
                    |
                    v
            Decision or observation
                    |
                    v
    Provenance-preserving evidence relay
                    |
                    v
   Validation -> feature promotion or rejection
                    |
                    +------> Updated matching / OTHERS
```

The architecture separates **candidate discovery** from **candidate evaluation**. It also separates **repeated observations** from **independent validation**: repeated execution can accumulate evidence and constitute relay without necessarily increasing independent evidential support.

## 4. Reading Guide: Six Research Papers

Read sequentially for the complete argument, or select a paper by concern:

| Paper | Focus | Primary question |
| --- | --- | --- |
| [MDI-001 — Problem Definition and Research Boundaries](docs/MDI-001-Problem-Definition-and-Research-Boundaries.md) | Definitions, scope, assumptions, epistemic limits | What is being scored, and what is not claimed? |
| [MDI-002 — Euclidean and Metric-Native Directional Scoring](docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md) | Operators, bounds, local relations, edge cases | How can directionality be scored without requiring Euclidean embedding? |
| [MDI-003 — Perspective Fields and Pre-Decisional Guidance](docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md) | Fields, multi-perspective guidance, candidate generation | How can directionality guide what is considered before selection? |
| [MDI-004 — OTHERS Residual Scoring and MET Integration](docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md) | Evidence allocation, score fusion, baseline preservation | How can weak directional evidence be added without double counting? |
| [MDI-005 — Lightweight Hypothesis Testing and Reputation](docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md) | Bounded hypothesis portfolios, tests, evidence reliability | Which few hypotheses are worth testing under limited compute? |
| [MDI-006 — Evidence Relay, Validation, and Structural Growth](docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md) | Provenance, conformance, experiments, feature promotion | How can candidate intuition become validated and reusable intelligence? |

**Suggested paths:** Mathematics: 001 → 002 → 004 → 006. Forward guidance: 001 → 003 → 005 → 006. MET engineering: 002 → 004 → 006. Evidence governance: 004 → 005 → 006.

## 5. Figures

The extension's figure identifiers and insertion points are:

| Figure | Planned filename | Primary paper |
| --- | --- | --- |
| Fig-008 | `figures/Fig-008-Directional-Intuition-Grand-Map.png` | MDI-001 |
| Fig-009 | `figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png` | MDI-002 |
| Fig-010 | `figures/Fig-010-Perspective-Fields-and-Forward-Guidance.png` | MDI-003 |
| Fig-011 | `figures/Fig-011-Hypothesis-Reputation-Relay-Loop.png` | MDI-005 / MDI-006 |

**Asset note:** The initial artwork was produced as a four-panel composite. The four individual PNG paths above are **target filenames**; verify that separate, legible images have been exported before inserting Markdown image links or claiming those files exist in the repository. Figure numbering continues the parent repository's Fig-001–007 series.

## 6. Key Engineering Contracts

MDI is specification-oriented. A candidate directional module should expose, at minimum:

- **Inputs:** source/candidate structures or transitions, perspective/goal, metric or structural relation, context, evidence references, and constraints.
- **Outputs:** explicitly typed directional score, confidence/calibration metadata where available, provenance, applicable scope, counter-evidence references, and abstention/fallback status.
- **Semantics:** distinguish progress, agreement, and similarity; specify normalization, zero-denominator handling, and direction reversal behavior.
- **Evidence governance:** attribute evidence to matching or residual channels to prevent duplicate counting; retain source and dependence information.
- **Fallback:** preserve the baseline matching result when the directional contribution is unavailable or insufficiently justified.
- **Conformance:** test mathematical bounds, missing-data behavior, robustness, provenance integrity, and operator-specific assumptions before runtime adoption.

A directional contribution should not be interpreted as a calibrated probability unless calibration has been independently established. Similarly, multiplying a score by a reputation estimate is a heuristic unless justified by an explicit probabilistic model.

## 7. Validation Strategy

The proposed comparison set includes baseline matching, Euclidean directional scoring, metric-native scoring, hypothesis-guided scoring, and governed residual fusion. Studies should report:

- Task-specific decision quality and ranking metrics, not only score magnitude.
- Calibration and selective abstention under weak or missing evidence.
- Compute, memory, test cost, and sample efficiency.
- Robustness to perspective shifts, metric changes, distribution shift, and adversarial or misleading signals.
- Evidence leakage, double counting, correlated sources, and false reputation accumulation.
- Structural-growth outcomes: candidate-feature acceptance, rejection, rollback, and downstream utility.

Use randomized-perspective and shuffled-evidence controls where appropriate. A positive directional score is not itself evidence that a system has learned an animal-like intuitive mechanism.

## 8. Relationship to the Parent Repository and Related SI Research

This directory is **additive**. The parent repository's `docs/BM-001` through `BM-008` remain the canonical exposition of the broader Beyond Matching / OTHERS framework. MDI narrows the focus to directional operators, metric-native formulation, low-cost hypothesis testing, and validation-oriented integration.

Conceptual interfaces are proposed with **MET** (metric/distance evaluation), **UCPSF** (scoring/control-plane governance), **SIF** (structural growth and conformance), **UIERU** (forward guidance and relay), and **BUI-DSI** (dynamic structural intelligence). These are research connections, not claims of implemented cross-repository compatibility.

## 9. Companion Files and Publication Policy

- `MDI-Extension-CONTENTS.md` — detailed paper and section map.
- `MDI-Extension-GLOSSARY.md` — scoped MDI terminology and symbol conventions.
- `MDI-Extension-FIGURE-INDEX.md` — figure descriptions and insertion guidance.
- `MDI-Extension-OPEN-QUESTIONS.md` — unresolved mathematical, engineering, and cognitive questions.
- `MDI-Extension-TESTABLE-HYPOTHESES.md` — falsifiable hypotheses and control conditions.
- `MDI-Extension-VALIDATION-ROADMAP.md` — staged experiments, acceptance criteria, and failure reporting.

These companion files should be added as they are completed; their mention here does not imply they have already been committed. The extension is **theory-first** and does not require demonstration code for its initial research release.

Release notes and metadata remain at the parent repository level. Historical v1.0.0 release assets should not be overwritten. Any subsequent release version and DOI metadata must reflect the actual publication state and Zenodo configuration.

## 10. Citation, License, and Research Integrity

For formal citation, use the parent repository's `CITATION.cff` and the DOI of the **specific archived version**, once available. Do not assign a DOI to this extension before it has been archived. Consult the parent repository's `LICENSE.txt` for the governing license; the extension does not introduce a separate license.

Mathematical propositions, proposed engineering mechanisms, experimental hypotheses, and biological analogies are deliberately distinguished. Negative results, counterexamples, and rejected hypotheses are expected research outputs and should remain traceable through the evidence relay record.

---

**Research thesis:** Directional intuition can be investigated as a perspective-conditioned, evidence-governed process that guides which possibilities to examine, tests a small number of consequential hypotheses, and promotes weak evidence into reusable structural intelligence only after validation.
