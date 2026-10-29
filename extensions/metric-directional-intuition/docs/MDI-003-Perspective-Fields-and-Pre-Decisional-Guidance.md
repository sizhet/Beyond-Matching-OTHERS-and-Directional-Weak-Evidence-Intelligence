# MDI-003 — Perspective Fields and Pre-Decisional Guidance

**Research extension:** Metric Directional Intuition (MDI)  
**Parent framework:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence (BM-ODWEI)  
**Companions:** [MDI-001 — Problem Definition and Research Boundaries](MDI-001-Problem-Definition-and-Research-Boundaries.md); [MDI-002 — Euclidean and Metric-Native Directional Scoring](MDI-002-Euclidean-and-Metric-Native-Directional-Scoring.md)  
**Status:** Theory-first architecture and falsifiable research hypotheses; not a demonstrated model of animal neural computation  
**Intended repository path:** `extensions/metric-directional-intuition/docs/MDI-003-Perspective-Fields-and-Pre-Decisional-Guidance.md`

## Abstract

Directional evidence need not wait until a fully specified action or decision is available. An agent may use a perspective-conditioned field to orient attention, propose candidate transitions, select low-cost probes, and prioritize evaluation *before* explicit choice. This paper develops **pre-decisional directional guidance** as an architectural extension of BM-ODWEI's Directional Measurement Sails and MDI-002's representation-agnostic scoring operators. We distinguish Euclidean vector fields, metric-native transition potentials, and general directed relations; define interfaces for proposal, screening, and final evaluation; and examine multi-perspective conflict, risk, uncertainty, temporal adaptation, evidence provenance, and computational budgets. We connect the resulting guidance loop to Structural Intelligence (SI), UIERU forward guidance, and relay without assuming that all directional representations are Euclidean or that any proposed operator is a proven biological mechanism. The paper concludes with conformance criteria and experiments designed to distinguish genuine improvement in candidate discovery from mere re-ranking or evaluation leakage.

---

![Fig-010-Perspective-Fields-and-Forward-Guidance.png](figures/Fig-010-Perspective-Fields-and-Forward-Guidance.png)

**Figure 010. Perspective Fields and Pre-Decisional Guidance.** Schematic perspective-conditioned landscape with multiple exploration trails. Directional information can prioritize attention and candidate generation before explicit evaluation, subject to task, risk, and governance constraints. The landscape is illustrative and does not require a Euclidean state representation.

---

## 1. Motivation: Direction Before Choice

Conventional pipelines often appear to follow `observe → enumerate actions → score actions → choose`. This is an adequate abstraction in small, known action spaces but becomes expensive or incomplete when the relevant candidates are not yet known. A perspective may already supply useful orientation: toward shelter, away from a hazard, along a stable path, toward an unresolved evidence source, or toward a promising structural modification. Such orientation can shape *which candidates are generated*, not merely how a fixed candidate list is ranked.

The research claim is architectural: **perspective-conditioned directionality can serve as a pre-decisional control signal**. It is not a claim that organisms literally calculate gradients, cosine similarities, or metric potentials. Biological inspiration motivates questions; mathematical models and controlled experiments determine which claims survive.

The term *pre-decisional* refers to the location of a computation in a system pipeline, not to the absence of internal choices. Attention allocation and candidate generation are themselves selective processes. We use the term to distinguish these stages from a subsequent explicit choice among evaluated alternatives.

### 1.1 Three separate questions

1. **Orientation:** Which local transitions or structural changes appear promising under perspective `P`?
2. **Generation:** Which candidate actions, observations, hypotheses, or relays should be constructed or retrieved?
3. **Selection:** Which feasible candidate should be chosen after risk, evidence quality, and constraints are assessed?

A system can answer these questions using different operators and evidence budgets. Conflating them obscures where an apparent gain originates.

## 2. Formal Setting and Semantics

Let `(X,d)` be a metric state space, `x ∈ X` the current state, `t` time or episode index, `P` a perspective, and `E_t` the evidence available at that time. Let `A(x)` denote feasible actions and `T(x,a)` a transition model or a distribution over successor states, when available. A perspective can include goals, protected constraints, contextual priorities, uncertainty tolerances, and evaluator identities.

