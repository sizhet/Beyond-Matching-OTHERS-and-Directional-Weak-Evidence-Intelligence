# MDI-006 — Evidence Relay, Validation, and Structural Growth

**Research extension:** Metric-Directional Intuition (MDI)  
**Parent research program:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Status:** Theory-first research proposal; candidate contracts and falsifiable hypotheses  
**Version:** 1.1.0 research-extension draft  
**Date:** 2026-10-27

## Abstract

Directional scoring becomes scientifically and operationally useful only when its claims, evidence, uncertainty, and failure cases can be inspected and transferred. This paper completes the six-part Metric-Directional Intuition (MDI) extension by defining an evidence-relay architecture, a validation program, and a governed path from weak OTHERS evidence to reusable structural scoring capabilities. It distinguishes transferable observations from transferable interpretations; proposes typed, provenance-preserving relay packets; establishes baseline-preserving conformance criteria; and outlines experiments for Euclidean sails, metric-native directional operators, learned directional relations, and lightweight hypothesis-guided scoring. Structural growth is treated as a conditional outcome of replicated evidence and governance, not as an automatic consequence of accumulating observations. The proposed system is a research architecture, not a claim that animal cognition implements these operators or that a new mathematical metric has been established.

**Keywords:** structural intelligence; OTHERS; directional scoring; metric-native intelligence; evidence relay; provenance; counter-evidence; hypothesis testing; reputation; structural growth; conformance; validation.

---

![Fig-008-Directional-Intuition-Grand-Map.png](figures/Fig-008-Directional-Intuition-Grand-Map.png)

**Figure 008. Directional Intuition — Grand Map.** Conceptual integration of matching evidence, the OTHERS open-evidence space, perspective-conditioned directional scoring, pre-decisional guidance, hypothesis testing, reputational evaluation, MET integration, and evidence-driven structural growth. Arrows indicate proposed information and control relationships rather than proven causal or neural mechanisms.

---

![Fig-011-Hypothesis-Reputation-Relay-Loop.png](figures/Fig-011-Hypothesis-Reputation-Relay-Loop.png)

**Figure 011. Hypothesis–Reputation–Relay Loop.** A proposed low-budget cycle in which directional hypotheses guide targeted evidence gathering, evaluation updates context-specific reliability, and provenance-preserving relay supports further testing. Promotion of OTHERS evidence into established matching features requires independent validation and governance rather than mere repetition.

---

## 1. Purpose and Position in the MDI Series

MDI-001 defined the research problem and boundaries. MDI-002 specified Euclidean and metric-native directional operators. MDI-003 distinguished pre-decisional guidance from post-generation evaluation. MDI-004 introduced OTHERS-residual allocation and optional MET integration. MDI-005 examined bounded hypothesis portfolios, low-cost tests, and contextual reputation. This final paper asks a different question:

> Under what conditions may a directional observation, hypothesis, or scoring component be trusted, reused by another agent, and eventually promoted into a durable structural capability?

The answer requires **evidence relay**, **independent validation**, and **governed structural growth**. These are separate stages. Successful transmission does not imply truth; repeated execution does not imply independent confirmation; and predictive utility does not by itself establish causal or biological interpretation.

## 2. Scope and Non-Claims

The proposed architecture covers: (i) evidence records, (ii) directional-scoring result records, (iii) hypothesis and test records, (iv) provenance and reputation, (v) cross-context relay, (vi) validation, and (vii) controlled promotion of residual evidence into matching features or structural units.

It does **not** establish that a directional similarity score is a metric. In particular, a score-defined dissimilarity \(D_I=1-S_I\) need not be symmetric, satisfy identity of indiscernibles, or obey the triangle inequality. Nor does it establish that metric-native scoring is biologically implemented by animals, that Beta-Bernoulli updates are calibrated in every setting, or that structural growth is guaranteed. Those are distinct hypotheses requiring empirical work.

## 3. Architectural Overview

The candidate workflow is:

