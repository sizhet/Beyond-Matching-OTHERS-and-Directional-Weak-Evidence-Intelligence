# Figure Index — Metric-Directional Intuition (MDI) Research Extension

**Parent project:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Extension:** Metric-Directional Intuition (MDI)  
**Scope:** MDI-001–MDI-006  
**Status:** Research-extension figure guide; not an empirical validation report  
**Figure numbering:** Continues the parent repository's Fig-001–Fig-007 as Fig-008–Fig-011.

## 1. Purpose and scope

This index documents the four proposed extension figures, their scientific interpretations, the papers in which they should appear, and the limits of what each illustration establishes. The MDI figures supplement rather than replace the seven figures of the original BM-ODWEI v1.0.0 release. In particular, an architecture diagram is a research proposal, not evidence that a biological or computational system implements that architecture.

**Asset status:** The four illustrations were initially generated together in a single four-panel composite. The individual filenames below are the **intended repository assets**. Export and inspect each panel separately before committing Markdown image links. Do not assume the individual PNG files already exist merely because they appear in this index.

## 2. Master figure catalog

| ID | Repository filename (relative to this extension) | Short title | Primary paper | Supporting papers |
|---|---|---|---|---|
| Fig-008 | `figures/Fig-008-Directional-Intuition-Grand-Map.png` | Directional Intuition — Grand Map | MDI-001 | MDI-003, MDI-004, MDI-006 |
| Fig-009 | `figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png` | Euclidean vs. Metric-Native Directional Scoring | MDI-002 | MDI-001, MDI-004 |
| Fig-010 | `figures/Fig-010-Perspective-Fields-and-Forward-Guidance.png` | Perspective Fields and Pre-Decisional Guidance | MDI-003 | MDI-002, MDI-005 |
| Fig-011 | `figures/Fig-011-Hypothesis-Reputation-Relay-Loop.png` | Hypothesis–Reputation–Relay Loop | MDI-005 | MDI-006, MDI-004 |

## 3. Fig-008 — Directional Intuition: Grand Map

**File:** `figures/Fig-008-Directional-Intuition-Grand-Map.png`  
**Primary placement:** `docs/MDI-001-Problem-Definition-and-Research-Boundaries.md`, immediately after its first integrated problem formulation or architecture overview, before detailed mathematical definitions.  
**Secondary reference:** MDI-006's synthesis of validation, relay, and structural growth.

**Suggested caption:**

> **Figure 008. Directional Intuition — Grand Map.** Conceptual integration of matching evidence, the OTHERS open-evidence space, perspective-conditioned directional scoring, pre-decisional guidance, hypothesis testing, reputational evaluation, MET integration, and evidence-driven structural growth. Arrows indicate proposed information and control relationships rather than proven causal or neural mechanisms.

**Interpretation:** The figure places matching and OTHERS alongside complementary directional evaluation routes. It distinguishes guidance and candidate generation from subsequent evaluation and action. Evidence can return through relay and validation, allowing new features to be considered for promotion into the matching baseline.

**Boundary:** The boxes are conceptual modules; the figure does not imply a required runtime sequence or a claim that all modules must always be active.

## 4. Fig-009 — Euclidean vs. Metric-Native Directional Scoring

**File:** `figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png`  
**Primary placement:** `docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md`, after both scoring routes have been defined and before their comparison and mathematical properties.  
**Secondary reference:** MDI-001's representation-independent research boundary.

**Suggested caption:**

> **Figure 009. Euclidean vs. Metric-Native Directional Scoring.** The Euclidean route evaluates alignment through normalized vector projections; the metric-native route evaluates progress toward a goal set using changes in a distance-to-goal potential. The latter does not require a Euclidean embedding, provided the metric and goal set satisfy the stated assumptions.

**Canonical mathematical reading:** For nonzero Euclidean vectors, a directional cosine is

$$
C_{\mathrm E}(v,p)=\frac{\langle v,p\rangle}{\|v\|\,\|p\|}\in[-1,1].
$$

For a metric space \((\mathcal X,d)\), a nonempty goal set \(G\), and distinct points \(x,y\), let \(V_G(x)=\inf_{g\in G}d(x,g)\). Then

$$
C_{\mathrm M}(x,y\mid G)=\frac{V_G(x)-V_G(y)}{d(x,y)}\in[-1,1].
$$

The metric-native bound follows from the 1-Lipschitz property of distance to a nonempty set. If \(x=y\), the quotient is undefined and requires an explicit implementation policy. A positive value indicates movement toward the goal set in this potential-based sense.

**Critical artwork check:** Mathematical labels in generated diagrams must be checked against the canonical formulas above. In particular, do **not** interpret a denominator containing a sum of distances or an added smoothing constant as the canonical metric-native formula unless the modified operator is separately defined and its properties proved. The initial composite may contain such illustrative notation; correct it before scientific publication. Similarly, cosine normalization requires nonzero vectors.

