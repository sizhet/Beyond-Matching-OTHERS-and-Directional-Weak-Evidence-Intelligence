# Open Questions — Metric-Directional Intuition (MDI)

**Research extension:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Location:** `extensions/metric-directional-intuition/MDI-Extension-OPEN-QUESTIONS.md`  
**Status:** Open research agenda; hypotheses and proposed operators, not validated cognitive mechanisms  
**Companion papers:** MDI-001–MDI-006  
**Version:** Draft for the proposed BM-ODWEI v1.1.0 extension

## 1. Purpose and scope

This document maintains a falsifiable research agenda for **perspective-conditioned intuitive similarity, metric-native directional evaluation, pre-decisional guidance, OTHERS-residual scoring, lightweight hypothesis testing, reputational intelligence, and evidence relay**. It does not revise the definitions or historical claims of BM-001–BM-008. Questions are intentionally separated from results: a mathematical property of a defined operator is not evidence that the operator improves decisions or models biological intuition.

Each question below identifies a **research uncertainty**, a **candidate method**, and an **observable resolution criterion**. See `TESTABLE-HYPOTHESES.md` and `VALIDATION-ROADMAP.md` for subsequent operationalization.

## 2. Mathematical foundations and score semantics

### OQ-MDI-001 — What is the minimal structure needed for directionality?

A metric `d` alone specifies separation, not preferred movement. Which additional structure is minimally sufficient: a goal set, scalar potential, ordered preferences, local transition relation, or context-indexed comparison oracle?

- **Candidate method:** Compare metric-plus-goal, metric-plus-potential, and learned pairwise preference formulations on the same finite and continuous spaces.
- **Resolution criterion:** Explicit existence assumptions, invariance properties, and counterexamples distinguishing the formulations.
- **Relevant:** MDI-001, MDI-002.

### OQ-MDI-002 — When can metric-native direction be represented by a potential?

Given a context-dependent relation `Phi_P(x,y)`, when does a scalar `V_P` exist such that its directional preference agrees with the relation? Nontransitive cycles and path dependence may prevent this.

- **Candidate method:** Study cyclic preferences, integrability/path-independence, and graph potential reconstruction with residual inconsistency reports.
- **Resolution criterion:** Necessary or sufficient conditions for representability, plus counterexamples.
- **Relevant:** MDI-002, MDI-003.

### OQ-MDI-003 — How should degenerate transitions be scored?

The goal-distance directional quotient

$$
C_P(x,y)=\frac{d(x,G_P)-d(y,G_P)}{d(x,y)}
$$

is defined for `x != y`, assuming a nonempty goal set and finite distance-to-goal values. What is the appropriate policy for `x=y`, unreachable goals, disconnected spaces, or uncertain distances?

- **Candidate method:** Define abstention, explicit zero-motion status, interval-valued scores, and contract-specific reachability checks.
- **Resolution criterion:** A complete edge-case table with conformance tests; no silent division by zero or fabricated direction.
- **Relevant:** MDI-002, MDI-004.

### OQ-MDI-004 — Which score transformations preserve intended ranking?

How do cosine normalization, convex mixture, additive residual correction, clipping, and log-odds correction affect rankings, calibration, and sensitivity to the baseline score?

- **Candidate method:** Prove monotonicity where possible and construct rank-reversal counterexamples under different mixture weights.
- **Resolution criterion:** Operator-specific guarantees and empirical calibration curves.
- **Relevant:** MDI-002, MDI-004.

### OQ-MDI-005 — When, if ever, does intuitive distance form a metric?

For `D_I=1-S_I`, symmetry, identity of indiscernibles, and triangle inequality are not guaranteed. Can restricted constructions satisfy metric axioms without losing perspective dependence?

- **Candidate method:** Analyze symmetric agreement-based alternatives, metric-preserving transforms, and finite-space exhaustive checks.
- **Resolution criterion:** A theorem for a restricted class or explicit counterexamples and a clear `distanceScore` naming convention.
- **Relevant:** MDI-001, MDI-002.

## 3. Representation, perspectives, and forward guidance

### OQ-MDI-006 — When does metric-native scoring outperform Euclidean projection?

Does a metric-native operator improve robustness in graph, symbolic, non-Euclidean, or mixed structural domains, compared with a well-tuned Euclidean embedding baseline?

- **Candidate method:** Matched-budget comparisons with representation quality controlled and embedding costs included.
- **Resolution criterion:** Reproducible gains on prespecified tasks, including failure cases and uncertainty intervals.
- **Relevant:** MDI-002, MDI-006.

### OQ-MDI-007 — How should multiple conflicting perspectives be governed?

How can a system combine goal alignment, safety, resource limits, and subject-specific preferences without masking unacceptable trade-offs in a single weighted average?

- **Candidate method:** Compare weighted aggregation, lexicographic constraints, Pareto filtering, and veto policies.
- **Resolution criterion:** Measured trade-offs and explicit records of unresolved perspective conflict.
- **Relevant:** MDI-003, MDI-004.