```text
State / candidate / perspective / metric contract
                    |
          Matching baseline S_M
                    |
     OTHERS residual evidence detection
                    |
  Directional operator + uncertainty report
                    |
  Hypothesis portfolio / discriminating tests
                    |
    Evidence and counter-evidence ledger
                    |
       Validation and governance gates
                    |
     Typed, provenance-preserving relay
                    |
    Reuse / adaptation / rejection / quarantine
                    |
   Candidate structural feature or unit promotion
                    |
    New baseline, monitoring, and revalidation
```

Each arrow represents a contract boundary, not an assumption that all stages must be executed in every use. For example, a low-risk local scorer may return a baseline result without invoking a relay subsystem. Missing or invalid directional evidence must not silently fabricate a directional adjustment.

## 4. Evidence Objects and Their Semantics

An **EvidenceRecord** is a claim-linked observation, not an unqualified assertion of truth. A minimal conceptual schema is:

| Field | Meaning |
|---|---|
| `evidence_id` | Stable identifier and deduplication key |
| `claim_id` | Claim or hypothesis being supported or challenged |
| `observation` | Recorded measurement or event, with units and interpretation boundaries |
| `source_id` | Sensor, person, agent, dataset, or publication identifier |
| `time_context` | Observation time, validity window, and ordering |
| `state_context` | Relevant environmental and subject conditions |
| `perspective_id` | Perspective under which directional significance is evaluated |
| `metric_contract_id` | Metric and goal-set semantics, if applicable |
| `evidence_role` | Support, counter-evidence, neutral, or ambiguous |
| `dependence_group` | Shared upstream data or correlated source cluster |
| `quality` | Measurement quality and known limitations |
| `provenance` | Transformation lineage and original-source pointers |
| `privacy_policy` | Access, consent, retention, and permitted reuse |

Records should distinguish the raw observation from the interpretation that it supports a directional claim. A single observation may support one hypothesis and undermine another. Source reputation and evidence strength are separate variables.

## 5. Directional Scoring as a Relayable Claim

A **DirectionalScoreRecord** binds a result to its scoring conditions:

$$
R_D=(A,B,P,M,O,\hat s,u,e,\nu),
$$

where \(A,B\) are evaluated structures or transitions, \(P\) is the perspective, \(M\) the metric or structural-relation contract, \(O\) the operator specification, \(\hat s\) the result, \(u\) an uncertainty description, \(e\) evidence references, and \(\nu\) versioned implementation metadata.

For a metric space \((\mathcal X,d)\) and nonempty goal set \(G_P\), the candidate metric-native operator is

$$
C_P(x,y)=\frac{d(x,G_P)-d(y,G_P)}{d(x,y)},\qquad x\ne y.
$$

Provided \(d(x,G_P)=\inf_{g\in G_P}d(x,g)\) is finite, distance-to-set is 1-Lipschitz and therefore \(-1\le C_P(x,y)\le1\). For \(x=y\), the operator requires an explicit undefined, neutral, or no-transition policy; a division by zero must not be concealed. The goal set, metric, and state mapping are essential relay metadata: transferring the number alone destroys its semantics.

In Euclidean directional sails, the operator may instead use normalized vector alignment; in a learned structural relation, it may use \(\Phi_P(x,y)\). These three **representation routes** must not be conflated with the independent **hypothesis-testing mechanism** of MDI-005.

## 6. Evidence Relay Contracts

We propose four relayable units:

1. **ObservationRelay:** raw or minimally transformed observations, with source, context, permissions, and lineage.
2. **HypothesisRelay:** hypothesis statement, alternatives, predicted outcomes, test plan, and status.
3. **DirectionalOperatorRelay:** operator contract, assumptions, calibration, known failure cases, and implementation version.
4. **FeatureCandidateRelay:** proposed structural feature, residual coverage, validation evidence, and promotion eligibility.

A common **RelayEnvelope** should include `schema_version`, `unit_type`, `unit_id`, `issuer`, `created_at`, `source_lineage`, `dependencies`, `perspective_scope`, `context_scope`, `claims`, `supporting_evidence`, `counter_evidence`, `uncertainty`, `reputation_scope`, `evaluation_status`, `policy_constraints`, and `content_digest`.

These fields are normative candidates, not a finalized machine-readable standard. The envelope should preserve an **explicit leftover**: what was not measured, what failed, what could not be transferred, and what remains unresolved.

