# MDI-002 — Euclidean and Metric-Native Directional Scoring

**Research extension:** Metric Directional Intuition (MDI)  
**Parent framework:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence (BM-ODWEI)  
**Companion:** [MDI-001 — Problem Definition and Research Boundaries](MDI-001-Problem-Definition-and-Research-Boundaries.md)  
**Status:** Theory-first mathematical specification and candidate algorithms; no empirical superiority or biological mechanism is claimed  
**Intended repository path:** `extensions/metric-directional-intuition/docs/MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md`

## Abstract

Directional weak-evidence scoring should not be identified with a particular embedding or cosine operator. This paper develops two complementary computational routes: (i) **Euclidean Directional Sails**, which project feature vectors onto perspective directions, and (ii) **Metric-Native Directional Differences**, which evaluate progress toward perspective-conditioned target sets directly from a metric. We prove a boundedness result for normalized changes in distance-to-target, state its exact assumptions, and derive the local connection to Euclidean gradient projection. We distinguish directional utility from directional agreement and strict mathematical metrics from bounded distance-like scores. We then specify multi-perspective aggregation, missing-evidence behavior, score composition, robustness constraints, counterexamples, and a minimal conformance and validation agenda. The goal is a representation-agnostic operator suitable for the BM-ODWEI OTHERS pathway and future MET integration—not a claim that biological intuition uses these computations.

---

![Fig-009-Euclidean-vs-Metric-Native-Scoring.png](figures/Fig-009-Euclidean-vs-Metric-Native-Scoring.png)

**Figure 009. Euclidean vs. Metric-Native Directional Scoring.** The Euclidean route evaluates alignment through normalized vector projections; the metric-native route evaluates progress toward a goal set using changes in a distance-to-goal potential. The latter does not require a Euclidean embedding, provided the metric and goal set satisfy the stated assumptions.

---

## 1. Research Position and Scope

BM-ODWEI establishes the progression **Matching → OTHERS → Directional Measurement Sails → Reputational Intelligence → Structural Growth → Evidence Governance**. MDI-001 defines the problem and research boundaries. MDI-002 asks a narrower, mathematical question: *How can perspective-dependent directional evidence be converted into a controlled, auditable score without assuming that all meaningful directionality is Euclidean?*

The design is intentionally plural:

- **Route E (Euclidean):** use vectors and cosine projections when a meaningful common inner-product representation exists.
- **Route M (metric-native):** use changes in distance to a perspective target set; no global vector coordinates are required.
- **Route R (general relational, future):** learn directed transition preferences or local action comparisons where neither a global target potential nor a Euclidean embedding is justified. This is a research boundary, not a fully specified algorithm here.

A directional *score* is not automatically a similarity, probability, utility, or mathematical metric. The consuming system must declare which interpretation it uses.

## 2. Common Definitions and Contracts

Let `(X,d)` be a nonempty metric space, with finite-valued metric `d: X × X → [0,∞)`. Let `P` denote a perspective: objectives, reference sets, context, preferences, and constraints. A *transition* is an ordered pair `(x,y)` with `x,y ∈ X`. In a structured system, `x` and `y` can be states, structural summaries, or projected descriptions of candidate transitions.

Define a **signed directional contribution**

$$
C_P(x,y)\in[-1,1],
$$

when evidence is available, with positive values representing progress according to the chosen perspective and negative values representing regress. Its optional display-scale transformation is

$$
S_P(x,y)=\frac{1+C_P(x,y)}{2}\in[0,1]. \tag{1}
$$

The midpoint `0.5` means *neutral directional contribution on this scale*, **not** 50% probability, 50% matching evidence, or a substitute for missing data. A missing or invalid contribution must be represented as unavailable, with a separately defined fallback.

**Directional utility** asks whether a transition or candidate moves in a desirable direction. **Directional agreement** asks whether two candidates have similar directional profiles. **Structural matching similarity** asks whether structures align under a specified matching scheme. These are distinct quantities and should be stored separately.

