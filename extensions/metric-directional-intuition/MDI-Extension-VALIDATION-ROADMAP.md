# VALIDATION ROADMAP — Metric-Directional Intuition (MDI)

**Research extension:** Metric-Directional Intuition (MDI)  
**Parent project:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Proposed extension release:** BM-ODWEI v1.1.0  
**Document status:** Research planning specification; no experimental results are claimed  
**Scope:** MDI-001 through MDI-006  

> **Central validation rule:** A mathematical property, a software conformance result, an empirical performance gain, and a claim about biological cognition are four different kinds of evidence. None automatically establishes the others.

## 1. Purpose

This roadmap converts the six MDI research papers and the companion [MDI-Extension-TESTABLE-HYPOTHESES.md](MDI-Extension-TESTABLE-HYPOTHESES.md) into an ordered, reproducible program of mathematical verification, contract conformance, controlled experimentation, evidence relay, and structural-growth evaluation. It is designed for independent researchers who may implement different representations and scoring operators while retaining comparable experimental claims.

MDI is an **optional research extension** of BM-ODWEI. Its validation must not require modification of the original BM-001–BM-008 theoretical texts or their historical v1.0.0 release. The first deliverable is a set of explicit contracts and falsifiable tests, not a demonstration that any particular animal brain implements these algorithms.

### 1.1 Research objectives

1. Establish which proposed directional scores are mathematically well-defined and under which assumptions.
2. Determine whether Perspective-conditioned scores improve task-relevant ranking beyond ordinary matching.
3. Test whether metric-native directionality has an advantage when Euclidean representation is inappropriate or distorting.
4. Separate improvements in **candidate discovery** from improvements in **candidate ranking**.
5. Verify that OTHERS evidence does not silently duplicate matching evidence or degrade the baseline when absent.
6. Test the decision value and compute efficiency of lightweight hypothesis testing and reputation-aware evidence selection.
7. Assess whether evidence can be relayed, independently checked, and promoted into reusable matching features without evidence laundering.
8. Delimit, rather than overstate, the biological interpretation of observed behavior.

## 2. Research assets and authoritative sources

| Asset | Primary responsibility |
|---|---|
| [MDI-001](docs/MDI-001-Problem-Definition-and-Research-Boundaries.md) | Definitions, problem boundaries, claim categories |
| [MDI-002](docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md) | Euclidean and metric-native mathematics |
| [MDI-003](docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md) | Perspective fields, pre-decisional guidance, candidate discovery |
| [MDI-004](docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md) | Evidence allocation, scoring composition, MET adapter and fallback |
| [MDI-005](docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md) | Small-budget hypotheses, value of information, contextual reputation |
| [MDI-006](docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md) | Provenance, relay, validation, OTHERS-to-feature promotion |
| [MDI-Extension-OPEN-QUESTIONS.md](MDI-Extension-OPEN-QUESTIONS.md) | Unresolved mathematical, engineering, and biomimetic questions |
| [MDI-Extension-TESTABLE-HYPOTHESES.md](MDI-Extension-TESTABLE-HYPOTHESES.md) | Canonical H-MDI-001–012 hypotheses and conformance matrix |
| [MDI-Extension-GLOSSARY.md](MDI-Extension-GLOSSARY.md) | Terminology and mathematical symbol discipline |

**Consistency policy:** Hypothesis identifiers are inherited from TESTABLE-HYPOTHESES.md; this roadmap does not create competing IDs. A change to a definition, hypothesis, or acceptance criterion requires an explicit change record and review of affected downstream experiments.

## 3. Evidence ladder and stage gates

The roadmap uses six gates. Each gate has **entry conditions, required outputs, exit criteria, and failure handling**. A stage may be repeated; passing a later stage never retroactively repairs an earlier unrecorded failure.

