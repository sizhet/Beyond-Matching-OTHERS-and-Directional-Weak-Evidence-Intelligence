# Glossary — Metric-Directional Intuition (MDI) Research Extension

**Repository:** Beyond Matching: OTHERS and Directional Weak-Evidence Intelligence (BM-ODWEI)  
**Extension path:** `extensions/metric-directional-intuition/`  
**Status:** Research vocabulary and candidate contracts; not an assertion of empirical validation  
**Companion papers:** MDI-001–MDI-006

## 1. Purpose and interpretation

This glossary establishes a stable vocabulary for the Metric-Directional Intuition (MDI) extension. It distinguishes (i) mathematical objects and proven properties, (ii) proposed scoring and engineering mechanisms, and (iii) biological or cognitive hypotheses requiring empirical testing. The original BM-001–BM-008 definitions remain authoritative for the parent research program; the definitions here are narrower, operational extensions, not retroactive replacements.

**Notation convention.** A *score* is an application-defined quantity; a *metric* is a mathematical distance satisfying nonnegativity, identity of indiscernibles, symmetry, and the triangle inequality. The term *metric-native* means operating directly with metric-space distances rather than requiring an explicitly chosen Euclidean embedding.

## 2. Foundational terms

### Matching / Matching Score
A baseline assessment of correspondence between recognized features, components, or structures. `S_M(A,B) ∈ [0,1]` denotes a normalized matching similarity when the implementation contract guarantees that range. Matching alone need not capture directional relevance, weak evidence, or unrecognized features.

### OTHERS / Open Evidence Space
A designated space for signals, discrepancies, relationships, or evidence not adequately represented by the current matching schema. OTHERS is not a synonym for noise, nor is it automatically valid evidence. Signals must retain provenance, uncertainty, and counter-evidence.

### Perspective (`P`)
An explicit evaluative standpoint: a goal, task, preference, risk posture, observer, context, or structured combination thereof. Perspective affects the meaning of directional relevance. It must not be silently conflated with a metric, an evidence source, or a decision policy.

### Perspective-Conditioned Intuitive Similarity (`S_I`)
A candidate normalized score combining baseline correspondence with admissible directional information under perspective `P`. A reference form is

`S_I(A,B | P) = (1 − λ) S_M(A,B) + λ S_P(A,B | P)`, with `0 ≤ λ ≤ 1`, provided both component scores lie in `[0,1]`. This is one operator family, not a universal definition of intuition.

### Intuitive Distance Score (`D_I`)
A complementary score `D_I = 1 − S_I` when `S_I ∈ [0,1]`. **This expression is not generally a mathematical metric**: it may be asymmetric, have nonzero self-distance, or violate the triangle inequality.

### Directional Utility
The degree to which a candidate transition or object advances a specified goal or perspective. It is distinct from similarity between two candidates.

### Directional Agreement
The degree to which two objects or transitions have comparable directional orientation under a common perspective. A candidate agreement score can be constructed from the difference of their directional contributions; this must not be substituted for directional utility without a declared contract.

### Directional Measurement Sail
A BM-ODWEI metaphor and candidate operator for capturing weak, perspective-sensitive directional signals that ordinary matching may miss. A sail can be implemented with vectors, metric-native progress, or more general structural relations; it is not necessarily a physical or Euclidean vector.

### Structural Intuition
An operational research hypothesis: a system's ability to identify and prioritize consequential structural relationships or candidate transitions without exhaustive enumeration. It does not claim a verified account of animal or human intuition.

## 3. Euclidean directional scoring

### Euclidean Embedding
A representation `φ: X → R^n` that makes vector operations available. Its convenience does not establish that the source domain or biological cognition is intrinsically Euclidean. Embedding distortion should be evaluated when it affects scoring.

### Direction Vector / Perspective Vector (`p`)
A nonzero vector representing a chosen directional reference in an embedding space. The interpretation and normalization of `p` must be documented.

### Cosine Directional Score
For nonzero vectors `v` and `p`, `C_cos(v,p) = <v,p> / (||v|| ||p||) ∈ [−1,1]`. Undefined for a zero-norm argument unless a separately specified fallback is applied. A normalized form is `(1 + C_cos)/2`.

### Perspective Ensemble
A finite set of perspective vectors or operators, with explicitly declared weights, contexts, and aggregation rules. If `w_i ≥ 0` and `Σ_i w_i = 1`, a weighted average of scores in `[−1,1]` remains in `[−1,1]`.

### Perspective Field / Directional Field
A state-dependent assignment of directional guidance or evaluation. In Euclidean implementations it may be a vector field `F_P(x,t)`; in metric-native or structural implementations it may instead be a transition scoring relation. The term *field* does not imply a smooth physical vector field.

