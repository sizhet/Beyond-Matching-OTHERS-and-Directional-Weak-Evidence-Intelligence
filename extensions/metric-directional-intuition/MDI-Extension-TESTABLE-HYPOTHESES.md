# Testable Hypotheses — Metric-Directional Intuition (MDI)

**Research extension:** `extensions/metric-directional-intuition/`  
**Parent project:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Status:** Theory-first research agenda; proposed hypotheses, not empirical findings  
**Version target:** BM-ODWEI v1.1.0 (proposed)  
**Scope:** MDI-001 through MDI-006

## 1. Purpose and evidential discipline

This document translates the MDI research program into falsifiable claims, controlled comparisons, measurement protocols, and explicit failure criteria. It distinguishes mathematical propositions, which require proof or counterexample, from empirical hypotheses, which require data. None of the proposed benefits is asserted to have been demonstrated.

The central research question is whether *perspective-conditioned directional evidence*, especially evidence outside an existing matching representation, improves similarity estimation, candidate discovery, and adaptive decision support under realistic compute and evidence constraints.

A successful experiment must report not only performance gains but also the provenance of evidence, the definition of the perspective, the budget consumed, and the cost of erroneous directional guidance.

## 2. Formal experimental vocabulary

Let $(\mathcal X,d)$ be a metric space, $P$ a perspective, $A,B\in\mathcal X$ or structures represented in $\mathcal X$, and $E$ the admissible evidence. Let

$$
S_M(A,B)\in[0,1]
$$

be the established matching baseline. A candidate MDI operator returns a bounded score and its evidential metadata:

$$
\mathsf{DirectionalScore}(A,B,P,E)
\longrightarrow (s_P,c_P,\pi_P),
$$

where $s_P\in[-1,1]$ or a declared normalized equivalent, $c_P$ is a separately defined confidence/calibration quantity, and $\pi_P$ records provenance and assumptions. Do **not** silently interpret $c_P$ as both the probability of a hypothesis and the reliability of its evidence source.

For a nonempty goal set $G_P\subseteq\mathcal X$, define $V_P(x)=d(x,G_P)$. For $x\ne y$, the metric-native directional difference is

$$
C_P(x,y)=\frac{V_P(x)-V_P(y)}{d(x,y)}.
$$

The distance-to-set function is 1-Lipschitz, so $|C_P(x,y)|\le 1$. This is a mathematical result under the stated assumptions, **not** an empirical hypothesis. The zero-distance case requires an explicit undefined/abstain policy or a separately justified convention. The existence of a metric alone does not specify $G_P$, a preference, or a direction.

When similarity is defined by $S_I\in[0,1]$, $D_I=1-S_I$ is a bounded *distance score*, not necessarily a metric: symmetry and the triangle inequality require separate demonstration.

## 3. Experimental baselines and controlled variants

Use matched train/test partitions, identical candidate pools where applicable, fixed data-access policies, and comparable compute or latency budgets.

| ID | Variant | Description | Primary role |
|---|---|---|---|
| B0 | Matching-only | Existing $S_M$, no directional channel | Primary baseline |
| B1 | Euclidean single sail | One normalized cosine perspective | Simple directional baseline |
| B2 | Euclidean field/ensemble | Weighted sails or local vector field | Representation ablation |
| B3 | Metric-native potential | Goal-set distance-change score | Non-Euclidean candidate |
| B4 | Learned structural relation | Pairwise $\Phi_P(x,y)$, not necessarily potential-derived | Expressivity control |
| B5 | Residual-gated MDI | OTHERS-only evidence and explicit fallback | Evidence-governance test |
| B6 | Hypothesis-guided MDI | Limited hypotheses, targeted tests, reputation | Compute-efficiency test |
| B7 | Full relay/growth pipeline | Governed evidence transfer and feature promotion | Longitudinal test |
| C1 | Random perspective | Randomized or shuffled $P$ with matched complexity | Negative control |
| C2 | Wrong perspective | Plausible but task-inappropriate $P$ | Specificity control |
| C3 | Evidence duplication | Replayed/correlated evidence with known ancestry | Leakage/robustness control |
| C4 | Equal-budget search | Random, heuristic, or exhaustive candidate generation under budget | Selection-value control |

A comparison of B3 with B1 must not conflate representational advantage with better access to task information. Where possible, provide the same goal information and measure distortion introduced by embedding separately.

## 4. Registered empirical hypotheses

### H-MDI-001 — Perspective specificity improves task-relevant ranking

**Claim.** On tasks with a preregistered, externally meaningful perspective, an appropriately conditioned directional model improves ranking quality over B0 and over C1/C2.

**Manipulation.** Hold structures and matching features fixed; vary only perspective specification and directional scoring.