| Gate | Stage | Principal evidence | Minimum exit condition |
|---|---|---|---|
| G0 | Claim registry and preregistration | Versioned definitions and experimental plans | Every tested claim has a hypothesis ID, baseline, outcome, and failure criterion |
| G1 | Mathematical and contract verification | Proofs, counterexamples, property tests | Preconditions, bounds, degeneracies, and fallback semantics are explicit |
| G2 | Synthetic controlled benchmarks | Ground-truth tasks and ablations | Reproducible directional effects and negative controls are reported |
| G3 | Budgeted decision and MET integration | Candidate search, decision-cost, and adapter tests | Benefits are measured at matched budgets with no unreported baseline regression |
| G4 | Reputation, relay, and growth | Provenance audits, transfer tests, feature promotion | No independent-evidence inflation; promoted features survive held-out tests |
| G5 | External replication and bounded biomimetic inquiry | Independent implementations and behavioral comparisons | Results reproduce or limitations are documented without biological overclaim |

A **conditional pass** is permitted only if unresolved limitations are enumerated and downstream experiments are constrained accordingly. A failed gate produces a recorded negative result, not a silently revised success metric.

## 4. G0 — Definitions, datasets, and preregistration

### 4.1 Inputs

- Frozen definitions of the objects being compared: structural elements, matching features, OTHERS evidence, Perspective, metric or distance function, and target task.
- A declared distinction between **directional utility** (alignment with a goal) and **directional agreement** (similar orientation of two objects).
- A declared distinction between **normalized distance score** \(D_I=1-S_I\) and a mathematical metric satisfying symmetry and the triangle inequality.
- A declared scope for reliability: hypothesis validity, source quality, contextual transferability, and action risk must not be conflated.

### 4.2 Preregistered protocol

For each H-MDI hypothesis, record: task family; primary and secondary endpoints; baseline; variants; dataset generation and splits; Perspective specification; metric assumptions; budget unit; number of seeds; planned uncertainty intervals; exclusion rules; anticipated confounders; and falsification threshold. The threshold must be chosen before inspecting test-set outcomes.

Partition by **source, scenario, subject, or provenance family** where necessary; random row splits alone can leak repeated or derived evidence into both training and evaluation. Maintain a frozen evaluation set and a separate development set. Record random seeds and software/contract versions.

### 4.3 G0 exit artifacts

- `claim-registry` with stable hypothesis and operator IDs.
- `experiment-protocol` and dataset manifest.
- `metric-contract` including domain, missing-value policy, symmetry status, and any triangle-inequality assumption.
- `perspective-contract` with origin, scope, validity interval, and conflict rules.
- `evidence-schema` identifying provenance, overlap groups, counter-evidence, and permitted reuse.

**Exit rule:** All primary comparisons are operationally defined and independently implementable. If not, narrow the claim rather than inventing retrospective definitions.

## 5. G1 — Mathematical verification and conformance

### 5.1 Euclidean operator

For nonzero vectors \(v\) and \(p\), verify that \(\cos(v,p)=\langle v,p\rangle/(\|v\|\|p\|)\) lies in \([-1,1]\), and that \((1+\cos(v,p))/2\) lies in \([0,1]\). Define explicit behavior for zero vectors, empty element sets, missing Perspective, invalid weights, and numerical round-off. Multi-sail combinations retain bounds only when their weights are nonnegative and normalized, or when an equivalent bounded aggregator is used.

### 5.2 Metric-native operator

Let \((\mathcal X,d)\) be a metric space, let \(G_P\subseteq\mathcal X\) be nonempty, and assume \(d(x,G_P)=\inf_{g\in G_P}d(x,g)\) is finite at the evaluated points. Define \(V_P(x)=d(x,G_P)\). For \(x\ne y\),

$$
C_P(x,y)=\frac{V_P(x)-V_P(y)}{d(x,y)}.
$$

The distance-to-set function is 1-Lipschitz: \(|V_P(x)-V_P(y)|\le d(x,y)\). Consequently \(C_P(x,y)\in[-1,1]\). Test this property across discrete graphs, tree metrics, finite metric tables, and continuous examples. **Do not** evaluate the expression at \(x=y\) without a separately specified convention. A general dissimilarity that violates metric axioms does not inherit this proof.

Verify the local Euclidean gradient interpretation only when the necessary differentiability and nonzero-displacement assumptions hold. A metric alone supplies no goal or preference: \(G_P\) or an equivalent directional relation is additional structure.