### Projection Contribution
A scalar contribution obtained by projecting a represented structural component onto a declared perspective direction. Aggregation across components requires coverage and reliability rules to prevent duplicate evidence.

## 4. Metric-native and structural directional scoring

### Metric Space (`X,d`)
A set `X` with distance `d: X × X → [0,∞)` satisfying the four metric axioms. If these axioms are relaxed, the structure must be named accurately (for example, pseudometric or dissimilarity space).

### Goal Set (`G_P`)
A nonempty subset of `X` representing acceptable target states under perspective `P`. A metric alone does not supply a goal: the goal set or other orientation structure is additional information.

### Distance-to-Goal Potential (`V_P`)
`V_P(x) = d(x,G_P) = inf_{g∈G_P} d(x,g)`. For a nonempty goal set, this is 1-Lipschitz: `|V_P(x) − V_P(y)| ≤ d(x,y)`.

### Metric-Native Directional Score (`C_P`)
For `x ≠ y` in a metric space, with nonempty `G_P`,

`C_P(x,y) = [V_P(x) − V_P(y)] / d(x,y)`.

The Lipschitz inequality proves `C_P(x,y) ∈ [−1,1]`. Positive values indicate progress toward `G_P` in distance-to-set terms; negative values indicate regression; zero indicates no change in this potential. The score is undefined at `x = y` without a declared convention. It is generally directional/asymmetric and is **not** itself a metric.

### Metric-Native Directional Difference
The signed change of a perspective-specific potential along a transition, normalized by a declared transition distance. The distance-to-goal formula above is a particularly well-defined instance; arbitrary potentials require a separately established Lipschitz bound or normalization.

### Local Euclidean Correspondence
Where the distance-to-goal potential is differentiable and a displacement is small, metric-native progress approximates the negative directional derivative: `C_P(x,x+Δx) ≈ −∇V_P(x)·Δx/||Δx||`. This is a local correspondence under assumptions, not an equivalence in all spaces.

### Structural Directional Relation (`Φ_P`)
A perspective-conditioned function or relation evaluating ordered transitions `Φ_P(x,y)`. It may be learned or rule-based and need not derive from a global potential; hence it may be cyclic or nontransitive. Its range and semantics must be declared.

### Representation-Agnostic Directional Contract
An interface such as `DirectionalScore(A,B,P,M) → (score, confidence, evidence)` where `M` specifies the representation and metric/operator contract. Confidence and evidence are outputs with separate semantics; they are not guaranteed by a numerical score alone.

### Potential-Based vs Relation-Based Directionality
*Potential-based* directionality evaluates progress through a scalar potential; *relation-based* directionality directly scores ordered pairs and can capture preferences that cannot be represented by one global scalar potential.

## 5. Pre-decisional guidance

### Pre-Decisional Directional Intelligence
A research hypothesis that directional structures can guide attention, candidate generation, or evidence gathering **before** an explicit choice is made. The term does not assert that all organisms or AI systems use the same representation.

### Forward Guidance
Use of prospective directional signals to prioritize search, investigation, or candidate generation. In MDI it is related to, but not identical with, UIERU forward guidance.

### Guide → Generate → Evaluate
A proposed separation of (1) where to search, (2) which candidates to instantiate, and (3) how to assess them. Separating these stages permits tests of whether guidance improves discovery rather than merely reranking a fixed list.

### Candidate Portfolio / Multi-Trail Exploration
A bounded collection of competing options, trajectories, or hypotheses maintained to avoid premature commitment. Portfolio diversity and resource costs must be evaluated independently of directional score.

### Perspective Conflict
A case in which different goals or stakeholders assign incompatible directional preferences. A weighted sum is one possible policy, but safety constraints and subject sovereignty may require noncompensatory governance.

## 6. OTHERS residual integration and MET

### MET
The metric/structural evaluation setting into which MDI candidate operators may be integrated. This glossary does not assume one specific software implementation or that all MET instances expose the same API.

### Matching Coverage (`r_i`)
An estimate, usually in `[0,1]`, of how fully existing matching features already account for an evidence item `i`. Coverage estimates are model-dependent and must be calibrated or audited.

### Residual Evidence Weight
A proposed weight for directional evidence not already credited to matching, for example `q_i(1−r_i)` where `q_i` is an admissibility or quality weight. This is a heuristic allocation rule, not a proof of statistical independence.

### OTHERS-Only Scoring
A policy that credits the directional channel only for evidence allocated to the open/residual space. It aims to reduce double counting but requires traceable feature and evidence attribution.