**Outcomes.** NDCG@k, MAP, pairwise preference accuracy, and calibration of any claimed uncertainty.

**Disconfirmation.** No reproducible improvement over B0, or improvement equally present under shuffled/wrong perspectives.

**Controls.** Blind perspective assignment, held-out tasks, and no labels leaking into the perspective representation.

### H-MDI-002 — Metric-native scoring is advantageous when Euclidean embedding distorts relevant structure

**Claim.** For selected non-Euclidean tasks, B3 preserves useful directional orderings better than B1/B2 at matched information and compute budgets.

**Manipulation.** Vary metric-space geometry and embedding distortion while holding goal semantics constant.

**Outcomes.** Ranking agreement with task-grounded transition quality, regret, embedding distortion, and runtime.

**Disconfirmation.** No benefit after controlling for embedding quality and information availability; systematic failure under sparse goals or noisy metrics.

**Boundary.** The mathematical bound on $C_P$ does not imply predictive utility. Report sensitivity to goal-set choice.

### H-MDI-003 — Pre-decisional directional guidance improves candidate discovery

**Claim.** Directional guidance applied *before* candidate generation increases the discovery rate of high-value candidates relative to post-generation scoring alone.

**Manipulation.** Compare guide→generate→evaluate against generate→evaluate with the same generation budget and evaluator.

**Outcomes.** Best-found utility, recall of valuable candidates, diversity, coverage, and time-to-first-useful-candidate.

**Disconfirmation.** Guidance merely changes final rankings, reduces exploration diversity, or misses important off-direction solutions.

**Safeguard.** Include exploration quotas and adversarial/off-perspective cases.

### H-MDI-004 — OTHERS-only attribution reduces double counting

**Claim.** Explicit residual attribution reduces score inflation and overconfidence from evidence already represented by matching features.

**Manipulation.** Compare naive fusion, convex mixing, additive residual correction, and evidence-ledger-gated correction.

**Outcomes.** Duplicate sensitivity, calibration error, Brier score, false-positive rate, and ranking stability.

**Disconfirmation.** Ledger gating does not improve duplicate robustness or sacrifices more task utility than it preserves.

**Boundary.** Attribution estimates may be uncertain; report errors in coverage estimates and cross-channel dependence.

### H-MDI-005 — Optional directional adapters preserve baseline behavior under missing evidence

**Claim.** A governed MDI adapter can return the exact baseline result when directional evidence is absent, rejected, or out of contract.

**Manipulation.** Inject missing fields, unsupported metrics, undefined goal sets, zero-distance transitions, and invalid provenance.

**Outcomes.** Exact fallback equality, error reporting, abstention correctness, and operational overhead.

**Disconfirmation.** Silent score changes, fabricated confidence, crashes, or unsafe continuation.

**Note.** This is primarily a *conformance requirement* rather than a claim of superior intelligence; it can be tested deterministically.

### H-MDI-006 — Lightweight hypothesis testing improves decision value per unit cost

**Claim.** A small, selectively tested hypothesis portfolio achieves higher expected decision utility per unit computation than equal-budget unguided testing.

**Manipulation.** Limit hypothesis count and test budget; compare random tests, entropy-driven information gain, expected value of information (EVI), and exhaustive search where feasible.

**Outcomes.** Realized utility, regret, compute/tokens, latency, evidence acquisition cost, and sensitivity to prior misspecification.

**Disconfirmation.** EVI selection fails under calibrated models or its model-estimation cost eliminates any net benefit.

**Important distinction.** Entropy reduction is not equivalent to decision value; predefine the downstream decision loss.

### H-MDI-007 — Reputation-aware evidence selection improves robustness under heterogeneous reliability

**Claim.** Context-conditioned source/hypothesis reputation improves prediction or decision calibration relative to uniform evidence weighting when source reliability differs.

**Manipulation.** Vary source error rates, correlation, drift, and adversarial manipulation; compare unweighted evidence, simple Beta–Bernoulli updating, and context-aware alternatives.

**Outcomes.** Log loss, Brier score, calibration curves, decision regret, recovery after drift, and manipulation susceptibility.

**Disconfirmation.** Reputation worsens calibration or amplifies correlated misinformation and historical bias.

**Boundary.** Beta–Bernoulli updating assumes a specified Bernoulli event model; it is not a general-purpose proof of truth or a model of biological neural implementation.

### H-MDI-008 — Counter-evidence governance improves error recovery

**Claim.** Explicit counter-evidence records and revision triggers reduce the persistence of false directional claims.

**Manipulation.** Introduce contradicting observations at controlled times and compare immutable-score, recency-only, and provenance-aware revision policies.

**Outcomes.** Time-to-correction, residual error, audit completeness, and false reversal rate.

**Disconfirmation.** Governance adds overhead without improving recovery or causes excessive oscillation.