### 5.3 Score composition and invariants

Test three separately specified operators: convex mixture, bounded additive residual correction, and log-odds correction. Verify range, missing-evidence handling, weight validity, and interpretation of positive and negative contributions. The complement \(1-S_I\) must be labeled a **distance score**, not a metric without a separate proof.

### 5.4 Conformance suites

Implement the canonical conformance checks in TESTABLE-HYPOTHESES.md, including: bounds, degeneracy handling, Perspective provenance, matching/OTHERS overlap, evidence ledger completeness, fallback identity, counter-evidence visibility, correlated-evidence handling, relay provenance, and feature-promotion rollback. Add adversarial cases with contradictory Perspectives, malicious sources, duplicate observations, and metric-contract violations.

**Exit rule:** Proof obligations are discharged or explicitly limited, and all mandatory contract tests pass for the declared implementation profile. Unproved biological claims do not count as mathematical obligations.

## 6. G2 — Controlled synthetic benchmarks

### 6.1 Benchmark families

| Family | Controlled variable | What it isolates |
|---|---|---|
| B1: vector alignment | Perspective angle and element orientation | Cosine contribution and Perspective sensitivity |
| B2: discrete graph navigation | Goal set and shortest-path metric | Metric-native progress without Euclidean embedding |
| B3: tree or hierarchical metric | Branching and depth | Structural rather than coordinate-native directionality |
| B4: distorted embedding | Embedding dimension and distortion | Conditions under which metric-native scoring helps |
| B5: weak-evidence overlap | Matching coverage and OTHERS redundancy | Double counting and residual allocation |
| B6: conflicting Perspectives | Goal conflict, risk and priority | Multi-Perspective governance |
| B7: sparse/noisy evidence | Signal prevalence and source quality | Hypothesis testing and reputation sensitivity |

Generate task labels independently of the algorithm being evaluated wherever feasible. If labels are constructed directly from the candidate score, mark the experiment as an **operator sanity check**, not evidence of external utility.

### 6.2 Comparison arms

- **A0 — Matching-only baseline:** existing score with no directional extension.
- **A1 — Euclidean single sail:** fixed vector Perspective.
- **A2 — Euclidean multi-sail or field:** controlled additional directional capacity.
- **A3 — Metric-native potential:** distance-to-goal progress.
- **A4 — Learned structural directional relation:** pairwise relation with explicit training and provenance.
- **A5 — OTHERS-residual composition:** evidence coverage and duplicate controls.
- **A6 — Random or shuffled Perspective:** negative control.
- **A7 — Noisy, stale, or adversarial Perspective:** robustness control.

Not every arm is meaningful on every benchmark. Declare exclusions before evaluation. Equalize training information, model capacity, and query or compute budget when comparing mechanisms; otherwise identify the comparison as a system-level rather than operator-level result.

### 6.3 Primary measures

Ranking: task utility, pairwise preference accuracy, NDCG or recall@k where appropriate, and calibration. Structural sensitivity: controlled response to Perspective changes. Robustness: worst-group performance, OOD degradation, adversarial regret, and baseline regression. Cost: wall-clock time, scoring operations, model calls, memory, and energy when measurable.

**Exit rule:** At least one fully reproducible benchmark per mathematical route and explicit reporting of failed or neutral results. No broad superiority claim follows from a single favorable synthetic setting.

## 7. G3 — Forward guidance, MET adapters, and budgeted decisions

### 7.1 Separate discovery from ranking

For H-MDI-003, evaluate candidate **generation** independently from candidate **selection**. Record candidate coverage/recall before scoring, quality of the best discovered candidate, final selected utility, and end-to-end cost. A system that improves ranking among a fixed candidate set has not demonstrated better discovery.

Compare unguided search, random guidance, Euclidean guidance, metric-native guidance, and a matched-compute stronger-search baseline. Evaluate both useful and misleading Perspective conditions.

### 7.2 MET integration profile