**Boundary:** Goal-distance progress is one metric-native directional construction, not a unique or universal definition of directional intelligence. A general learned pairwise directional relation may be non-potential-based.

## 5. Fig-010 — Perspective Fields and Pre-Decisional Guidance

**File:** `figures/Fig-010-Perspective-Fields-and-Forward-Guidance.png`  
**Primary placement:** `docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md`, following the discussion of guidance preceding explicit candidate evaluation.  
**Secondary reference:** MDI-005's limited-budget hypothesis and evidence selection.

**Suggested caption:**

> **Figure 010. Perspective Fields and Pre-Decisional Guidance.** Schematic perspective-conditioned landscape with multiple exploration trails. Directional information can prioritize attention and candidate generation before explicit evaluation, subject to task, risk, and governance constraints. The landscape is illustrative and does not require a Euclidean state representation.

**Interpretation:** The diagram's field arrows and exploration paths illustrate a possible **Guide → Generate → Evaluate → Select/Act** pipeline. Different perspectives can change which regions are explored and which hypotheses are tested, not merely reorder an already fixed candidate set.

**Boundary:** The illustrated surface is a visualization metaphor. Metric-native or relational guidance need not be representable as a smooth scalar field, and no neural implementation is inferred from the picture.

## 6. Fig-011 — Hypothesis–Reputation–Relay Loop

**File:** `figures/Fig-011-Hypothesis-Reputation-Relay-Loop.png`  
**Primary placement:** `docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md`, after the hypothesis-testing and reputation-update loop has been introduced.  
**Secondary placement:** `docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md`, where relay, independent validation, and feature promotion are integrated.

**Suggested caption:**

> **Figure 011. Hypothesis–Reputation–Relay Loop.** A proposed low-budget cycle in which directional hypotheses guide targeted evidence gathering, evaluation updates context-specific reliability, and provenance-preserving relay supports further testing. Promotion of OTHERS evidence into established matching features requires independent validation and governance rather than mere repetition.

**Interpretation:** Hypotheses compete for limited test budgets; evidence may support, refute, or leave them unresolved. Reputation tracks a defined and calibrated reliability target. Relay transports hypotheses, observations, counter-evidence, and provenance. Structural growth is conditional on validated evidence.

**Boundary:** Repeated observations can be useful relay data without constituting independent confirmation. A reputation score is not automatically the probability that a hypothesis is true, and neither quantity is interchangeable with expected action value.

## 7. Recommended insertion and citation convention

Once the individual images have been exported and verified, use a relative link from each paper in `docs/` to the sibling `figures/` directory. For example, inside MDI-002:

```markdown
![Figure 009 — Euclidean versus metric-native directional scoring](figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png)

*Figure 009. Euclidean vs. Metric-Native Directional Scoring. See the figure index for assumptions and interpretation.*
```

For a link **from this index** (located at the extension root), use `figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png` without `../`. Do not insert image links until the files exist under those exact names.

**One primary placement per figure** is recommended. Other papers may link to the primary figure rather than duplicating the full-size image. This avoids repetitive diagrams and inconsistent captions.

## 8. Publication quality-control checklist

- [ ] Export four distinct PNGs from the composite, at sufficient resolution for full-size reading.
- [ ] Verify exact spelling and capitalization of all four filenames.
- [ ] Inspect cropped edges, title bars, arrow directions, and text legibility.
- [ ] Audit all formulas in Fig-009 against MDI-002; correct any illustrative but noncanonical denominator or missing domain condition.
- [ ] Confirm that Fig-010's potential landscape is identified as schematic, not a universal metric-space representation.
- [ ] Confirm that Fig-011 does not conflate repeated relay observations with independent validation.
- [ ] Insert primary figures at the designated sections of MDI-001, MDI-002, MDI-003, and MDI-005.
- [ ] Check that relative image links resolve from the `docs/` directory.
- [ ] Confirm numbering does not collide with the parent project's Fig-001–Fig-007.
- [ ] Update the parent repository's `FIGURE-INDEX.md` only with a short pointer to this extension index, if desired.

## 9. Relationship to the parent BM-ODWEI figures

The original Fig-001–Fig-007 remain unchanged. Fig-008–Fig-011 deepen the mathematical and operational interpretation of OTHERS, directional measurement sails, reputation, and structural growth. They do not retroactively change the claims or figure numbering of the original BM-ODWEI v1.0.0 materials.

## 10. Suggested cross-reference

From the parent `FIGURE-INDEX.md`, an optional single-line addition is sufficient:

> **MDI research-extension figures (Fig-008–Fig-011):** See [`../../extensions/metric-directional-intuition/FIGURE-INDEX.md`](../../extensions/metric-directional-intuition/MDI-Extension-FIGURE-INDEX.md) for captions, paper placement, mathematical cautions, and validation boundaries.

---

*This figure index is part of the MDI research extension. Its diagrams communicate research designs and hypotheses; formal definitions and proof obligations remain in MDI-001–MDI-006.*