We define a **directional guidance object** abstractly as

$$
\mathcal G_P(x,t,E_t;\,\Delta)\longrightarrow
\bigl(g,\,c,\,\pi,\,\rho\bigr), \tag{1}
$$

where `Δ` is a proposed transition, local change, observation, or query; `g` is a signed guidance value or an ordering relation; `c` is confidence or evidence adequacy (not automatically a probability); `π` records provenance; and `ρ` records applicable risk and constraint annotations. The object need not expose a global vector field.

**Important distinctions:**

- *Directional utility* assesses whether a transition helps a perspective.
- *Directional agreement* compares two candidates' directional profiles.
- *Structural matching* measures correspondence of features or components.
- *Evidence reliability* assesses support for a directional claim.
- *Decision utility* may include consequences not captured by directionality, including safety, feasibility, and long-horizon costs.

MDI-002 provides candidate signed directional scores in `[-1,1]`. Their boundedness is useful for composition but does not turn them into calibrated probabilities or strict metrics.

## 3. A Taxonomy of Perspective Fields

### 3.1 Single Euclidean sail

For an inner-product feature space and nonzero perspective direction `p`, a local displacement `Δx ≠ 0` can be scored by

$$
C^{E}_P(x,\Delta x)=\frac{\langle \Delta x,p\rangle}{\|\Delta x\|\,\|p\|}. \tag{2}
$$

This is a normalized alignment score. It assumes the representation, inner product, and coordinate meaning are defensible. A zero vector is *unavailable*, not a neutral score by default.

### 3.2 Multiple sails and competing perspectives

With directions `p_j`, nonnegative context-dependent weights `w_j(x,t)` summing to one, and valid component scores `C_j`, define

$$
C^{E,ens}_P(x,\Delta x)=\sum_{j=1}^{m}w_j(x,t)C_j(x,\Delta x). \tag{3}
$$

This remains in `[-1,1]` when each component is valid. Missing components require explicit weight renormalization or an unavailable status; silent zero-filling may bias the score. Aggregation can conceal conflicts: a safety-negative sail and a speed-positive sail may cancel. Preserve per-perspective scores and veto constraints before aggregation.

### 3.3 Euclidean directional field

A state-dependent vector field `F_P(x,t)` yields

$$
C^{field}_P(x,\Delta x,t)=
\frac{\langle\Delta x,F_P(x,t)\rangle}
{\|\Delta x\|\,\|F_P(x,t)\|}, \tag{4}
$$

where both vectors are nonzero. The field can reflect local hazards, affordances, or evolving priorities. It is a modeling choice, not a statement about neural encoding.

### 3.4 Metric-native potential guidance

Suppose a nonempty goal set `G_P ⊆ X` is meaningful and `V_P(x)=d(x,G_P)` is finite. For `x ≠ y`, define

$$
C^{M}_P(x,y)=\frac{V_P(x)-V_P(y)}{d(x,y)}. \tag{5}
$$

Since distance to a nonempty set is 1-Lipschitz, `C^M_P ∈ [-1,1]`. Positive values indicate progress toward the target set; zero indicates no change in target distance, not necessarily irrelevance. This route requires a target set and a metric but no Euclidean embedding. When `x=y`, the ratio is undefined and must not be evaluated.

More generally, a potential `V_P` with Lipschitz constant `L>0` permits

$$
C^{V}_P(x,y)=\frac{V_P(x)-V_P(y)}{L\,d(x,y)} \in [-1,1], \tag{6}
$$

provided the Lipschitz claim is established over the evaluated domain. An unknown or invalid bound must not be silently assumed.

### 3.5 General directed structural relations

Some preferences are local, contextual, cyclic, or dependent on history. A relation

$$
R_P(x,y\mid h_t,E_t) \tag{7}
$$

may represent a directed preference or a confidence-bearing comparison without any global scalar potential. It may be nontransitive. A learned relation is **not automatically** a metric-native potential: additional consistency assumptions are required to recover a potential. This remains a separate candidate research route.

### 3.6 Representation-independent interface