### H-MDI-009 — Evidence relay transfers useful information without treating repetition as independence

**Claim.** Provenance-aware relay improves cross-agent or cross-context performance while avoiding confidence inflation from repeated copies of one observation.

**Manipulation.** Compare raw copied evidence, deduplicated evidence, and structured relay packets carrying origin, dependencies, metric/perspective contracts, and counter-evidence.

**Outcomes.** Transfer gain, effective sample-size estimation, duplicate-induced confidence inflation, and interoperability failure rate.

**Disconfirmation.** Structured relay yields no gain or fails to preserve necessary context; duplicates still appear as independent confirmation.

**Interpretation.** Repeated execution may accumulate observations, but independence is an additional property to be established.

### H-MDI-010 — Validated OTHERS evidence can become reusable matching capability

**Claim.** A controlled residual-to-feature promotion pipeline produces transferable matching features with lower future evidence-acquisition cost than leaving all signals in the residual channel.

**Manipulation.** Compare no promotion, naive promotion, and promotion conditioned on held-out validation, calibration, provenance, and rollback criteria.

**Outcomes.** Held-out generalization, future matching quality, evidence cost, feature stability, and rollback frequency.

**Disconfirmation.** Promotion mainly overfits or shifts errors from the residual channel into baseline matching.

**Safeguard.** Evaluate on fresh subjects, contexts, and time periods; do not reuse promotion evidence as independent validation.

### H-MDI-011 — Perspective conflict governance improves safety and controllability

**Claim.** Explicit constraints and perspective arbitration reduce unacceptable recommendations compared with unconstrained scalar aggregation.

**Manipulation.** Construct conflicting goal/risk perspectives; compare weighted scalarization, lexicographic constraints, and abstention/escalation policies.

**Outcomes.** Constraint-violation rate, feasible utility, Pareto coverage, and abstention precision.

**Disconfirmation.** Arbitration produces no safety benefit or excessive loss of feasible alternatives.

### H-MDI-012 — Biomimetic directional hypotheses are behaviorally useful, not necessarily biologically literal

**Claim.** Under sparse observations and tight time budgets, compact directional-hypothesis models can reproduce selected *behavioral patterns* of adaptive navigation or threat discrimination more efficiently than selected unguided baselines.

**Manipulation.** Use simulated agents with partial observability, shifting hazards, and bounded memory; compare matched-compute policies.

**Outcomes.** Survival/task reward, sample efficiency, response latency, generalization, and behavioral fit to preregistered reference patterns where data exist.

**Disconfirmation.** No robust behavioral fit or advantage; simpler non-directional mechanisms explain the same observations.

**Boundary.** Behavioral resemblance does not establish that animals use the proposed metric, potential, Bayesian update, or algorithm.

## 5. Mathematical propositions and counterexample obligations

The following should not be counted as experimentally validated discoveries merely because a test passes:

- **P-MDI-001 (proved under assumptions):** For nonempty $G_P$ in a metric space, $V_P(x)=d(x,G_P)$ is 1-Lipschitz and $|C_P(x,y)|\le1$ for $x\ne y$.
- **P-MDI-002 (local relation, conditional):** In a differentiable Euclidean setting, the directional difference has the first-order approximation $-\nabla V_P(x)\cdot u$ for unit direction $u$. This is not automatically a cosine unless the gradient is normalized and nonzero.
- **P-MDI-003 (requires counterexample/qualification):** $D_I=1-S_I$ need not be a metric; construct explicit failures of symmetry or triangle inequality for proposed variants.
- **P-MDI-004 (contractual):** A residual adapter with a zero/invalid evidence gate must recover $S_M$ exactly if specified to do so.
- **P-MDI-005 (not generally true):** A pairwise structural preference relation need not be representable by one global potential; test cyclic preferences and nonconservative relations.

## 6. Shared measurement protocol

### 6.1 Preregistration

Before accessing held-out outcomes, record task definition, perspective semantics, metric/goal-set selection, baseline configuration, evidence admissibility, compute budget, primary endpoint, minimum meaningful effect, and failure thresholds. Label exploratory analyses separately.

### 6.2 Data partitioning and independence

Partition by entity, source lineage, context, and time where appropriate. Keep evidence used to construct a feature, tune a perspective, or assign reputation out of independent validation. Log correlated observations and relay ancestry.

### 6.3 Statistical analysis

Report effect sizes with confidence intervals or posterior intervals, task-level variation, paired comparisons, and sensitivity analyses. Account for multiple comparisons across the hypothesis family. Do not interpret a nonsignificant result as proof of equivalence; use an equivalence margin when that is the actual question.

### 6.4 Resource accounting

Count model inference, embedding, metric evaluation, hypothesis generation, evidence acquisition, governance, and relay serialization. Report quality–cost Pareto curves rather than accuracy alone.