## 7. Relay Is Not Replication

Repeated execution may be valuable **data accumulation relay**, even when it does not add a new algorithmic unit. However, it must not be mistaken for independent replication. Ten runs using one contaminated dataset or one shared sensor can be less informative than two genuinely independent measurements.

We therefore distinguish:

- **Execution relay:** repeated observations and outcomes from a common operational process.
- **Evidence relay:** transfer of records and their limitations.
- **Interpretation relay:** transfer of hypotheses and directional explanations.
- **Capability relay:** transfer of validated operators, features, or executable structural units.

A receiver must be allowed to accept the observations while rejecting the interpretation or operator. Reuse is conditional on contract compatibility, provenance integrity, and local governance.

## 8. Reputation as Contextual, Revisable Evidence

Reputation is not an intrinsic universal property of a hypothesis or source. It is scoped to task, environment, measurement process, and time. A simple Beta-Bernoulli model can summarize repeated binary outcomes under suitable assumptions:

$$
\mathbb E[\theta\mid s,f]=\frac{\alpha+s}{\alpha+\beta+s+f}.
$$

This is not a generic substitute for calibrated predictive probabilities. Correlated trials, changing environments, ambiguous outcomes, selective reporting, and adversarial manipulation require alternative or extended models. A relay must carry enough context to prevent an apparently high score from being reused outside its valid domain.

Counter-evidence must remain attached to the claim. Negative findings are first-class relay content, not records to be discarded during summarization or structural folding.

## 9. Validation Framework: What Must Be Compared

A robust study should compare systems under matched computational and information budgets:

| Condition | Description | Main purpose |
|---|---|---|
| B0 | Matching-only MET baseline | Establish original task performance |
| B1 | Baseline + Euclidean single-sail score | Test simple directionality |
| B2 | Baseline + multi-sail or vector field | Test richer Euclidean perspectives |
| B3 | Baseline + metric-native goal-distance operator | Test non-embedding route |
| B4 | Baseline + learned structural directional relation | Test flexible non-potential relations |
| B5 | B1–B4 + OTHERS-residual allocation | Test double-counting controls |
| B6 | B5 + lightweight hypothesis selection/testing | Test decision value per unit compute |
| B7 | B6 + reputation, provenance, and relay governance | Test reliable cross-context reuse |
| N1 | Random or permuted perspective | Detect spurious perspective benefit |
| N2 | Misaligned goal or invalid metric contract | Test sensitivity to semantics |
| N3 | Correlated or duplicated evidence injection | Test evidence leakage and false confidence |
| N4 | Shifted environment and adversarial evidence | Test robustness and abstention |

B4 is a candidate family, not necessarily comparable without additional complexity controls. Evaluations must separate **candidate discovery** from **candidate ranking**, and **local scoring improvement** from **cross-agent relay improvement**.

## 10. Metrics and Evaluation Protocol

Use task-appropriate primary outcomes: ranking quality, top-k candidate recall, decision utility, regret, calibration, out-of-distribution robustness, and cost per successful decision. Supporting metrics include:

- **Coverage:** proportion of cases with valid directional evidence.
- **Incremental lift:** difference from B0 under matched data and compute.
- **Residual attribution accuracy:** evidence incorrectly counted in both Matching and OTHERS.
- **Calibration:** relationship between stated confidence and observed success.
- **Counter-evidence sensitivity:** ability to downgrade a previously supported claim.
- **Relay portability:** performance after transfer without retraining or with bounded adaptation.
- **Contract failure rate:** invalid transfers correctly rejected or quarantined.
- **Growth yield:** fraction of promoted features that retain value on held-out future data.

Prespecify evaluation datasets, train/validation/test separation, outcome definitions, confidence intervals, and statistical tests. Avoid choosing perspectives or thresholds on the test set. Report negative results, ablations, and computational overhead, not just headline accuracy.

## 11. OTHERS-to-Feature Promotion

Let \(e\) be a residual signal not already explained by the matching feature set \(\mathcal F\). Promotion is a governed state transition:

```text
Unexplained residual
    -> candidate hypothesis
    -> discriminating evidence
    -> independently checked predictor
    -> scoped feature proposal
    -> compatibility / leakage / fairness checks
    -> shadow-mode deployment
    -> approved matching feature
    -> post-promotion monitoring or rollback
```

A proposed feature \(f_e\) should be promoted only if it (a) has a stable operational definition, (b) provides incremental predictive or decision value on held-out data, (c) does not double-count existing evidence, (d) satisfies policy constraints, and (e) retains counter-evidence and provenance. A useful decision criterion is

$$
\Delta U_e=U(\mathcal F\cup\{f_e\})-U(\mathcal F)-operatorname{Cost}(f_e),
$$

estimated out of sample and subject to governance gates. Positive \(\Delta U_e\) is necessary under this objective, but not sufficient for universal promotion. Domain drift may require rollback; a feature may remain useful only for a specific perspective or context.

## 12. Cross-Agent and Cross-Context Interoperability

A receiver should perform at least five checks before reuse:

1. **Schema compatibility:** can the relay object be parsed without semantic loss?
2. **Metric/perspective compatibility:** do goal sets, distance functions, and state representations have equivalent meaning?
3. **Evidence lineage:** are observations duplicated, correlated, manipulated, or unavailable?
4. **Policy and sovereignty:** is the receiving agent authorized to use the data or proposed action?
5. **Local validity:** does the transferred unit meet the receiver's calibration, risk, and task requirements?

Where direct compatibility fails, a perspective transformation or adapter may be proposed, but its error and unverified assumptions must be recorded. Never silently translate a directional score across incompatible metrics or goals.

## 13. Conformance Requirements (Candidate MDI-CR)

The following requirements are proposed for future specification work:

| ID | Requirement |
|---|---|
| MDI-CR-001 | Every score declares operator, perspective, metric/relation, and version. |
| MDI-CR-002 | Undefined and missing directional evidence are represented explicitly. |
| MDI-CR-003 | The baseline matching result remains recoverable. |
| MDI-CR-004 | Matching/OTHERS attribution is auditable and duplicate evidence is controlled. |
| MDI-CR-005 | Supporting and counter-evidence are preserved with provenance. |
| MDI-CR-006 | Confidence, source reputation, and hypothesis probability are not conflated. |
| MDI-CR-007 | Dependence and correlation are considered in evidence aggregation. |
| MDI-CR-008 | Relay recipients can reject interpretations independently of observations. |
| MDI-CR-009 | Metric and perspective incompatibilities trigger adaptation or rejection. |
| MDI-CR-010 | No new matching feature is promoted without out-of-sample validation. |
| MDI-CR-011 | Promoted features have monitoring, revision, and rollback provisions. |
| MDI-CR-012 | Data rights, privacy, and action sovereignty remain enforceable. |
| MDI-CR-013 | Failed tests, negative results, and unresolved leftovers remain accessible. |
| MDI-CR-014 | Biological analogies are labeled as hypotheses, not implementation facts. |
| MDI-CR-015 | Computational and evidence budgets are disclosed for comparative results. |
| MDI-CR-016 | The distinction between score distance and mathematical metric is maintained. |

Conformance to this draft checklist is a design target, not a claim of existing implementation or certification.

## 14. Testable Research Hypotheses

**H1 — Incremental directional utility.** Under appropriate perspectives, directional scoring improves held-out decision utility beyond matching-only baselines.

**H2 — Metric-native competitiveness.** In tasks with meaningful non-Euclidean metric structure, metric-native goal-distance scoring is competitive with or superior to Euclidean embeddings at matched resource budgets.

**H3 — Residual allocation.** OTHERS-only evidence allocation reduces double counting and improves calibration relative to unrestricted combination.

**H4 — Pre-decisional benefit.** Directional guidance improves candidate recall or cost-efficiency, not merely ranking of fixed candidates.

**H5 — Hypothesis efficiency.** Budgeted discriminating tests achieve higher decision utility per unit cost than unstructured or exhaustive testing in selected environments.

**H6 — Contextual reputation.** Context-scoped, dependence-aware reputation is better calibrated under distribution shift than unscoped counts.

**H7 — Relay portability.** Typed evidence and operator relay improves reuse and error detection across agents relative to unstructured textual handoff.

