# MDI-004 — OTHERS Residual Scoring and MET Integration

**Research extension:** Metric-Directional Intuition (MDI)  
**Parent research program:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Status:** Theory-first candidate specification; not an empirically validated algorithm  
**Version context:** Proposed BM-ODWEI v1.1.0 extension  
**License context:** Apache-2.0 (subject to repository LICENSE.txt)

## Abstract

Conventional similarity systems primarily score attributes that have been explicitly modeled and aligned. The BM-ODWEI program proposes **OTHERS** as an open evidence space for signals that are not yet represented by established matching features. This article develops an implementable but representation-agnostic approach to allocating such signals to *residual directional scoring*, without silently counting the same evidence twice. It distinguishes three aggregation operators—convex mixture, additive residual correction, and log-odds residual correction—and specifies their conditions, failure modes, calibration requirements, and fallback behavior. It then proposes an adapter interface for Metric Evaluation Technology (MET), including evidence attribution, perspective contracts, confidence and reliability separation, counter-evidence, and conformance tests. The principal claim is architectural: directional evidence can be admitted as a separately governed scoring channel while preserving the baseline evaluator and its audit trail. No universal improvement in accuracy, biological plausibility, or metric validity is claimed.

**Keywords:** OTHERS; residual evidence; metric-native directionality; perspective; matching; weak-evidence scoring; MET; evidence provenance; calibration; conformance; structural relay.

---

## 1. Purpose and Scope

This document extends the research boundaries of MDI-001, the directional operators of MDI-002, and the pre-decisional guidance concepts of MDI-003. Its engineering question is:

> How can an existing matching-based MET evaluator admit perspective-conditioned directional evidence from OTHERS without destabilizing baseline scoring, duplicating evidence, or overstating uncertainty?

The objectives are to:

1. define an explicit boundary between matching-covered evidence and residual OTHERS evidence;
2. distinguish directional *utility*, *agreement*, and *reliability*;
3. provide bounded combination operators and characterize their different semantics;
4. specify an optional MET adapter with safe fallback and traceable evidence;
5. identify falsifiable hypotheses and conformance requirements.

Out of scope are claims that the proposed operators form a mathematical metric, a validated neuroscience model, or an optimal decision policy. Implementations, learned parameters, and empirical benchmarks are deferred.

## 2. Baseline Evaluation Contract

Let $A$ and $B$ be objects, structures, or states in a domain $\mathcal X$. Let $P$ be a declared perspective or goal specification, and $E$ the available evidence. Assume an existing MET baseline produces

$$
S_M(A,B\mid E_M)\in[0,1],
$$

where $E_M$ contains the evidence used by established matching features. Larger scores denote greater baseline similarity; this convention must be stated rather than assumed for all applications.

The baseline contract must specify: feature definitions, feature coverage, missing-data handling, calibration domain, symmetry (if any), score semantics, and evaluator version. The directional extension **must not silently redefine** these baseline semantics.

Define a separate residual evidence collection $E_O$, with lineage linking it to raw observations. Merely labeling an observation “OTHERS” does not prove independence from $E_M$.

## 3. Evidence Allocation: Matching, OTHERS, and Overlap

### 3.1 Coverage-aware residual weights

For candidate evidence item $e_i$, let

- $q_i\geq0$: predeclared relevance or quality weight;
- $r_i\in[0,1]$: estimated fraction already explained or consumed by matching features;
- $\rho_i\in[0,1]$: admissibility factor for provenance, permission, and quality.

Define

$$
w_i^{O}=q_i(1-r_i)\rho_i.
$$

If $\sum_i w_i^O>0$, normalize $\tilde w_i^O=w_i^O/\sum_j w_j^O$. If the denominator is zero, the directional residual channel is **unavailable**, not a zero-valued directional observation.

This is a candidate attribution mechanism, not a proof of statistical independence. Correlated observations, derived features, and shared sources require additional overlap tests or joint modeling.

### 3.2 Attribution ledger

Each accepted residual item should record:

| Field | Meaning |
|---|---|
| `evidence_id` | Stable identifier for the observation or derived signal |
| `source_id` | Provenance and source reputation context |
| `matching_coverage` | Estimated $r_i$ and method of estimation |
| `residual_weight` | $w_i^O$ and normalization context |
| `perspective_id` | Perspective under which the evidence is evaluated |
| `directional_operator` | Operator and version used |
| `support_or_counter` | Whether evidence supports or challenges a hypothesis |
| `dependencies` | Links to overlapping or derived evidence |
| `timestamp_context` | Relevant time or state validity |