All routes should implement a common external contract while reporting their mathematical basis:

```text
GuidanceResult {
  status: valid | unavailable | invalid
  semantics: transition_progress | directional_agreement | pairwise_preference
  route: euclidean_sail | sail_ensemble | euclidean_field |
         metric_target | metric_potential | structural_relation
  perspective_id: string
  state_id: string
  candidate_id: string
  signed_score: number?             # [-1,1] only if valid and bounded
  confidence: number?               # separately calibrated/defined
  evidence_refs: list
  counter_evidence_refs: list
  model_version: string
  constraints: list
  explanation: string?
}
```

A pairwise preference route may return an ordering rather than a normalized signed score; the adapter must declare which contract fields are applicable. An invalid or unavailable score must not masquerade as `0`.

## 4. Pre-Decisional Guidance as a Three-Stage Process

We propose a **Guide → Generate → Evaluate** decomposition.

### Stage A — Guide

Given `(x,P,E_t)`, retrieve or construct a local directional model. It identifies candidate regions, promising transitions, information gaps, or evidence sources. The output may be a field, a potential, a ranked set of local transition templates, or a structural relation.

### Stage B — Generate

A proposal mechanism `Q_θ` samples or constructs a bounded set of candidates using guidance:

$$
\mathcal A_K(x\mid P,E_t)=
operatorname{Propose}_K\bigl(x,\mathcal G_P,E_t,\mathcal C\bigr), \tag{8}
$$

where `K` is a candidate budget and `𝒞` contains hard constraints. Candidates can be actions, observations, questions, local structural edits, or relay targets. Guidance may improve *candidate recall* even when the final scorer is unchanged.

### Stage C — Evaluate and choose

For each candidate `a`, combine evidence-based progress, feasibility, risk, uncertainty, and longer-horizon value:

$$
J(a\mid x,P,E_t)=
\alpha\,\widehat C_P(x,a)
+\beta\,\widehat U_{long}(a)
-\gamma\,\widehat R(a)
-\delta\,\widehat K(a), \tag{9}
$$

subject to hard safety and feasibility constraints. Here `\widehat C_P(x,a)` is a transition-based estimate derived from predicted outcomes or observations; it is **not** the same as a vector direction unless an explicit mapping is justified. The weights and terms must be dimensionally and semantically calibrated before numeric aggregation. If such calibration is absent, use constrained or lexicographic ranking rather than equation (9).

The final choice is

$$
a^*\in\arg\max_{a\in\mathcal A_K\cap\mathcal A_{safe}}J(a\mid x,P,E_t). \tag{10}
$$

A proposal system must also support abstention or safe fallback when no admissible candidate exists.

## 5. Why Guidance Is Not Merely Re-Ranking

A fixed-list scorer can only select from the supplied list. Pre-decisional guidance changes the *distribution of candidates considered*. If `Q_0(a|x)` is an unguided proposal policy and `Q_P(a|x,E)` a guided policy, the central research question is whether the guided proposal produces better feasible candidates within the same budget, not whether it assigns larger numbers to its own outputs.

Two experiments must be separated:

- **Proposal test:** hold the final evaluator fixed and compare candidates generated by `Q_0` versus `Q_P` at equal budget.
- **Ranking test:** hold the candidate pool fixed and compare baseline versus directional evaluation.

A third factorial experiment can test their interaction. Otherwise the claimed gain may arise from a stronger evaluator, larger search budget, or privileged access to the ground-truth target.

### 5.1 Candidate diversity and exploration

Purely greedy directional generation can become trapped by local minima or a misspecified perspective. Reserve some budget for exploratory candidates, counter-directional probes, and alternative perspectives. For example:

$$
Q_{mix}=(1-\epsilon)Q_P+\epsilon Q_{explore},\quad \epsilon\in[0,1]. \tag{11}
$$

This is an engineering heuristic, not a universal optimality result. Its value must be tested against resource and safety constraints.

## 6. Dynamic Perspectives and Temporal Adaptation

A field may change with position, time, context, and evidence. Denote its update as

$$
P_{t+1}=operatorname{Revise}(P_t,E_{t+1},\text{constraints},\text{governance}). \tag{12}
$$