**H8 — Governed growth.** Features promoted through independent validation retain more out-of-sample value and have lower rollback incidence than ungoverned feature accumulation.

Each hypothesis can fail. The program should document disconfirming outcomes rather than reinterpreting every result as support.

## 15. Suggested Validation Roadmap

**Phase 0 — Definitions and reference datasets.** Freeze score semantics, perspective contracts, task utilities, and baseline splits. Identify tasks where Euclidean and metric-native operators are meaningfully distinguishable.

**Phase 1 — Operator conformance.** Unit-test range bounds, identity/zero-transition handling, normalization, missing evidence, metric assumptions, and perspective mismatches.

**Phase 2 — Controlled scoring experiments.** Compare B0–B5 with random-perspective and duplicate-evidence controls; report effect sizes and calibration.

**Phase 3 — Guidance and hypothesis tests.** Compare candidate generation and evidence selection with equal compute/test budgets; measure decision value and regret.

**Phase 4 — Relay experiments.** Transfer evidence and operators among isolated agents and datasets; test semantic compatibility, provenance loss, and counter-evidence propagation.

**Phase 5 — Structural promotion.** Run shadow-mode feature promotion, longitudinal monitoring, and rollback; distinguish observed gain from data leakage or shifting baselines.

**Phase 6 — Open-ended research.** Explore metric-native directional relations, non-potential preference cycles, learned hypothesis portfolios, and cross-perspective governance.

A future implementation should publish machine-readable schemas, conformance fixtures, test harnesses, and reproducibility artifacts separately. This theory-first document does not claim those artifacts already exist.

## 16. Worked Research Scenario: Navigational Choice Under Sparse Evidence

Consider an agent choosing between routes in a changing environment. A matching baseline evaluates known route attributes. A directional perspective prioritizes progress toward a destination while respecting hazards. The metric-native operator evaluates goal-distance reduction, while OTHERS contains unmodeled cues such as an intermittent obstacle signal. The agent forms two hypotheses: the cue indicates a genuine blockage, or it is sensor noise. It selects a low-cost observation that best discriminates the hypotheses, records the outcome, and updates context-scoped source reputation.

A second agent may receive the raw observation, the test conditions, and the hypothesis record. It should not inherit the first agent's route recommendation unless map metric, hazard policy, and time context are compatible. Repeated observations may support a new obstruction feature, but only after independent validation. If the cue disappears, counter-evidence must update or retire the feature.

This is an illustrative design scenario, not a reported experiment or a claim of improved performance.

## 17. Failure Modes and Governance

**Perspective capture:** one goal dominates despite conflicting constraints. Mitigation: explicit perspective hierarchy and hard constraints.

**Potential-field traps:** local directional improvement fails to produce global progress. Mitigation: multi-trail exploration, horizon checks, and alternative hypotheses.

**Metric misuse:** distances are incomparable or fail metric assumptions. Mitigation: operator contracts and conformance tests.

**Evidence laundering:** relay strips caveats and makes weak signals appear authoritative. Mitigation: immutable provenance and receiver-side verification.

**Reputation cascades:** correlated endorsements create artificial certainty. Mitigation: dependence groups, source diversity, and calibration.

**Feature ossification:** promoted signals become permanent despite drift. Mitigation: monitoring, expiry, rollback, and counter-evidence.

**Goodhart effects:** optimization of a scoring proxy degrades real-world outcomes. Mitigation: multiple evaluators, adversarial testing, and outcome audits.

**Sovereignty violations:** transferred units trigger actions outside authorization. Mitigation: recipient-controlled execution and explicit policy gates.

## 18. Relationship to the Parent BM-ODWEI Repository

This extension is additive and non-destructive:

- **BM-001/002:** matching limits and the OTHERS evidence space remain foundational.
- **BM-003/005:** directional sails and perspective-distance motivate the new operators.
- **BM-004:** reputational intelligence motivates context-scoped evidence reliability.
- **BM-006:** structural scoring growth motivates feature promotion.
- **BM-007:** counter-evidence and provenance motivate relay governance.
- **BM-008:** unified architecture and validation motivate the research roadmap.