### 2.1 Output contract

A candidate operator should return at least:

```text
DirectionalScoreResult {
  status: valid | unavailable | invalid
  score_signed: number?          # [-1, 1] only when valid
  score_normalized: number?      # [0, 1] only when valid
  semantics: utility | agreement
  perspective_id: string
  representation_id: string
  evidence_ids: list[string]
  reliability: number?           # separately calibrated; not a probability by default
  assumptions: list[string]
  warnings: list[string]
}
```

The score is a bounded **candidate evaluation**. Confidence, reliability, and evidence strength are separate fields. Source-level evidence attribution and no-double-counting requirements are developed in MDI-004 and MDI-005.

## 3. Route E: Euclidean Directional Sails

### 3.1 Single-vector sail

Assume an inner-product space `R^n`, a nonzero perspective vector `p`, and nonzero feature vectors `v_i` for `i=1,...,N`. Define

$$
c_i(p)=\frac{\langle v_i,p\rangle}{\|v_i\|_2\|p\|_2}\in[-1,1]. \tag{2}
$$

With nonnegative weights `q_i` and `Q=Σ_i q_i>0`, define

$$
C_E(B\mid p)=\frac{\sum_{i=1}^{N}q_i c_i(p)}{\sum_{i=1}^{N}q_i}. \tag{3}
$$

For uniform `q_i`, (3) reduces to the arithmetic mean of the cosine projections originally proposed for Directional Measurement Sails. Convexity proves `C_E ∈ [-1,1]`; applying (1) yields a normalized score. Zero-length feature or perspective vectors cannot be assigned an arbitrary cosine: they must be excluded according to a declared eligibility policy or cause an unavailable result. If no eligible feature remains, the operator is **unavailable**, not `C_E=0` by fiat.

**Interpretation:** (3) is a perspective-conditioned *directional utility* of `B`, not by itself a similarity between `A` and `B`.

### 3.2 Reference-versus-candidate semantics

For a fixed reference `A`, a candidate `B`, and a common perspective `p`, one possible ranking score is

$$
U_E(A,B\mid p)=\alpha S_E(A\mid p)+(1-\alpha)S_E(B\mid p), \quad \alpha\in[0,1]. \tag{4}
$$

If `A`, `p`, and `α` are fixed for every candidate, the `A` term is constant. It may be removed **for ranking** when the remaining coefficient is positive, but not when reporting calibrated absolute scores or distances. At `α=1`, every candidate ties under (4), so the reduction cannot produce a meaningful ranking.

If the goal is **directional agreement**, a simple scalar comparison is

$$
A_E(A,B\mid p)=1-\frac{|C_E(A\mid p)-C_E(B\mid p)|}{2}\in[0,1]. \tag{5}
$$

This tests agreement along one perspective, not structural identity. Opposite signs imply disagreement; equal projected values may still conceal substantial differences in orthogonal components. More informative multi-direction profiles are considered below.

### 3.3 Multi-vector perspective ensemble

Let `P={(p_j,w_j)}_{j=1}^m`, with nonzero `p_j`, nonnegative `w_j`, and `Σ_j w_j=1`. If every component score is valid,

$$
C_E(B\mid P)=\sum_{j=1}^m w_j C_E(B\mid p_j)\in[-1,1]. \tag{6}
$$

Retain the **unfolded profile**

$$
\mathbf c_E(B\mid P)=(C_E(B\mid p_1),\ldots,C_E(B\mid p_m)). \tag{7}
$$

A scalar sum may hide conflicting goals. Governance rules may therefore require a minimum score on safety-critical dimensions before any weighted folding. Missing dimensions must follow an explicit reweight-or-abstain policy; silently reweighting may change the meaning of the perspective.

### 3.4 Structural vector field