### 6.5 Calibration and risk

When a score is interpreted probabilistically, test calibration using a stated event definition. For nonprobabilistic directional scores, avoid probability language. Record false confidence, missed candidates, constraint violations, and recovery from drift.

## 7. Conformance test matrix

| ID | Required property | Example test | Pass condition |
|---|---|---|---|
| CT-01 | Range declaration | Extreme vectors and goals | Output within declared range |
| CT-02 | Undefined-case policy | $x=y$, empty goal set | Explicit abstain/error/convention |
| CT-03 | Metric contract | Nonmetric dissimilarity input | Reject or clearly relabel |
| CT-04 | Perspective provenance | Missing/changed $P$ | Detect and record |
| CT-05 | Baseline fallback | Missing directional evidence | Exact $S_M$ when required |
| CT-06 | Attribution integrity | Duplicate matching evidence | No unlogged double count |
| CT-07 | Source independence | Copied relay packets | No false independent confirmations |
| CT-08 | Reputation semantics | Change event definition | Reject incompatible update |
| CT-09 | Counter-evidence | Contradictory new observation | Revision/audit path available |
| CT-10 | Hard constraints | Attractive unsafe candidate | Constraint policy enforced |
| CT-11 | Relay interoperability | Unknown metric/perspective version | Explicit compatibility outcome |
| CT-12 | Feature promotion | Reused training evidence | Independent-validation gate fails |

## 8. Staged experimental program

**Stage A — Mathematical and interface verification.** Formalize score domains, prove boundedness, construct nonmetric counterexamples, and implement deterministic contract tests. Focus: P-MDI-001–005, CT-01–05.

**Stage B — Controlled directional scoring.** Synthetic metric spaces and known perspectives; evaluate H-MDI-001/002 and randomized controls. Include cases where the direction is misleading.

**Stage C — Candidate discovery and residual governance.** Evaluate H-MDI-003/004/005/011 with fixed budgets and audited evidence channels.

**Stage D — Bounded hypothesis and reputation experiments.** Evaluate H-MDI-006/007/008/012 with partial observability, correlated evidence, drift, and adversarial sources.

**Stage E — Relay and longitudinal structural growth.** Evaluate H-MDI-009/010 across contexts, agents, and time; preserve immutable lineage and independent holdouts.

Advancement to a later stage does not imply prior claims are proven; unresolved failures must be carried forward as explicit residuals.

## 9. Reporting template for each hypothesis

Use this minimal record in future experiments:

```text
Hypothesis ID:
Task and data version:
Perspective and metric contract:
Primary outcome and meaningful-effect threshold:
Baselines and negative controls:
Compute/evidence budget:
Evidence lineage and exclusion rules:
Sample size and uncertainty method:
Result (effect, interval, cost):
Counter-evidence and failure cases:
Decision (supported / not supported / inconclusive):
Reproducibility artifacts:
Next relay question:
```

The label **supported** means supported under the tested conditions, never universally established.

## 10. Research dependencies and reading map

| Hypothesis group | Primary paper | Supporting paper |
|---|---|---|
| H-001, H-002 | [MDI-002](docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md) | [MDI-001](docs/MDI-001-Problem-Definition-and-Research-Boundaries.md) |
| H-003, H-011 | [MDI-003](docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md) | [MDI-002](docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md) |
| H-004, H-005 | [MDI-004](docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md) | [MDI-001](docs/MDI-001-Problem-Definition-and-Research-Boundaries.md) |
| H-006, H-007, H-012 | [MDI-005](docs/MDI-005-Lightweight-Hypothesis-Testing-and-Reputation.md) | [MDI-003](docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md) |
| H-008, H-009, H-010 | [MDI-006](docs/MDI-006-Evidence-Relay-Validation-and-Structural-Growth.md) | [MDI-004](docs/MDI-004-OTHERS-Residual-Scoring-and-MET-Integration.md) |

See also [MDI-Extension-OPEN-QUESTIONS.md](MDI-Extension-OPEN-QUESTIONS.md), [MDI-Extension-VALIDATION-ROADMAP.md](MDI-Extension-VALIDATION-ROADMAP.md), and the extension [MDI-Extension-README.md](MDI-Extension-README.md).

## 11. Publication and scope boundaries

This file is a research extension to BM-ODWEI and does not revise the historical claims of BM-001–008. It proposes no biological proof, no deployed MET implementation, and no measured superiority. Conformance precedes runtime deployment; evidence provenance and counter-evidence are first-class outputs. New findings should be recorded with versioned datasets, methods, negative results, and explicit limitations.

---

**Working principle:** *A directional intuition mechanism is scientifically valuable only to the extent that its assumptions, benefits, failure modes, and evidence dependencies can be independently tested.*