Define an optional adapter with conceptual inputs `(A, B, Perspective, metric contract, matching evidence, OTHERS evidence, governance policy)` and outputs `(score, confidence metadata, attribution ledger, provenance, fallback status)`. This is a **research interface**, not a claim about an existing production MET API.

Required integration checks:

1. Missing, invalid, or untrusted directional evidence can trigger a documented baseline return.
2. If fallback is specified as exact identity, the returned score equals the baseline within a declared numerical tolerance.
3. No Matching evidence is silently counted again through OTHERS.
4. Negative evidence and conflict states remain visible in the ledger.
5. A bounded score remains bounded under all supported compositions.
6. Policy constraints cannot be bypassed by a high directional score.

### 7.3 Lightweight hypothesis-testing profile

For H-MDI-006, give all variants the same decision-time budget. Compare exhaustive search where feasible, fixed heuristics, random tests, information-gain selection, and **expected decision value of information**. Measure expected realized utility, regret, number of tests, latency, and value per cost. The EVSI/VOI estimate must include possible adverse observations and test costs; do not simply multiply directional score by an alleged truth probability.

**Exit rule:** A reproducible adapter-conformance report and at least one budget-matched decision experiment. Any claim of compute efficiency must state the accounting boundary.

## 8. G4 — Reputation, relay, and structural growth

### 8.1 Reputation and counter-evidence

Test H-MDI-007 and H-MDI-008 with heterogeneous source reliability, correlated reports, context shift, source drift, and adversarial sources. A Beta–Bernoulli update may serve as a simple baseline when its event and independence assumptions are satisfied; otherwise evaluate dependence-aware or hierarchical alternatives.

Report reliability calibration (e.g., Brier score, ECE with declared binning), decision utility, false-confidence rates, detection delay after source degradation, and recovery following counter-evidence. Track reputation at its declared target—source, hypothesis, context, or operator—not as an interchangeable universal scalar.

### 8.2 Relay independence

Test H-MDI-009 by sending evidence packages across agents or execution contexts. Each package should include stable claim ID, source lineage, observation IDs, Perspective, metric and operator versions, confidence semantics, contradictory evidence, and usage restrictions.

Compare: no relay; raw evidence relay; provenance-aware relay; and provenance-stripped relay. Repeated execution may yield additional data, but **retransmission of the same observation is not independent corroboration**. Explicitly model shared ancestors and derivative observations.

### 8.3 OTHERS-to-feature promotion

For H-MDI-010, define a candidate feature lifecycle:

`Observed OTHERS signal → candidate hypothesis → scoped validation → independent replication → proposed feature → conformance review → gated promotion → monitored operation / rollback`.

Promotion requires a predeclared benefit threshold on held-out tasks, overlap accounting, stability across contexts, a documented feature contract, and a rollback path. Compare the original Matching-only baseline, the temporary OTHERS correction, and the promoted Matching feature. Report maintenance cost and negative transfer as well as gains.

**Exit rule:** Provenance survives transfer, duplicate evidence does not inflate confidence, and at least one feature-promotion attempt is fully documented whether it succeeds or fails.

## 9. G5 — Replication and biomimetic limits

### 9.1 Independent replication

Ask an independent implementer to reconstruct at least the metric-native operator and one budgeted decision task from published contracts alone. Record ambiguities and divergences. Repeat with new datasets or scenarios not used in development. Replication failures must remain visible and may trigger revisions to the contract or claim scope.

### 9.2 Behavioral, not mechanistic, biomimicry

For H-MDI-012, compare model behavior with carefully defined animal or human behavioral phenomena only where suitable published data or ethically obtained observations exist. Candidate tasks include approach/avoidance, navigation under uncertainty, and selective inspection of ambiguous signals. Compare multiple non-MDI mechanisms as alternatives.

A behavioral fit does **not** establish that biological nervous systems encode Euclidean vector fields, metric potentials, Bayesian reputations, or SI units. Biological implementation requires separate neuroscientific evidence. Avoid anthropomorphic labels such as “the animal tests hypothesis H” unless clearly identified as a modeling interpretation.

**Exit rule:** At least one independent replication attempt, a documented alternative-model comparison, and a precise statement of what remains unproven.