For feature state or location `z_i`, let `F_P(z_i)` be a perspective-conditioned, nonzero vector in the same local inner-product space as `v_i`. Then

$$
C_F(B\mid P)=\frac{\sum_i q_i\,\cos(v_i,F_P(z_i))}{\sum_i q_i}. \tag{8}
$$

This is well-defined only when the vector spaces and pairings are specified. If different elements live in different tangent or feature spaces, do not compare or sum raw vectors across locations without a justified transport or representation rule. Scalar cosine results can be aggregated once each local pairing is valid. A field used to guide *candidate generation before scoring* is an additional architectural hypothesis, developed in MDI-003.

## 4. Route M: Metric-Native Directional Difference

### 4.1 Distance to a target set

Let `G_P ⊆ X` be a **nonempty** perspective-conditioned target set. Define the potential

$$
V_P(x)=d(x,G_P):=\inf_{g\in G_P}d(x,g). \tag{9}
$$

Because the metric is finite-valued and `G_P` is nonempty, `V_P(x)` is finite and nonnegative. No closest point needs to exist: the infimum is sufficient. For distinct states `x ≠ y`, define

$$
\boxed{C_M(x,y\mid P)=\frac{V_P(x)-V_P(y)}{d(x,y)}}. \tag{10}
$$

For `x=y`, the quotient is undefined. A policy may return `unavailable` or a separately labeled `no-motion` status; it must not pretend the ratio was evaluated. Equation (10) is *ordered*: reversing the transition negates the score.

### 4.2 Proposition: boundedness

**Proposition 1.** Under the assumptions above, for any `x ≠ y`,

$$
-1\le C_M(x,y\mid P)\le1. \tag{11}
$$

**Proof.** For any `g∈G_P`, the triangle inequality gives `d(x,g) ≤ d(x,y)+d(y,g)`. Taking the infimum over `g` gives `V_P(x) ≤ d(x,y)+V_P(y)`. Interchanging `x,y` gives `V_P(y) ≤ d(x,y)+V_P(x)`. Hence

$$
|V_P(x)-V_P(y)|\le d(x,y).
$$

Because `x≠y` implies `d(x,y)>0`, divide by `d(x,y)` to obtain (11). ∎

Thus **metric-native bounded directional scoring requires neither Euclidean embedding nor cosine**. Its bound is a mathematical theorem; its usefulness for intuitive decisions remains an empirical question.

### 4.3 Properties and limitations

- **Sign:** `C_M>0` indicates reduction in target-set distance; `C_M<0` indicates increase; `C_M=0` indicates no *net* change in this potential, not necessarily a valueless action.
- **Reversal:** `C_M(y,x|P)=-C_M(x,y|P)` for `x≠y` and fixed `P`.
- **Scale invariance:** replacing `d` by `a d`, `a>0`, leaves (10) unchanged, provided the target set is unchanged.
- **No target attainment required:** `G_P` need not be closed or compact; only nonempty.
- **No automatic path optimality:** local positive progress need not yield a globally safe, feasible, or optimal path.
- **No universal direction from distance alone:** the metric supplies magnitudes, while `G_P` supplies perspective and orientation. Without a target, preference, or transition rule, a metric cannot distinguish desirable from undesirable directions.

### 4.4 Worked examples

**Real line.** Let `X=R`, `d(x,y)=|x-y|`, `G_P={0}`. For `x=3`, `y=2`, `V_P(x)=3`, `V_P(y)=2`, and `d(x,y)=1`, so `C_M=+1`. For `x=3`, `y=4`, `C_M=-1`. For `x=3`, `y=-3`, the score is `0`: equal distances to the target do not imply identical states or identical trajectories.

**Discrete graph.** Let `X` be vertices of a connected graph with positive edge lengths, `d` the shortest-path metric, and `G_P` a nonempty set of goal vertices. Equation (10) works directly with shortest-path distances; no coordinate embedding is necessary. If `x` and `y` are neighboring vertices, the score evaluates relative goal progress per edge cost. It does **not** incorporate hazards or admissible actions unless these are represented in the graph, the target, or separate constraints.