Revisions should record whether a goal changed, new evidence arrived, an evaluator was recalibrated, or the system merely shifted computational attention. These events have different meanings and audit requirements.

A time-varying field need not be the gradient of a single stationary potential. If goals or constraints change, path independence and global consistency cannot be assumed. Guidance systems should detect stale perspectives, regime shifts, and oscillation between incompatible objectives.

### 6.1 Hysteresis and switching costs

Rapidly changing directions can induce unstable behavior. A candidate control design adds switching costs or hysteresis to prevent needless oscillation, while preserving immediate overrides for safety-critical events. This is a proposed design pattern; appropriate stability conditions depend on the transition model and application.

## 7. Multi-Perspective Governance

A perspective is not automatically an authorized objective. Distinguish:

1. **Goal perspective:** what the system is trying to improve.
2. **Safety perspective:** what it must not violate.
3. **Evidence perspective:** what the available measurements can justify.
4. **Stakeholder perspective:** whose interests or evaluations are represented.
5. **Exploration perspective:** which uncertainties are worth reducing.

Weighted averaging is suitable only when trade-offs are authorized and scores are comparable. For non-negotiable constraints, use hard feasibility checks, vetoes, or lexicographic priorities. Preserve per-perspective outputs to avoid a favorable aggregate hiding an unacceptable component.

Perspective conflicts should be first-class evidence, not treated as numerical noise. A conflict may itself generate a new hypothesis, information request, or relay task.

## 8. Directional Guidance Under Weak Evidence

BM-ODWEI emphasizes OTHERS as a space for potentially useful evidence not yet captured by strict Matching. Guidance may exploit such evidence, but the system must prevent unverified signals from silently becoming authoritative controls.

A weak-evidence guidance record should distinguish:

- the observed signal and its provenance;
- the hypothesis linking that signal to a direction;
- the perspective under which the direction is meaningful;
- evidence supporting and contradicting the hypothesis;
- confidence calibration and applicable context;
- the action or candidate-generation consequences of using it.

**OTHERS-only allocation** is important when the same observation already influences a Matching score. MDI-004 develops residual scoring and double-counting controls; this paper does not prescribe its final aggregation rule.

### 8.1 Confidence is not direction

A strong positive directional score with weak evidence is different from a small positive score with strong evidence. Maintain separate axes for signed direction, reliability, risk, and evidence completeness. Do not multiply them mechanically unless the resulting statistic has a defined interpretation and has been calibrated.

## 9. Lightweight Hypothesis Tests as Guidance Updates

A guidance system need not build a complete world model before acting. It can propose a small set of hypotheses about local transitions and request inexpensive discriminating observations:

$$
H_i:\; \text{transition or probe }a_i\text{ is favorable under }P. \tag{13}
$$

Each hypothesis can carry a predicted outcome, a confidence estimate, a counterexample condition, and a test cost. A probe is valuable when its result could change which candidate is selected. In a probabilistic formulation, the appropriate comparison is the **expected value of information** against the cost of testing, subject to safety constraints.

For illustration, an agent navigating an unfamiliar surface may test traction before committing to a turn. This analogy motivates low-cost local probing; it does not imply that a human skater performs explicit Bayesian calculations. MDI-005 specifies lightweight reputation updates and their assumptions.

## 10. Structural Intelligence, UIERU, and Relay

The proposed mechanism connects several SI functions without requiring that they share a single runtime implementation:

**Structural representation:** represent state, candidate transitions, perspectives, evidence, and constraints as addressable objects.  
**Scoring/control plane:** select or compose valid directional operators with explicit semantics.  
**Forward guidance:** bias candidate generation toward promising transitions and informative probes.  
**Multi-trail exploration:** maintain alternative local hypotheses rather than committing prematurely to one direction.  
**Structural relay:** transfer candidate structures, tested hypotheses, counterevidence, and evaluator provenance to another unit or later episode.  
**Residual-driven growth:** promote repeatedly validated weak signals into explicit reusable features or policies, subject to conformance.

This is a conceptual compatibility map, not an assertion that the referenced frameworks already implement all interfaces.