The ledger makes overlap auditable and supports later feature promotion from OTHERS into matching.

## 4. Directional Evidence Is Not a Single Quantity

For a perspective $P$, a directional operator may produce a bounded signed signal

$$
C_P(A,B\mid E_O)\in[-1,1].
$$

Its meaning must be declared. Two distinct examples are:

**Directional utility:** Does moving from $A$ to $B$ advance a goal? A metric-native candidate from MDI-002 is

$$
C_P^{\mathrm{goal}}(A,B)=\frac{d(A,G_P)-d(B,G_P)}{d(A,B)},\qquad A\ne B,
$$

where $d$ is a metric and $G_P$ a nonempty goal set, with well-defined finite distances. This lies in $[-1,1]$ by the reverse triangle inequality for distance-to-set. At $A=B$, the operator must return a separately defined neutral/undefined status rather than divide by zero.

**Directional agreement:** Do $A$ and $B$ express similar perspective-conditioned orientation? If $c_P(A),c_P(B)\in[-1,1]$, a possible agreement score is

$$
S_P^{\mathrm{agree}}(A,B)=1-\frac{|c_P(A)-c_P(B)|}{2}\in[0,1].
$$

These answer different questions. A favorable transition is not necessarily a similar structure. An application must choose the intended semantics before combination with $S_M$.

Reliability $R$, confidence $K$, and evidence support are separate from the signed directional score; they should not be conflated.

## 5. Three Candidate Scoring Compositions

Let $s=S_M(A,B)\in[0,1]$, and let $p\in[0,1]$ be a properly interpreted and normalized directional score (for example $p=(1+C_P)/2$). These are not automatically comparable probabilities. Combining them requires calibration and semantic compatibility.

### 5.1 Operator A: Convex mixture

$$
S_A=(1-\lambda)s+\lambda p,\qquad \lambda\in[0,1].
$$

**Properties:** $S_A\in[0,1]$; simple, interpretable, and monotone in each input for fixed $\lambda$. If $\lambda=0$, the baseline is recovered.

**Risk:** A neutral or weak directional signal can dilute a strong baseline, and a missing signal must not be replaced by an arbitrary $p=0.5$ while keeping $\lambda>0$. Set $\lambda=0$ when the channel is unavailable. This operator is best suited to calibrated channels that represent commensurate judgments.

### 5.2 Operator B: Bounded additive residual correction

Let $c\in[-1,1]$ be a signed residual effect and $g\in[0,1]$ a governance gate:

$$
S_B=mathrm{clip}_{[0,1]}\left(s+\eta g c\right),\qquad \eta\geq0.
$$

**Properties:** baseline preservation at $g=0$ or $c=0$; explicit residual semantics; easily ablated.

**Risks:** clipping destroys magnitude information near boundaries, can reduce ranking resolution, and may conceal poor calibration. The $\eta$ scale is not automatically portable across tasks. For similarity applications, $c$ must express an *incremental similarity correction*, not an unrelated action utility.

### 5.3 Operator C: Log-odds residual correction

For $s\in(0,1)$, define

$$
S_C=\sigma\!\left(mathrm{logit}(s)+\eta g c\right),
\quad \sigma(z)=\frac{1}{1+e^{-z}}.
$$

This preserves the open interval and supports additive residual effects in log-odds space. It is useful only when a log-odds interpretation is defensible or explicitly adopted as a score transform. A generic similarity score is **not necessarily a probability**. Numerical implementations should clamp the logit input to $[\epsilon,1-\epsilon]$ and document the consequences for exact baseline preservation at endpoints.

### 5.4 Comparison

| Criterion | Convex mixture | Additive residual | Log-odds residual |
|---|---|---|---|
| Output bounded | Yes | Yes, by clipping | Yes, for finite inputs |
| Baseline preserved when channel absent | Yes, $\lambda=0$ | Yes, $g=0$ | Yes in interior, $g=0$ |
| Natural interpretation | Two-channel combination | Incremental correction | Log-odds shift |
| Main risk | Dilution | Saturation | Misleading probability semantics |
| Calibration need | High | High | High |

No operator is universally preferred. Selection is a benchmarked design choice, not a theoretical conclusion.

## 6. Governance Gate and Missingness

A useful decomposition is