### OQ-MDI-008 — Does pre-decisional guidance increase candidate quality?

Can perspective fields guide attention and candidate generation toward useful but otherwise undiscovered options, rather than merely reranking a fixed candidate set?

- **Candidate method:** Separate *candidate recall/coverage* from *ranking quality* under equal search budgets.
- **Resolution criterion:** Improvement in held-out candidate discovery without unacceptable loss of diversity or safety.
- **Relevant:** MDI-003, MDI-006.

### OQ-MDI-009 — How should directionality evolve under changing contexts?

Can a direction field adapt to nonstationary goals, moving hazards, or changed constraints without amplifying stale reputations or causing oscillatory behavior?

- **Candidate method:** Dynamic benchmarks with drift detectors, forgetting, and context-indexed policies.
- **Resolution criterion:** Bounded adaptation lag and documented stability/failure behavior.
- **Relevant:** MDI-003, MDI-005.

## 4. OTHERS, MET integration, and evidence governance

### OQ-MDI-010 — How can overlapping evidence be allocated without double counting?

Matching evidence and OTHERS evidence may share sources, features, or causal ancestry. Is soft matching coverage sufficient, or must allocation be based on a provenance/causal graph?

- **Candidate method:** Compare feature-level residual weights with evidence-lineage-aware allocation on intentionally duplicated data.
- **Resolution criterion:** Quantified inflation under duplicate/correlated evidence and an auditable attribution ledger.
- **Relevant:** MDI-004, MDI-006.

### OQ-MDI-011 — When should residual correction abstain?

What constitutes enough support to alter the baseline Matching score? How should the system distinguish missing evidence, contradictory evidence, and low-confidence evidence?

- **Candidate method:** Selective prediction and calibration studies with abstention/fallback thresholds.
- **Resolution criterion:** Prespecified reliability and coverage trade-offs; baseline restoration when evidence is unavailable.
- **Relevant:** MDI-004.

### OQ-MDI-012 — How can OTHERS evidence become a validated matching feature?

What independent evidence, stability, and governance conditions justify promoting an OTHERS hypothesis into a reusable feature?

- **Candidate method:** Preregister feature-promotion gates with held-out validation and rollback tests.
- **Resolution criterion:** Promotion improves out-of-sample performance without leakage; negative outcomes remain visible.
- **Relevant:** MDI-004, MDI-006.

### OQ-MDI-013 — What is the minimal MET integration contract?

Which fields must a directional adapter expose for reproducibility: baseline score, operator version, perspective, metric definition, evidence IDs, confidence, counter-evidence, and fallback reason?

- **Candidate method:** Contract-first schema review and cross-implementation conformance tests.
- **Resolution criterion:** Interoperable outputs and exact baseline compatibility when the extension is disabled.
- **Relevant:** MDI-004, MDI-006.

## 5. Hypothesis testing, reputation, and bounded computation

### OQ-MDI-014 — When are a few hypotheses better than broad search?

Can a small, well-selected hypothesis portfolio outperform exhaustive or random hypothesis generation at equal inference, tool, and observation budgets?

- **Candidate method:** Budget-controlled benchmarks with portfolio-size ablations and adversarial missing-hypothesis cases.
- **Resolution criterion:** Decision quality per unit cost and explicit coverage failures.
- **Relevant:** MDI-005.

### OQ-MDI-015 — How should tests be selected under partial observability?

When is expected information gain insufficient, and when does expected **decision** value of information justify a test despite its cost?

- **Candidate method:** Compare entropy reduction, expected value of information (EVI), and heuristic directional tests in sequential decisions.
- **Resolution criterion:** Lower regret or better utility at controlled test cost; transparent assumptions about utility and outcomes.
- **Relevant:** MDI-005.

### OQ-MDI-016 — What exactly should reputation estimate?

A hypothesis's truth probability, a source's reliability, a test's discrimination power, and an operator's calibration are different quantities. How should they be represented and updated separately?

- **Candidate method:** Hierarchical or context-conditioned models with independent calibration diagnostics.
- **Resolution criterion:** Reduced conflation, improved calibration, and traceable update provenance.
- **Relevant:** MDI-005, MDI-006.

### OQ-MDI-017 — How should reputation handle dependent and adversarial evidence?

Naive Beta–Bernoulli updates assume well-defined outcomes and often independence/stationarity. What corrections are needed for repeated observations, correlated sources, feedback loops, or strategic manipulation?

- **Candidate method:** Compare naive counts with dependency-aware, context-stratified, and adversarially robust updates.
- **Resolution criterion:** Measured resistance to duplicated evidence and source collusion, with clear computational overhead.
- **Relevant:** MDI-005, MDI-006.

### OQ-MDI-018 — Can low-cost intuition remain calibrated under distribution shift?

Do lightweight directional hypotheses maintain reliability when the environment, metric, or perspective changes?

- **Candidate method:** Out-of-distribution and temporal-drift evaluations with abstention and reputation decay.
- **Resolution criterion:** Calibration/error curves before and after shift, including recovery time.
- **Relevant:** MDI-005.