**Multi-goal target set.** If `G_P` includes multiple acceptable terminal states, the potential evaluates distance to the nearest acceptable goal in the metric sense. This can be useful, but can also obscure goal switching and nonconvex preferences; preserve the identity of the active or nearest goal when relevant.

## 5. A More General Metric-Native Family

Equation (10) works because distance-to-set is **1-Lipschitz**. More generally, suppose a perspective potential `V_P:X→R` satisfies

$$
|V_P(x)-V_P(y)|\le L_P d(x,y), \quad L_P>0. \tag{12}
$$

Then

$$
C_{M,V}(x,y\mid P)=\frac{V_P(x)-V_P(y)}{L_P d(x,y)}\in[-1,1],\quad x\ne y. \tag{13}
$$

The constant `L_P` must be a justified global or domain-specific Lipschitz bound, not a value guessed after observing scores. If `L_P=0`, the potential is constant on the domain, and no directional information is supplied by (13). This generalization permits cost-to-go surrogates, learned potentials with certified regularity, or composite distance-derived potentials.

**Important boundary:** a generic learned potential without a known Lipschitz bound does **not** inherit the theorem. Clipping its output to `[-1,1]` enforces a numerical range but does not establish metric consistency.

### 5.1 Multiple metric-native objectives

For target sets `G_j` and metrics or metric-compatible distances `d_j`, construct individually valid scores `C_{M,j}`. A convex combination

$$
C_{M,\mathrm{multi}}(x,y\mid P)=\sum_j w_j C_{M,j}(x,y),\quad w_j\ge0,\ \sum_jw_j=1 \tag{14}
$$

remains bounded if every term is valid. However, if each score uses a different state representation or admissibility domain, the operator must establish that `(x,y)` is meaningfully represented in every component. Report per-objective scores and constraints before folding.

### 5.2 Perspective changes over time

If `P=P_t` changes, the score compares states under a *fixed perspective snapshot* `P_t`:

$$
C_M(x_t,y\mid P_t).
$$

Comparing `V_{P_t}(x_t)` to `V_{P_{t+1}}(y)` mixes state change with a change of evaluation function and does **not** satisfy the boundedness proof in general. Dynamic perspectives require explicit versioning or an additional term accounting for perspective drift.

## 6. Connection Between the Metric and Euclidean Routes

Assume `X=R^n` with Euclidean distance and a differentiable potential `V_P` at `x`. For `y=x+h`, `h≠0`, first-order expansion gives

$$
V_P(x+h)=V_P(x)+\nabla V_P(x)\cdot h+o(\|h\|_2).
$$

Hence

$$
C_{M,V}(x,x+h\mid P)=
-\frac{\nabla V_P(x)\cdot h}{L_P\|h\|_2}+o(1). \tag{15}
$$

If `\nabla V_P(x)≠0`, this can be written

$$
-\frac{\|\nabla V_P(x)\|_2}{L_P}
\cos\big(h,\nabla V_P(x)\big)+o(1). \tag{16}
$$

Thus a metric-native difference locally resembles a **gradient projection**, with magnitude factor `||∇V||/L_P`. It becomes a *pure* cosine only where that factor is one. For a distance-to-set potential, differentiability is not guaranteed, particularly at target boundaries, cut loci, or points with multiple nearest targets.

This establishes a precise bridge: **Euclidean cosine is a useful local special case under additional geometric assumptions; it is not a universal definition of directionality.**

## 7. Similarity Composition and Distance-Score Conversion

Let a structural matching baseline return `S_M(A,B)∈[0,1]`. A valid directional score may be mapped to `S_P=(1+C_P)/2` and combined by a convex mixture:

$$
S_I(A,B\mid P)=(1-\lambda)S_M(A,B)+\lambda S_P(A,B\mid P),\quad \lambda\in[0,1]. \tag{17}
$$

Here `S_P` must be chosen deliberately: a candidate's directional **utility** is not automatically a pairwise **agreement** score. Equation (17) is bounded when both inputs are valid. It may nonetheless lower a high matching score when directional evidence is neutral, which motivates an alternative residual correction:

$$
S_I=operatorname{clip}_{[0,1]}\left(S_M+\eta g_P C_P\right), \tag{18}
$$

where `η≥0` controls strength and `g_P∈[0,1]` is an evidence-validity/reliability gate. With no valid directional evidence, set `g_P=0` and return `S_M` unchanged. A smooth alternative for `0<S_M<1` is

$$
S_I=\sigma\left(operatorname{logit}(S_M)+\eta g_P C_P\right). \tag{19}
$$

The clipping form can saturate and cause ties; the logit form needs explicit treatment at baseline endpoints and calibration of its effect size. Neither composition is proven optimal. Evidence allocation must avoid double-counting features already credited by Matching; MDI-004 specifies the OTHERS/residual interface.

The requested score conversion is

$$
\boxed{D_I(A,B\mid P)=1-S_I(A,B\mid P)}. \tag{20}
$$

Equation (20) yields a bounded **distance-like score**, not necessarily a mathematical metric. It may violate identity of indiscernibles, symmetry, or the triangle inequality, especially when directional utility is asymmetric or perspective-dependent. A metric claim requires separate proof for the actual composed operator.

## 8. Engineering Failure Modes and Counterexamples

| Failure mode | Why it matters | Required mitigation |
|---|---|---|
| Missing or zero-length vectors | Cosine is undefined | Explicit unavailable status; eligibility policy |
| Empty target set | Distance-to-set cannot be evaluated as a finite potential | Reject or request a target specification |
| Identical states `x=y` | Denominator in (10) is zero | Separate no-motion status; do not invent a quotient |
| Changing perspective across a transition | Breaks fixed-potential bound | Freeze/version `P` for a score, or model drift explicitly |
| Unknown Lipschitz constant | No guarantee of (13)'s bound | Certify the bound or label as heuristic |
| Attractive local minima / obstacles | Positive progress need not imply a feasible plan | Safety constraints, reachability checks, multi-step planning |
| Scalar folding hides goal conflict | A strong negative can cancel a positive | Retain unfolded vector; enforce hard constraints |
| Same feature counted in Matching and OTHERS | Inflated apparent evidence | Provenance and residual evidence allocation |
| Score treated as probability | Invalid confidence interpretation | Separate calibration and reliability fields |
| Pairwise distance mistaken for strict metric | False mathematical guarantees | Name as distance-like unless axioms are proved |

A useful counterexample to *local progress implies safe action*: a shortest geometric move toward a goal may cross an impassable obstacle. Metric-native progress alone cannot authorize the action; the action set and transition dynamics must be checked separately.

A useful counterexample to *directional agreement implies structural similarity*: two structurally different candidates can have identical cosine projections on a single perspective vector. Equation (5) assigns perfect directional agreement even though their unmatched dimensions differ greatly.

## 9. Minimal Conformance Requirements

A proposed implementation should satisfy the following testable requirements before being presented as a valid scoring operator:

**E-series — Euclidean:**

- **E-01:** Nonzero, finite vectors produce cosine scores in `[-1,1]` within numerical tolerance.
- **E-02:** Positive-weight aggregation preserves the range.
- **E-03:** Zero-vector and empty-eligible-set cases return an explicit unavailable/invalid state.
- **E-04:** Multi-sail aggregation retains the unfolded directional profile.

**M-series — Metric-native:**