$$
g=g_{\mathrm{available}}\,g_{\mathrm{admissible}}\,g_{\mathrm{reliable}}\,g_{\mathrm{context}},
$$

with factors in $[0,1]$. This product is a **policy heuristic**, not a theorem about probabilistic confidence. If any hard condition fails, the extension returns the baseline score and an explicit reason code.

Recommended states:

- `AVAILABLE`: directional channel evaluated under valid contracts;
- `UNAVAILABLE`: no admissible residual evidence or unsupported perspective;
- `ABSTAINED`: evidence exists but governance or calibration rejects its use;
- `CONFLICTED`: material counter-evidence or incompatible perspectives require escalation;
- `ERROR`: computation or contract failure, handled without silent substitution.

A missing directional result is distinct from an observed neutral result.

## 7. MET Adapter Architecture

The integration is designed as an **optional scoring adapter** rather than a replacement for MET's established evaluator:

```text
(A, B, Context)
       |
       v
[Baseline MET Matching Evaluator] ---> S_M + matching evidence ledger
       |
       v
[Evidence Attribution / OTHERS Residual Filter]
       |
       v
[Perspective Contract + Directional Operator]
       |
       v
[Provenance / Counter-Evidence / Reliability Governance]
       |
       v
[Selected Composition Operator] ---> S_I + diagnostics
       |
       v
[Decision / Ranking / Relay / Validation]
```

The baseline result must remain independently accessible, even when a composed score is returned. No execution graph, API shape, or specific MET implementation is presumed here.

### 7.1 Candidate abstract contract

**Input**

```text
DirectionalScoringRequest:
  subject_A, candidate_B
  baseline_score_and_semantics
  perspective_specification
  metric_or_structural_relation_specification
  evidence_items_with_lineage
  governance_policy
  operator_and_version
```

**Output**

```text
DirectionalScoringResult:
  baseline_score
  directional_signal: optional
  composed_score
  score_semantics
  availability_status
  calibration_scope
  attribution_ledger
  support_and_counter_evidence
  reliability_assessment
  uncertainty_assessment
  fallback_reason: optional
  operator_version
```

This is a conceptual specification, not executable code or a committed wire schema. Exact serialization and field typing belong in a later conformance specification.

### 7.2 Separation of responsibilities

- **Baseline evaluator:** established matching features and score.
- **Residual allocator:** evidence coverage and overlap governance.
- **Perspective resolver:** goal, subject, temporal scope, and constraints.
- **Directional evaluator:** Euclidean, metric-native, or structural relation.
- **Evidence governor:** source provenance, reliability, counter-evidence, and admissibility.
- **Composer:** selected, calibrated scoring operator.
- **Relay recorder:** versioned trace for re-evaluation and structural learning.

## 8. Perspective-Specific Semantics and Asymmetry

When $P$ denotes a goal-directed transition, typically

$$
C_P(A,B)\ne C_P(B,A).
$$

In the metric-native goal-potential example, $C_P(B,A)=-C_P(A,B)$ for distinct points. This directional antisymmetry is often useful for action evaluation but incompatible with treating the raw transition signal as symmetric similarity.

Therefore each output must declare whether it represents:

1. symmetric or approximately symmetric similarity;
2. directional transition utility;
3. preference-conditioned candidate ranking;
4. a general bounded evaluation score.

The convenience transformation $D_I=1-S_I$ yields a bounded *distance score* if $S_I\in[0,1]$. It does **not** establish identity of indiscernibles, symmetry, or the triangle inequality. Metric properties require separate proofs and tests for a specific operator.

## 9. Multi-Perspective and Competitive Contexts

Suppose $P_1,\ldots,P_k$ represent distinct stakeholders or objectives. A simple weighted combination

$$
C_{\mathrm{ensemble}}=\sum_{j=1}^k\omega_j C_{P_j},\quad \omega_j\geq0,\quad\sum_j\omega_j=1
$$

is bounded if each signal is bounded. However, boundedness does not imply fairness, legitimacy, or compatibility among perspectives.

A governance-aware system should distinguish:

- nonnegotiable safety and authorization constraints;
- subject ownership and perspective provenance;
- aggregation weights and who selected them;
- conflicts that must be exposed rather than averaged away;
- competitive contexts in which another agent's utility is not the subject's utility.

In high-conflict cases, return a vector of perspective-specific scores and a conflict flag rather than a deceptively precise scalar.

## 10. Calibration, Uncertainty, and Anti-Goodhart Controls

Three distinct questions must be evaluated:

**Score calibration:** Does a score or score band correspond to the target empirical outcome in its declared task? For ordinary similarity, calibration may mean alignment with human judgments or task-specific downstream performance, not probability calibration.

**Reliability:** How trustworthy is the directional evidence source or hypothesis in the current context? Source reliability must be conditioned on domain, time, and selection effects.

**Uncertainty:** How much is unknown because of missing observations, out-of-distribution states, ambiguous perspective, or model disagreement?

A single confidence scalar cannot necessarily represent all three. The adapter should expose them separately where available, and explicitly state when they have not been estimated.

Controls should include random-perspective baselines, held-out tasks, evidence lineage checks, perturbation tests, source-correlation checks, counter-evidence injection, and score saturation audits. Governance thresholds must be chosen without peeking at test labels.

## 11. Residual-to-Feature Promotion

OTHERS is not intended as a permanent bucket of unexamined signals. A candidate signal may advance through:

```text
Observed residual signal
  -> provisional evidence item
  -> directional hypothesis
  -> repeated validation / counter-evidence
  -> stable feature candidate
  -> reviewed matching-feature promotion
  -> revised coverage and attribution ledger
```

Promotion must trigger recalculation of $r_i$ and residual weights; otherwise the same signal can be counted in both the new matching feature and the old OTHERS channel. Feature retirement or demotion must also be possible when evidence weakens.

This mechanism connects BM-ODWEI to residual-driven structural growth and structural relay without presuming that every residual deserves a permanent feature.

## 12. Conformance Requirements

The following are proposed normative requirements for an implementation claiming compatibility with this extension:

- **MDI-MET-001:** Preserve the baseline score and evaluator identity in every result.
- **MDI-MET-002:** Declare the semantics and range of every directional score.
- **MDI-MET-003:** Distinguish missing directional evidence from observed neutral evidence.
- **MDI-MET-004:** Return the baseline when the extension is unavailable or disallowed.
- **MDI-MET-005:** Track residual evidence provenance and matching overlap estimates.
- **MDI-MET-006:** Expose the chosen composition operator and parameter version.
- **MDI-MET-007:** Enforce the output range promised by that operator.
- **MDI-MET-008:** Keep reliability, uncertainty, and directional effect conceptually separate.
- **MDI-MET-009:** Record material counter-evidence and conflicting perspectives.
- **MDI-MET-010:** Do not label $1-S_I$ a mathematical metric without proof.
- **MDI-MET-011:** Ensure feature promotion updates residual attribution.
- **MDI-MET-012:** Provide reproducible fallback and abstention reason codes.
- **MDI-MET-013:** Evaluate out-of-domain and correlated-evidence failure modes.
- **MDI-MET-014:** Do not use directional utility as similarity without an explicit task mapping.

Conformance to this contract establishes interface and governance behavior, **not** empirical accuracy.

## 13. Worked Conceptual Cases

### 13.1 Candidate ranking toward a target

An agent compares two prospective states relative to a goal. Matching similarity may favor the state resembling the present configuration, while metric-native directionality favors the state closer to the goal. The system must decide whether it is scoring *similarity to the present state* or *progress toward the goal*. Combining the two without specifying this distinction is a category error. A multi-objective decision score may be legitimate, but it must be named accordingly.

### 13.2 Structural analogy with unmodeled signals

Two structural descriptions share few known matching attributes but show similar perspective-conditioned functional behavior. OTHERS may carry provisional directional agreement evidence. The residual allocator must discount evidence already implied by matched features, and the evaluator must test whether the additional channel improves held-out analogy judgments.

### 13.3 Reputationally weak evidence

A candidate signal comes from a historically unreliable source. The directional effect may be large while admissibility or reliability is low. A governance gate can reduce or reject the contribution. This does not mean the signal itself is geometrically small; it means the system has insufficient grounds to rely on it.

### 13.4 Contradictory perspectives

A move is beneficial under $P_1$ and harmful under $P_2$. A single average score may obscure a critical constraint. The adapter should preserve the score vector and, when warranted, abstain from scalar composition.

## 14. Evaluation Plan and Falsifiable Hypotheses

**H1 — Residual value:** On held-out tasks, properly attributed OTHERS evidence improves the designated task metric over matching-only scoring.

**H2 — Overlap control:** Coverage-aware allocation reduces false gains caused by duplicate evidence relative to naive fusion.

**H3 — Baseline stability:** With unavailable or rejected directional evidence, the adapter reproduces baseline output exactly within the declared numerical contract.