No revision of BM-001–008 is required for the claims in this paper. Cross-references can be added in the extension README and parent navigation files. Version 1.1.0 is a proposed release designation and should be reconciled with the repository's actual publication state.

## 19. Connections to the Wider Structural Intelligence Program

**MET:** optional directional adapters and residual evidence attribution.

**UCPSF:** multi-perspective scoring, evaluator reconciliation, and control-plane governance.

**SIF:** residual-driven growth, precedent tracking, and conformance-first engineering.

**UIERU:** forward guidance, multi-trail exploration, evidence relay, and composable intelligence units.

**BUI-DSI:** dynamic structural observation, perspective transformations, and changing equivalence conditions.

These are conceptual integration opportunities, not declarations that compatible APIs or implementations already exist.

## 20. Open Research Questions

1. When is a goal-distance potential sufficient, and when must directional preference be non-potential or cyclic?
2. Which metric-native directional operators best preserve useful task semantics under structural transformations?
3. Can evidence dependence be estimated reliably from sparse, heterogeneous sources?
4. What is the minimal relay envelope that preserves reproducibility without excessive overhead?
5. How should a receiving agent recalibrate reputation when contexts differ?
6. Which hypothesis-selection policies are robust under severe compute and observation budgets?
7. How can residual feature promotion be made reversible and resistant to Goodhart effects?
8. Can pre-decisional directional guidance improve open-ended question generation and inquiry relay?
9. Which findings, if any, support a substantive analogy to animal intuition rather than only engineering utility?
10. How should human and agent sovereignty be expressed in compositional relay contracts?

## 21. Conclusion

The MDI research program proposes a progression from matching baselines and directional weak evidence to metric-native operators, pre-decisional guidance, lightweight hypothesis testing, and contextual reputation. This paper adds the missing discipline: **evidence must remain traceable, claims must remain falsifiable, relay must preserve limitations, and structural growth must be earned through validation**.

The most important distinction is between transmitting a plausible directional story and transmitting an inspectable, reproducible research object. Only the latter can support cumulative structural intelligence without hiding uncertainty, double counting, or counter-evidence. The resulting architecture is a candidate research framework whose value must be demonstrated through conformance testing, controlled experiments, and transparent reporting of failures.

---

## Appendix A. Minimal Relay Acceptance Checklist

- [ ] Source and transformation lineage are available.
- [ ] Metric, perspective, goal, and operator semantics are declared.
- [ ] Evidence dependence and duplication risks are identified.
- [ ] Support and counter-evidence are retained.
- [ ] Uncertainty and reputation scopes are explicit.
- [ ] Receiving context and policies are compatible.
- [ ] Baseline and fallback behavior are defined.
- [ ] Transfer restrictions and privacy permissions are satisfied.
- [ ] Local validation status is recorded.
- [ ] Rejection, quarantine, and rollback paths are available.

## Appendix B. Terminology

**Directional score:** a perspective-conditioned measure of alignment or progress, not necessarily a metric.  
**Metric-native:** formulated directly using a metric space without requiring Euclidean embedding.  
**OTHERS:** weak or not-yet-matched evidence outside established matching coverage.  
**Residual attribution:** assignment of incremental evidence to prevent duplicate counting.  
**Evidence relay:** transfer of observations, provenance, and limitations.  
**Capability relay:** transfer of a validated operator or structural unit.  
**Reputation:** context-dependent estimate of reliability or predictive performance.  
**Structural promotion:** governed transition of a validated residual signal into a reusable feature.  
**Explicit leftover:** documented unresolved information, failures, and untransferred constraints.

## References and Research Lineage

- BM-ODWEI parent research documents, BM-001–BM-008, in the associated repository.
- MDI-001 — *Problem Definition and Research Boundaries*.
- MDI-002 — *Euclidean and Metric-Native Directional Scoring*.
- MDI-003 — *Perspective Fields and Pre-Decisional Guidance*.
- MDI-004 — *OTHERS Residual Scoring and MET Integration*.
- MDI-005 — *Lightweight Hypothesis Testing and Reputation*.

*This paper is a proposed research extension. No experimental results, certification, or empirical biological validation are claimed.*