- **M-01:** For nonempty `G_P` and `x≠y`, computed scores satisfy (11) within numerical tolerance.
- **M-02:** Reversing `(x,y)` negates the score under the same perspective snapshot.
- **M-03:** Positive rescaling of the metric leaves (10) invariant.
- **M-04:** Empty targets and `x=y` are handled explicitly.
- **M-05:** The implementation works on at least one non-Euclidean representation (e.g., a shortest-path graph).
- **M-06:** Dynamic perspective changes are versioned and never silently mixed in a single finite difference.

**Integration:**

- **I-01:** `S_I` and `D_I` remain in `[0,1]` when their contracts declare normalized outputs.
- **I-02:** No directional evidence returns the baseline Matching score under the declared fallback.
- **I-03:** Directional utility and directional agreement are labeled distinctly.
- **I-04:** Raw directional evidence, reliability, and matching evidence remain separately inspectable.
- **I-05:** Any claim of a strict metric includes an independent axiomatic proof or is withdrawn.

## 10. Validation Design and Falsification

A minimum comparative experiment should include:

1. **Matching-only baseline:** no directional operator.
2. **Euclidean Sail:** single-vector and multi-vector projection, with fixed feature eligibility.
3. **Metric-native target difference:** equation (10), using a declared metric and target set.
4. **Residual integration:** equation (18) or (19), with independently specified evidence gating.

Use held-out tasks and report ranking quality, predictive/decision utility, calibration, computation cost, and out-of-distribution performance. Add controls that randomize the perspective direction, permute target assignments, or remove OTHERS features. Performance improvements under those controls may indicate spurious effects, leakage, or merely increased model capacity. Report negative results.

A biological interpretation requires a separate protocol comparing model behavior with human or animal observations, including error patterns and response under limited time, evidence, and computation. Mathematical boundedness is not biological validation.

## 11. Research Questions and Open Boundaries

- Under what task families does a metric-native directional difference outperform a learned embedding-based projection at comparable cost?
- Can useful perspective potentials be learned with verifiable Lipschitz bounds?
- When does a target-set potential fail to represent context-dependent or cyclic preferences?
- Can a relational directional evaluator preserve auditability without a global scalar potential?
- What is the smallest evidence budget at which directional weak signals improve decisions beyond Matching?
- Can a system promote repeatedly validated OTHERS evidence into reliable Matching components without double-counting?
- Which, if any, of these mechanisms reproduce observable properties of biological intuition?

## 12. Relationship to the MDI Series

- **MDI-001:** foundational definitions, semantics, and epistemic boundaries.
- **MDI-002 (this paper):** mathematical operators, proofs, counterexamples, and conformance conditions.
- **MDI-003:** pre-decisional perspective fields and forward guidance.
- **MDI-004:** OTHERS-only residual scoring, MET adapter, and score composition.
- **MDI-005:** lightweight hypothesis testing and reputational evidence updates.
- **MDI-006:** evidence relay, validation roadmap, and structural growth.

These documents are proposed extensions to BM-ODWEI. They do not revise or supersede BM-001–BM-008. This paper contains mathematical derivations and research specifications, not executable code or a claim of experimentally demonstrated superiority.

## 13. Conclusion

Directional scoring can be formalized along more than one mathematical route. Euclidean Sails provide accessible cosine-based operators; metric-native target differences provide a coordinate-free, bounded directional operator with a short proof based on the triangle inequality. Their relationship can be understood locally through gradient projection under differentiability assumptions. The broader design principle is **representation-agnostic directional intelligence**: preserve a stable scoring contract while permitting alternative geometric, metric, or relational implementations. The scientific next step is to determine when these operators supply genuinely new, reliable information beyond structural Matching, under explicit evidence governance and falsifiable experiments.

---

**Keywords:** BM-ODWEI; Metric Directional Intuition; MET; OTHERS; Perspective-Conditioned Scoring; Directional Measurement Sails; Metric Spaces; Distance-to-Set; Lipschitz Continuity; Structural Intelligence; Evidence Governance.