## 10. Hypothesis-to-stage traceability matrix

| Hypothesis | Primary stage | Required principal comparison |
|---|---|---|
| H-MDI-001 Perspective specificity | G2 | Correct vs shuffled Perspective under matched ranking task |
| H-MDI-002 Metric-native advantage | G1–G2 | Native metric vs Euclidean embedding under controlled distortion |
| H-MDI-003 Pre-decisional discovery | G3 | Guided vs unguided candidate generation at matched budget |
| H-MDI-004 OTHERS attribution | G1–G3 | Overlap-aware vs naive combination with injected duplicate evidence |
| H-MDI-005 Baseline preservation | G1–G3 | Adapter with absent/invalid directional evidence vs exact baseline |
| H-MDI-006 Lightweight testing | G3 | VOI-guided vs heuristic/random tests at matched cost |
| H-MDI-007 Reputation robustness | G4 | Contextual reliability modeling vs unweighted or naive trust |
| H-MDI-008 Counter-evidence recovery | G4 | Explicit contradiction handling vs no update/hidden contradictions |
| H-MDI-009 Relay provenance | G4 | Provenance-aware vs provenance-stripped relay |
| H-MDI-010 Structural growth | G4 | Promoted feature vs baseline and temporary residual correction |
| H-MDI-011 Perspective conflict | G2–G3 | Governed vs ungoverned competing objectives |
| H-MDI-012 Biomimetic utility | G5 | MDI behavioral model vs plausible alternative models |

The table identifies **where** a claim is tested; the authoritative hypothesis wording, primary metrics, and falsification requirements remain in [MDI-Extension-TESTABLE-HYPOTHESES.md](MDI-Extension-TESTABLE-HYPOTHESES.md).

## 11. Statistical and experimental discipline

- **Primary endpoints:** One predeclared primary endpoint per confirmatory experiment; exploratory metrics are explicitly labeled.
- **Uncertainty:** Report confidence or credible intervals, effect sizes, and uncertainty over seeds, scenarios, and sources. Do not rely on point estimates alone.
- **Multiplicity:** Specify correction or hierarchical testing when many hypotheses or metrics are assessed confirmatorily.
- **Leakage:** Partition related evidence by provenance family; audit duplicated examples, synthetic generators, and embedding-training overlap.
- **Fair comparisons:** Match compute, available observations, search depth, and tuning opportunity when claiming algorithmic efficiency.
- **Negative controls:** Include random Perspective, irrelevant goal sets, reversed guidance, duplicate evidence, and stale source reputations as appropriate.
- **Ablations:** Remove Perspective, OTHERS, reliability, counter-evidence, and relay provenance independently to identify which component creates the effect.
- **Failure reporting:** Preserve failed seeds, unsafe trajectories, null results, and regression cases in the published artifact.
- **Reproducibility:** Publish configuration, dataset hashes or generation procedures, operator versions, hardware/runtime descriptions, and analysis scripts when available.

## 12. Risk register and stopping rules

| Risk | Warning sign | Required response |
|---|---|---|
| Score/metric confusion | Claims of metric axioms from \(1-S_I\) alone | Relabel as score or provide proof/counterexample |
| Circular ground truth | Labels generated by the tested score | Classify as sanity test; add external task labels |
| Perspective leakage | Perspective derived from test outcomes | Rebuild data split and preregister Perspective generation |
| Double counting | Same signal enters Matching and OTHERS | Audit ledger; reduce or reject residual contribution |
| False independence | Relayed duplicates treated as corroboration | Merge provenance families; recalculate uncertainty |
| Miscalibrated reputation | Confidence rises while predictive accuracy falls | Quarantine source or model; recalibrate and retest |
| Unsafe guidance | Higher score selects prohibited actions | Enforce hard constraints before action selection |
| Cost illusion | Better performance uses more unreported compute | Recompute matched-budget comparison |
| Fragile feature promotion | Held-out regression or context failure | Roll back feature; retain evidence and counterexamples |
| Biological overclaim | Behavioral analogy presented as neural fact | Reframe as computational hypothesis |