### Evidence Attribution Ledger
A record identifying which evidence contributed to which score, through which feature, operator, perspective, and version. It supports audits, corrections, and leakage detection.

### Convex Mixture
`S_I = (1−λ)S_M + λS_P`, with `λ∈[0,1]`. It preserves the unit interval when both inputs are bounded, but may lower the baseline score when directional evidence is absent or weak unless a fallback is defined.

### Additive Residual Correction
`S_I = clip_[0,1](S_M + η g_P C_residual)`. The gain `η`, gate `g_P`, and residual correction require explicit calibration. Clipping can hide saturation and should be monitored.

### Log-Odds Residual Correction
A candidate combination in logit space, for example `S_I = σ(logit(S_M) + ηg_PC_residual)`, with appropriate handling of `S_M = 0` or `1`. This is an engineering option, not automatically a calibrated posterior probability.

### Confidence Gate / Admissibility Gate
A rule controlling whether and how strongly an optional directional contribution enters a score. Gate inputs may include evidence quality, applicability, novelty, and risk; they must not silently convert unreliable evidence into certainty.

### Baseline Preservation / Fallback
The contract that an unavailable, rejected, or nonconformant directional channel can return the baseline matching result, with a recorded reason. It prevents optional intuition mechanisms from silently degrading the existing evaluator.

### Residual-to-Feature Promotion
A governed transition by which repeatedly validated OTHERS evidence becomes a recognized matching feature. Promotion requires independent evaluation, provenance, schema change control, and rollback capability.

## 7. Lightweight hypothesis testing and reputation

### Directional Hypothesis (`H`)
A falsifiable proposition about whether a transition, action, or structural relation will advance a declared perspective, under specified conditions.

### Lightweight Hypothesis Testing
Testing a small, prioritized hypothesis portfolio with bounded compute, observations, and decision latency. It is a proposed computational strategy, not a claim that biological brains use a particular statistical algorithm.

### Discriminating Evidence
An observation whose expected distribution differs meaningfully between competing hypotheses. Evidence is useful when it changes a decision or belief, not merely when it confirms a preferred hypothesis.

### Expected Information Gain (EIG)
The expected reduction in uncertainty about a hypothesis or model after a test. It is distinct from the test's value for choosing an action.

### Expected Value of Information (EVI / EVSI)
The expected improvement in achievable decision utility from acquiring information, minus relevant testing cost where explicitly included. It depends on available actions, outcome utilities, and the predictive model; high information gain need not imply high decision value.

### Hypothesis Reputation
A context-indexed record of how reliably a hypothesis or hypothesis-producing mechanism has predicted relevant outcomes. It is not interchangeable with truth probability, source credibility, or the utility of acting on the hypothesis.

### Evidence-Source Reputation
An assessment of an observation source's reliability under declared contexts and error modes. Shared provenance or correlated sources can invalidate naïve independent-evidence aggregation.

### Beta–Bernoulli Reputation Update
For binary outcomes under an exchangeable Bernoulli model with `Beta(α,β)` prior, after `s` successes and `f` failures, the posterior mean is `(α+s)/(α+β+s+f)`. Its validity depends on outcome definitions and model assumptions; it is not a universal reputation formula.

### Bayesian Evidence Update
A revision of probability assignments using a specified likelihood model. Multiplying a directional score by a reliability estimate is only a heuristic unless justified by a complete decision model.

### Counter-Evidence
An observation, test result, or credible argument that weakens or contradicts a hypothesis or directional claim. Counter-evidence must be retained with its context and provenance rather than erased by aggregation.

### Calibration
Agreement between stated confidence/probabilities and observed frequencies under a specified evaluation protocol. Calibration of reliability is separate from directional accuracy and task utility.

### Distribution Shift / Context Drift
A change in operating conditions that may invalidate a learned directional operator, reputation estimate, or evidence source. Drift detection should trigger review, adaptation, or fallback.

## 8. Relay, governance, and structural growth

### Evidence Relay
The transfer of observations, hypotheses, tests, provenance, uncertainty, and counter-evidence between agents, contexts, or time periods for re-evaluation and reuse. Relay is not proof of independent replication.

### Structural Relay
Transfer of a reusable structural object—such as an operator, contract, hypothesis unit, or feature candidate—together with enough context to assess compatibility and validity.

### Hypothesis Unit / Test Unit / Reputation Record / Relay Packet
Candidate portable records for, respectively, a hypothesis and its scope; a test and its procedure; an evidence-backed reliability history; and a package for cross-context transfer. These are proposed contract families, not already standardized interchange formats.

### Repeated-Execution Relay
Accumulation of execution traces and outcomes across repeated runs. Such accumulation can support learning, but repeated observations sharing the same cause or data source are not independent confirmations.