## 6. Evidence relay and structural evolution

### OQ-MDI-019 — What information must survive a relay boundary?

How can an Observation, Hypothesis, Operator, or Feature Candidate move between agents or implementations without losing meaning, evidence lineage, or sovereignty constraints?

- **Candidate method:** Canonical relay packet schema with semantic round-trip and cross-runtime tests.
- **Resolution criterion:** Preserved identifiers, assumptions, perspectives, counter-evidence, versioning, and consent/policy fields.
- **Relevant:** MDI-006.

### OQ-MDI-020 — How should repeated execution be distinguished from independent confirmation?

Repeated runs can add useful observations and improve calibration, but shared upstream evidence can make apparent confirmation misleading.

- **Candidate method:** Track common ancestry and distinguish *observation count*, *effective sample size*, and *independent replication*.
- **Resolution criterion:** Relay reports never silently equate repeated correlated runs with independent validation.
- **Relevant:** MDI-005, MDI-006.

### OQ-MDI-021 — What makes structural growth genuinely open-ended?

Can OTHERS-driven discovery produce new useful operators, perspectives, or feature families rather than only retune a fixed scoring function?

- **Candidate method:** Longitudinal benchmarks with frozen baselines, growth logs, and complexity penalties.
- **Resolution criterion:** Novel, reusable, independently validated capabilities and controlled regression risk.
- **Relevant:** MDI-004, MDI-006.

### OQ-MDI-022 — How should negative results be relayed?

Can counter-evidence, failed hypotheses, and rejected feature promotions become first-class reusable assets instead of being discarded?

- **Candidate method:** Versioned counter-evidence packets and replayable rejection rationales.
- **Resolution criterion:** Lower repeated-error rate and measurable reuse of negative evidence across tasks.
- **Relevant:** MDI-005, MDI-006.

## 7. Biological interpretation and epistemic boundaries

### OQ-MDI-023 — Is metric-native directionality a useful model of animal intuition?

Can metric-native directional mechanisms explain behavioral data better than Euclidean-vector, model-free, or conventional control baselines? Similar behavioral predictions do not establish neural implementation.

- **Candidate method:** Behavioral-model comparison with matched complexity and independently collected observations.
- **Resolution criterion:** Out-of-sample predictive advantage, identifiable predictions, and explicit limits on biological inference.
- **Relevant:** MDI-001, MDI-003, MDI-005.

### OQ-MDI-024 — Are lightweight hypothesis tests a plausible cognitive abstraction?

Do animals or humans behave *as if* they select a few discriminating tests before action, and can this be separated from simpler heuristic explanations?

- **Candidate method:** Competing cognitive models and interventions on information availability, time pressure, and test cost.
- **Resolution criterion:** Distinct predictions that separate hypothesis testing from reactive heuristics; no unsupported claims of neural equivalence.
- **Relevant:** MDI-005.

## 8. Prioritization and research dependencies

| Priority | Questions | Why now | Primary deliverable |
|---|---|---|---|
| P0 | 001–005 | Establish semantics, assumptions, and mathematical safety | Definitions, proofs, counterexamples |
| P0 | 010–013, 016–017 | Prevent evidence leakage and unjustified score changes | MET contract, attribution and calibration tests |
| P1 | 006–009, 014–015, 018 | Test usefulness under fixed budgets | Comparative experiments and ablations |
| P1 | 019–022 | Enable portable, auditable learning | Relay schema and longitudinal validation |
| P2 | 023–024 | Evaluate biomimetic interpretation without overclaiming | Competing-model studies |

Priority is a proposed order, not a claim that all questions are independent. For example, tests of metric-native improvement depend on a stable baseline and well-defined score semantics; reputation tests depend on evidence-lineage tracking.

## 9. Cross-document coordination

- **MDI-001:** scope, definitions, epistemic boundaries.
- **MDI-002:** Euclidean and metric-native mathematical operators.
- **MDI-003:** perspective fields and pre-decisional candidate generation.
- **MDI-004:** OTHERS residual allocation and MET compatibility.
- **MDI-005:** bounded hypothesis testing and reputation.
- **MDI-006:** evidence relay, validation, and structural growth.
- **`TESTABLE-HYPOTHESES.md`:** operational claims, controls, outcomes, and falsification rules.
- **`VALIDATION-ROADMAP.md`:** sequencing, datasets, budgets, governance, and release gates.

## 10. Governance of the open-question registry

Each future update should record: question ID, proposed answer or candidate mechanism, assumptions, supporting and counter-evidence, evaluation protocol, status (`open`, `under-test`, `supported-in-scope`, `refuted-in-scope`, or `superseded`), and links to versioned artifacts. **Do not mark a question solved solely because a formula was defined or a demonstration succeeded.** Distinguish mathematical proof, engineering benchmark evidence, and cognitive/biological interpretation.

The parent BM-ODWEI v1.0.0 research text remains unchanged. This extension is additive and should be released as a new version only after link, metadata, figure, and conformance checks.

---

*End of MDI Open Questions.*