A hard-constraint violation, unresolved provenance corruption, or unreproducible primary result blocks promotion of the corresponding implementation or claim. It need not block publication of a clearly labeled negative research finding.

## 13. Deliverables and suggested release sequence

### Phase A — Theory and contracts

- Mathematical proof/counterexample notebook or paper appendix.
- Versioned operator and evidence schemas.
- Conformance test descriptions, including boundary cases.
- Preregistered H-MDI protocol templates.

### Phase B — Controlled evaluation

- Synthetic benchmark definitions and generator documentation.
- Baseline/variant comparison tables with uncertainty.
- Negative controls, ablations, and resource accounting.
- A list of supported, unsupported, and contradicted claims.

### Phase C — System integration

- MET adapter contract and fallback audit.
- Candidate-discovery and budgeted-testing evaluations.
- Reliability calibration and counter-evidence tests.

### Phase D — Relay and growth

- Provenance-preserving relay packet examples.
- Duplicate-evidence and cross-context transfer reports.
- Feature-promotion proposal, review, and rollback record.

### Phase E — Independent review

- External replication report and discrepancy log.
- Biomimetic interpretation boundaries.
- Updated OPEN-QUESTIONS and future directions.

**Publication policy:** The proposed BM-ODWEI v1.1.0 extension can be published as a **theory-first research release** before implementation results exist, provided it does not imply that validation has been completed. Later experimental artifacts should be published as distinct, versioned follow-ups. Historical BM-ODWEI v1.0.0 release materials remain unchanged.

## 14. Minimal experiment report template

```text
Experiment ID:
Hypothesis ID (H-MDI-...):
Claim category: mathematical / conformance / empirical / biomimetic
Operator and contract versions:
Perspective specification and provenance:
Metric assumptions and degeneracy policy:
Dataset/scenario manifest and independence split:
Baseline and comparison arms:
Primary endpoint and preregistered success/failure threshold:
Compute/test budget and measurement boundary:
Seeds, uncertainty method, and multiplicity policy:
Results (including null/negative outcomes):
Counter-evidence, anomalies, and safety violations:
Provenance and relay overlap audit:
Replication status:
Supported conclusion (narrow wording):
Unresolved limitations and next action:
```

## 15. Research questions after the first validation cycle

The first cycle should inform, not assume answers to, the following:

1. When is a metric-native potential preferable to a learned non-potential directional relation?
2. Can directional guidance improve **discovery** independently of final ranking quality?
3. What is the smallest reliable evidence ledger that prevents Matching/OTHERS leakage?
4. Which hypotheses are worth testing when test cost, false alarms, and risk are asymmetric?
5. How should reputation transfer across Perspectives, sources, and nonstationary contexts?
6. When does a validated OTHERS signal become a new feature rather than a temporary correction?
7. Can question generation itself be treated as a future, separately scoped form of pre-decisional cognitive guidance?

The last question is a possible **future research relay**, not a claim that MDI already solves autonomous question generation.

## 16. Conclusion

The MDI validation program is deliberately staged: **definitions before operators; proofs and contracts before performance claims; controlled comparisons before integration claims; provenance before collective relay; and independent validation before structural promotion**. This sequence is intended to keep directional intuition research ambitious while preserving clear boundaries between formal mathematics, engineering evidence, and speculative biomimetic interpretation.

The intended outcome is not an unconditional assertion that MDI is superior to matching. It is a collection of **reproducible, bounded, and revisable findings** that show where Perspective-conditioned directional intelligence adds value, where it fails, and which validated components can be safely reused or grown.

---

**Related:** [MDI-Extension-README](MDI-Extension-README.md) · [MDI-Extension-CONTENTS](MDI-Extension-CONTENTS.md) · [MDI-Extension-GLOSSARY](MDI-Extension-GLOSSARY.md) · [MDI-Extension-OPEN QUESTIONS](MDI-Extension-OPEN-QUESTIONS.md) · [MDI-Extension-TESTABLE HYPOTHESES](MDI-Extension-TESTABLE-HYPOTHESES.md) · [MDI-006](docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md)