### Provenance
Traceable information about an evidence item's origin, collection conditions, transformations, ownership/authorization where relevant, and subsequent reuse.

### Conformance
Verification that an implementation obeys declared mathematical, semantic, interface, safety, and evidence-accounting contracts. Conformance is a prerequisite for interpreting results, not a substitute for empirical validation.

### Structural Growth
A validated increase in the system's reusable representations, operators, features, or problem-solving capabilities. Increased complexity or a larger repository alone does not demonstrate growth in useful intelligence.

### Open-Ended Structural Growth
An architecture's capacity to admit new evidence types, perspectives, operators, and relay units under governance, without requiring that every possible future capability be specified in advance.

### Anti-Goodhart Governance
Measures against optimizing a convenient proxy while degrading the intended objective. In MDI, examples include gaming directional scores, selecting only favorable evidence, or inflating reputation through correlated repetitions.

### Validation Baseline / Ablation
A controlled comparator, such as matching-only, Euclidean directional, metric-native directional, or hypothesis-guided variants. An *ablation* removes or changes one mechanism to estimate its contribution under a fixed protocol.

### Falsifiability
The requirement that a claim have identifiable observations or experiments that could count against it. A mathematical bound, engineering performance claim, and biological mechanism claim require different validation methods.

## 9. Symbols and notation quick reference

| Symbol | Meaning | Domain / qualification |
|---|---|---|
| `A, B` | Compared objects or structures | Domain-specific |
| `x, y` | States or transition endpoints | `x,y ∈ X` |
| `(X,d)` | Metric space | `d` satisfies metric axioms |
| `P` | Perspective | Explicitly specified |
| `G_P` | Goal set | Nonempty subset of `X` |
| `V_P(x)` | Distance-to-goal potential | `d(x,G_P)` |
| `C_P(x,y)` | Metric-native directional score | `[-1,1]` for `x ≠ y` |
| `v,p` | Euclidean displacement / direction vectors | Nonzero for cosine |
| `F_P(x,t)` | Perspective field | Representation-dependent |
| `Φ_P(x,y)` | General directional relation | Range defined by contract |
| `S_M` | Matching similarity | Usually `[0,1]` |
| `S_P` | Perspective-conditioned similarity component | Normalized if mixed |
| `S_I` | Intuitive similarity score | `[0,1]` under contract |
| `D_I` | Complementary distance score | `1−S_I`, not necessarily a metric |
| `λ` | Convex-mixture weight | `[0,1]` |
| `η` | Residual-correction gain | Calibration-dependent |
| `g_P` | Directional admissibility gate | Usually `[0,1]` |
| `r_i` | Matching coverage | Usually `[0,1]` |
| `q_i` | Evidence quality/admissibility weight | Contract-dependent |
| `H` | Hypothesis | Falsifiable and contextual |
| `E` | Evidence | Includes provenance and counter-evidence |
| `R` | Reputation estimate | Meaning must be specified |

## 10. Common distinctions and prohibited shortcuts

1. **Score ≠ metric.** `1 − similarity` does not automatically satisfy metric axioms.
2. **Metric ≠ direction.** A distance function alone does not choose a goal, value function, or preferred transition.
3. **Goal progress ≠ object similarity.** A candidate moving toward a goal may still be unlike the reference object.
4. **Directional utility ≠ directional agreement.** These answer different questions.
5. **Euclidean convenience ≠ cognitive mechanism.** A useful cosine implementation is not evidence of neural cosine computation.
6. **Weak evidence ≠ validated feature.** OTHERS requires explicit promotion criteria.
7. **Reputation ≠ truth probability ≠ action value.** Each has a different reference class and loss function.
8. **Repeated evidence ≠ independent replication.** Dependence and shared provenance must be checked.
9. **Conformance ≠ validation.** A correct implementation of a candidate operator may still be ineffective.
10. **Forward guidance ≠ final decision.** Search prioritization must remain distinguishable from policy selection.

## 11. Reading map and maintenance policy

- **MDI-001:** problem formulation, score semantics, and research boundaries.
- **MDI-002:** Euclidean and metric-native mathematical operators.
- **MDI-003:** perspective fields and pre-decisional guidance.
- **MDI-004:** OTHERS residual allocation and MET integration.
- **MDI-005:** lightweight hypothesis testing and reputational intelligence.
- **MDI-006:** evidence relay, validation, and structural growth.

This glossary is extension-local. New terms should be added only when they have a distinct operational meaning; substantive changes should be reflected in the relevant MDI paper and version notes. Historical BM-ODWEI definitions and release artifacts should not be silently overwritten.