### 10.1 Relay contract

A transferable guidance item should include:

```text
GuidanceRelay {
  source_unit_id
  perspective_id
  context_scope
  representation_route
  candidate_or_transition_description
  evidence_refs
  counter_evidence_refs
  estimated_guidance
  confidence_semantics
  observed_outcome_if_any
  failure_conditions
  evaluator_version
  timestamp_or_episode
  authorization_and_usage_constraints
}
```

A receiving unit must revalidate representation compatibility, context scope, evaluator assumptions, and authorization before reuse. Repeated executions may accumulate evidence for a relay item, but repetition is not independent confirmation when outcomes are correlated.

## 11. Application Cases and Limits

### 11.1 Autonomous navigation

A local field can propose routes or maneuvers before full trajectory evaluation. Safety envelopes, collision avoidance, and dynamics constraints must remain independent of an optimistic directional score. Evaluate candidate quality at fixed planning budget and under distribution shift.

### 11.2 Skilled movement and biological inspiration

Locomotion, skating, and animal foraging suggest that orientation and local probing can be useful under tight reaction-time constraints. These are motivating analogies, not evidence that brains use the proposed cosine or metric-native formulas. Biological claims require behavioral and neuroscientific tests beyond software benchmarks.

### 11.3 Research and engineering agents

A structural research agent may guide its next observation, experiment, code inspection, or question by predicted progress toward a goal. A useful question is itself a candidate cognitive action; its quality must be measured by downstream evidence gain or problem reduction, not linguistic plausibility alone. A fuller theory of question generation and question relay belongs to a separate research agenda, not to the scope of this MDI paper.

### 11.4 Competitive or multi-agent settings

Different agents can maintain incompatible directional perspectives. Competitive advantage is not guaranteed by local progress scores; adversarial adaptation and strategic feedback can reverse local rankings. Retain explicit opponent uncertainty and governance constraints.

## 12. Conformance Requirements

A conforming prototype should satisfy the following minimum requirements:

**C-01 — Semantic declaration.** Every guidance result declares whether it is transition progress, agreement, or preference.  
**C-02 — Representation declaration.** Every operator declares its Euclidean, metric-native, or relational assumptions.  
**C-03 — Validity checks.** Zero norms, zero metric distances, missing goals, invalid bounds, and unavailable evidence are handled explicitly.  
**C-04 — Boundedness.** Operators claiming `[-1,1]` scores provide a mathematical bound or validated enforcement.  
**C-05 — Provenance.** Guidance records identify evidence sources, model versions, and applicable context.  
**C-06 — Constraint priority.** Safety and authorization constraints are not bypassed by positive guidance.  
**C-07 — Proposal/evaluation separation.** Tests can independently measure generation and ranking contributions.  
**C-08 — Perspective conflict visibility.** Conflicting component scores are preserved rather than hidden in an average.  
**C-09 — Fallback.** Missing or unreliable directional evidence triggers a documented baseline or abstention.  
**C-10 — No metric overclaim.** A bounded directional distance-like score is not advertised as satisfying symmetry or the triangle inequality without proof.  
**C-11 — Relay revalidation.** Transferred guidance is checked against destination context and evaluator assumptions.  
**C-12 — Claim discipline.** Mathematical properties, engineering hypotheses, and biological interpretations are labeled separately.

## 13. Falsifiable Hypotheses and Evaluation Design

**H1 — Candidate discovery.** At matched computational and candidate budgets, guided proposal finds more feasible high-quality candidates than an unguided baseline on selected tasks.

**H2 — Proposal/ranking complementarity.** Guidance used in proposal generation provides measurable gains beyond applying the same signal only as a final reranker.

**H3 — Metric-native advantage in appropriate domains.** On non-Euclidean or embedding-distorted tasks, metric-native target-difference guidance outperforms a justified Euclidean projection baseline, without assuming universal superiority.

**H4 — Multi-perspective robustness.** Explicit conflict and hard-constraint handling reduces constraint violations compared with unconstrained score averaging.

**H5 — Weak-evidence calibration.** Provenance-aware gating improves out-of-distribution reliability relative to ungated directional weak evidence.