**H4 — Representation choice:** Metric-native operators outperform Euclidean embeddings on at least some non-Euclidean or structurally constrained tasks; the reverse may hold elsewhere.

**H5 — Calibration:** Explicitly calibrated composition generalizes better than fixed unvalidated weights across shifted contexts.

**H6 — Counter-evidence:** Provenance and counter-evidence governance reduce failures from unreliable or adversarial signals.

Recommended experimental arms: matching-only; naive convex mixture; residual correction without overlap control; residual correction with overlap control; metric-native directional operator; random-perspective negative control; and governance-enabled variants. Use the same datasets and predeclared metrics for fair comparisons.

Metrics should include primary task quality, calibration where meaningful, ranking stability, abstention quality, latency, compute budget, source sensitivity, and evidence duplication rate. Statistical uncertainty and negative results should be reported.

## 15. Failure Modes and Research Boundaries

1. **Evidence leakage:** Residual features inadvertently encode target labels or matching outputs.
2. **Correlation masquerading as independence:** Multiple signals share one underlying source.
3. **Semantic mismatch:** Action utility is combined with similarity without a justified mapping.
4. **Perspective drift:** A goal changes while cached scores remain active.
5. **Uncalibrated reputation:** Past reliability does not transfer to new contexts.
6. **Score saturation:** Clipping hides important differences between candidates.
7. **Spurious directionality:** Random or arbitrary perspectives appear predictive due to selection bias.
8. **Unstable feature promotion:** A newly formalized feature is double-counted or overfit.
9. **Biomimetic overinterpretation:** An engineering heuristic is described as an established neural mechanism.
10. **Metric overclaim:** A bounded dissimilarity score is incorrectly called a distance metric.

The research program should preserve explicit unresolved residuals rather than force all evidence into existing features or produce unwarranted certainty.

## 16. Relationship to Adjacent MDI Documents

- **MDI-001 — Problem Definition and Research Boundaries:** establishes the general problem, terminology, and claim boundaries.
- **MDI-002 — Euclidean and Metric-Native Directional Scoring:** develops candidate directional operators and their mathematical properties.
- **MDI-003 — Perspective Fields and Pre-Decisional Guidance:** extends directional intelligence from evaluation to candidate generation and exploration.
- **MDI-005 — Lightweight Hypothesis Testing and Reputation:** will elaborate evidence tests, source/hypothesis reliability, and small-budget evaluation.
- **MDI-006 — Evidence Relay, Validation and Structural Growth:** will specify broader validation and the relay/promotion lifecycle.

Within the parent repository, this extension complements **BM-002** (OTHERS), **BM-003** (Directional Measurement Sails), **BM-004** (Reputational Intelligence), **BM-006** (Structural Growth), **BM-007** (Evidence Governance), and **BM-008** (Unified Architecture), without replacing their original claims.

## 17. Open Research Questions

1. Can matching coverage $r_i$ be estimated robustly when feature dependencies are learned and opaque?
2. Which composition operator best preserves ranking under distribution shift?
3. When does residual directional evidence add genuine information rather than repackaging matching evidence?
4. How should nontransitive structural directional relations be aggregated?
5. Can task-specific calibration remain stable when perspectives change dynamically?
6. What minimal evidence trace is sufficient for third-party conformance and relay?
7. When should the system abstain rather than output a scalar score?
8. How can validated residuals become matching features without losing their historical provenance?
9. Can low-cost hypothesis tests reduce the compute needed for reliable directional scoring?
10. Which aspects of the architecture, if any, correspond to experimentally supported biological mechanisms?

## 18. Conclusion

OTHERS residual scoring is best treated as a **governed extension of an existing evaluator**, not as an unrestricted bonus added to matching. The architecture proposed here preserves baseline semantics, assigns evidence lineage, separates directional effects from confidence, and makes composition operators explicit and testable. Its most important invariant is simple: **when the directional channel cannot justify its contribution, the system must be able to fall back to the baseline without hiding what was missing or rejected.**

The larger research opportunity is an evolvable scoring system in which weak directional evidence is tested, relayed, challenged, and—when warranted—promoted into new structural capabilities. Whether that opportunity delivers measurable gains remains an empirical question.

---

### Citation and release note

This is a proposed research-extension manuscript for the BM-ODWEI repository. It is not itself evidence of a registered DOI or a published release. Repository-level citation metadata and version identifiers should be verified at release time.