**H6 — Probe efficiency.** Under limited evidence budgets, selectively testing decision-relevant hypotheses improves outcome quality relative to random probing.

### 13.1 Experimental matrix

| Condition | Candidate proposal | Final evaluator | Directional evidence |
|---|---|---|---|
| B0 | Unguided | Baseline | None |
| B1 | Unguided | Direction-aware | Fixed candidate pool |
| B2 | Direction-guided | Baseline | Proposal only |
| B3 | Direction-guided | Direction-aware | Proposal and ranking |
| B4 | Random/shuffled perspective | Same as B3 | Negative control |
| B5 | Metric-native guided | Same as B3 | No Euclidean embedding required |
| B6 | Guided + probe selection | Same as B3 | Budgeted new evidence |

Use independent test environments, matched model calls, equal candidate counts, explicit safety constraints, and held-out perspectives. Report candidate recall, regret or achieved objective, feasibility, violations, calibration, latency, computational cost, and failure modes. Where ground truth is only partially observable, declare proxy limitations. Randomize seeds and test perspective perturbations, stale goals, contradictory signals, and adversarial evidence.

### 13.2 Disconfirmation conditions

The pre-decisional guidance thesis is weakened if guided proposal offers no benefit at matched budgets, if gains disappear under blind evaluation, if performance is driven solely by leaked target information, or if instability and governance costs consistently exceed any gains. Failure of a Euclidean route does not automatically falsify a metric-native route, and vice versa.

## 14. Open Research Questions

1. Can meaningful directionality be learned from sparse evidence without imposing an artificial Euclidean geometry?
2. What conditions allow a relational preference field to be approximated by a global potential without losing important cyclic preferences?
3. How should a guidance system trade off short-horizon directional progress against delayed rewards and irreversible risks?
4. When is it better to generate an action candidate versus an information-gathering question?
5. Can weak evidence be incorporated without double counting signals already represented in Matching?
6. Which relay representations remain portable across different metrics, ontologies, and perspectives?
7. How can changing perspectives be governed without oscillation or unauthorized objective drift?
8. Which behavioral observations would discriminate pre-decisional directional guidance from post-hoc scoring in biological agents?
9. How much candidate-generation improvement survives when the directional model is misspecified?
10. Can SI control planes select among Euclidean, metric-native, and relational operators using evidence-based conformance tests?

## 15. Position Within the MDI Series

- **MDI-001:** problem definition, research scope, and semantic boundaries.
- **MDI-002:** Euclidean and metric-native directional operators, boundedness, and mathematical assumptions.
- **MDI-003 (this paper):** perspective fields as pre-decisional guidance for attention, candidate generation, and probing.
- **MDI-004:** OTHERS-only residual scoring, score composition, and MET integration.
- **MDI-005:** lightweight hypothesis testing and reputational evidence updating.
- **MDI-006:** evidence relay, experimental validation, and structural growth.

The MDI series extends rather than rewrites BM-001–BM-008. In particular, this paper builds on BM-003 (Directional Measurement Sails), BM-005 (Perspective Distance and Competitive Action Scoring), BM-007 (Counter-Evidence, Provenance, and Scoring Governance), and BM-008 (Unified Architecture and Validation).

## 16. Conclusion

Perspective-conditioned directionality can be treated as an input to *what an agent considers*, not only to *how it scores what it already considered*. The proposed Guide → Generate → Evaluate decomposition makes that distinction explicit and experimentally testable. Euclidean vector fields, metric-native target potentials, and general directed structural relations provide different realizations under a shared governance contract. The resulting architecture supports bounded candidate generation, local evidence probes, multi-perspective control, and portable relay while retaining fallbacks and explicit uncertainty. Whether these mechanisms outperform conventional approaches, and whether they illuminate biological intuition, remain empirical questions.

---

**Keywords:** BM-ODWEI; Metric Directional Intuition; Perspective Fields; Pre-Decisional Guidance; Forward Guidance; Directional Measurement Sails; Metric-Native Scoring; Candidate Generation; Structural Intelligence; UIERU; OTHERS; Evidence Governance; Structural Relay.
