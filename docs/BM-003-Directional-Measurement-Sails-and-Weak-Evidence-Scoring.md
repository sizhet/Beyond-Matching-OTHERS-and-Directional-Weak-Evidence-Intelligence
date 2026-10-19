# BM-003 — Directional Measurement Sails and Weak-Evidence Scoring

**Project:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence  
**Version:** 1.0.0 — Research framework / proposed algorithm  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual and algorithmic proposal; empirical performance not yet established  
**Companion papers:** BM-001 (limits of matching), BM-002 (open evidence space)

## Abstract

Conventional similarity and distance scoring operate primarily on features that have already been identified, aligned, and measured. Open-world intelligence also encounters heterogeneous, incomplete, indirect, and weak signals whose significance may be directional even when their underlying explanatory features are not yet formalized. This paper proposes **Directional Measurement Sails (DMS)**, a modular architecture for converting such signals into auditable, perspective-conditioned scoring responses. A sail is a declared or learned directional response function, not a physical detector: it measures how evidence supports, opposes, or leaves unresolved a specified evaluation axis. The proposal separates raw evidence, source reliability, dependence, directional response, uncertainty, and downstream action policy. It describes a minimal mathematical model, correlation-aware aggregation, dynamic learning, counter-evidence, open-ended sail discovery, and an interface for structural growth. DMS is intended as a testable research program, not as an assertion that unstructured signals are intrinsically trustworthy or that directional scoring outperforms existing decision methods.

**Keywords:** directional measurement sails; weak evidence; OTHERS; reputational intelligence; perspective distance; evidence provenance; correlation control; open structural learning; structural intelligence.

## 1. Problem: useful evidence before formal matching

A feature-based matcher asks whether two objects agree on a predefined representation. An open-world evaluator must sometimes act before that representation is complete. A company may exhibit a pattern of troubling employee departures before any single measurable financial indicator deteriorates; an animal may respond to the sudden flight of nearby animals without identifying the underlying threat. In both examples, a weak signal can matter without proving its interpretation.

The research question is:

> How can an intelligent system preserve and evaluate directional effects from heterogeneous evidence that cannot yet be mapped to reliable matched metrics?

DMS is proposed as an *additional evidence-processing layer*, not a replacement for well-calibrated measurements, probabilistic inference, or domain expertise.

## 2. Scope and distinctions

We distinguish four quantities:

1. **Feature similarity**: correspondence under an established representation.
2. **Metric distance**: a function satisfying nonnegativity, identity, symmetry, and triangle inequality.
3. **Perspective-conditioned assessment**: a possibly asymmetric, contextual relation between objects and a declared evaluation axis.
4. **Action value**: expected utility or risk-adjusted value for a decision-maker.

A transformation such as `d = 1 - s` can define dissimilarity for a bounded similarity score, but does not in general create a metric or an action cost. DMS outputs evidence-oriented directional assessments. A separate decision plane determines what action, if any, should follow.

## 3. The sail metaphor as an explicit computational interface

The original intuition is to place a measurement sail along a direction of interest and treat weak signals as influences whose effects can be registered on that sail. To make the metaphor operational, define:

- **Signal**: an observation, report, anomaly, behavior, or inferred clue with provenance.
- **Direction**: a named evaluation axis, such as safety, trust, opportunity, or operational resilience.
- **Sail**: a response function that maps signal features and context to signed support on an axis.
- **Reading**: an aggregate directional score accompanied by quality and uncertainty metadata.

Unlike a literal particle, a signal has no required physical direction. Its *directional representation* is model-dependent and must be learned, specified, or calibrated. A sail may yield positive, negative, or near-zero response; it may also abstain.

**Figure placement:** `../figures/Fig-003-Directional-Measurement-Sails.png` immediately after this section. Suggested caption: *Heterogeneous evidence impinges on multiple direction-specific response functions; readings preserve support, opposition, reliability, and uncertainty rather than collapsing every signal into one global reputation score.*

## 4. Formal objects and notation

Let an evaluation instance be `(x, c, p, t)`, where `x` is the target object, `c` is context, `p` is the declared perspective, and `t` is evaluation time. Let the evidence set be

\[
\mathcal E(x,c,t)=\{e_1,\ldots,e_n\}.
\]

Each evidence unit has a structured envelope:

\[
e_i=(z_i,s_i,\tau_i,c_i,\pi_i,\gamma_i),\]

where `z_i` is signal content or representation, `s_i` is source identity, `τ_i` is observation time, `c_i` is context, `π_i` is provenance, and `γ_i` is an evidence-group or dependence identifier. Missing values must be explicit, not silently imputed as trustworthy.

Let the set of current evaluation directions be

\[
\mathcal U_p=\{u_1,\ldots,u_K\}.
\]

Directions are *perspective-conditioned*: the same evidence can support innovation while opposing capital preservation.

For each direction `k`, define a signed sail response:

\[
r_{ik}=g_{\theta_k}(z_i,u_k,c,p)\in[-1,1].\]

The response is a claim about the signal's *bearing on an evaluation axis*, not a probability that the signal is true. Evidence credibility is represented separately by `q_i ∈ [0,1]`, preferably calibrated using historical outcomes and source audits.

## 5. Minimal directional scoring model

A deliberately simple first approximation is

\[
R_k^{\mathrm{raw}}=\sum_{i=1}^{n}w_{ik}q_i r_{ik},
\]

where `w_ik ≥ 0` is the context- and direction-specific influence weight. This is a **proposed aggregation rule**, not a universal distance law. It can double-count repeated or correlated reports and may be unbounded as evidence volume grows.

A bounded, normalized variant is

\[
R_k=\frac{\sum_i w_{ik}q_i r_{ik}}{\epsilon+\sum_i w_{ik}q_i},\qquad \epsilon>0.
\]

The denominator prevents a larger number of observations from mechanically inflating magnitude, but it does **not** solve dependence or coordinated manipulation. We therefore recommend a grouped formulation.

### 5.1 Dependence-aware aggregation

Partition evidence into source-dependence groups `G_1,...,G_J` using provenance, common upstream claims, and propagation links. First aggregate within a group:

\[
h_{jk}=\frac{\sum_{i\in G_j}w_{ik}q_i r_{ik}}{\epsilon+\sum_{i\in G_j}w_{ik}q_i}.
\]

Then aggregate group contributions:

\[
R_k=\frac{\sum_j \alpha_{jk}h_{jk}}{\epsilon+\sum_j\alpha_{jk}},
\]

with group weights `α_jk` based on independently justified quality and relevance. Grouping is an approximation: shared causal origins can be unknown, and group weights must not be interpreted as independence guarantees.

### 5.2 Keep the evidence channels separate

A single signed score is insufficient. A sail reading should also expose:

- `R_k`: net signed response;
- `P_k`: total positive support;
- `N_k`: total negative or counter-evidence support;
- `Q_k`: assessed evidence quality and provenance coverage;
- `U_k`: uncertainty or an interval/posterior distribution;
- `A_k`: abstention or insufficient-evidence flag.

For example, `R_k ≈ 0` can mean either no evidence or intense conflicting evidence. `P_k`, `N_k`, and `U_k` distinguish these cases.

## 6. An illustrative example: assessing an unfamiliar partner

Suppose a decision-maker evaluates a prospective collaborator along **Trust**, **Innovation**, and **Execution Reliability**. Signals include repeated customer praise, high staff turnover, a history of fast experimentation, and a late contractual disclosure. Their source quality and relevance vary.

| Signal | Trust sail | Innovation sail | Execution sail | Caveat |
|---|---|---|---|---|
| Customer praise | weak positive | near neutral | weak positive | reviews may share one campaign |
| High turnover | weak negative | ambiguous | negative | industry baseline matters |
| Fast experimentation | ambiguous | positive | ambiguous | speed is not quality |
| Late disclosure | negative | near neutral | weak negative | check context and materiality |

These are **illustrative qualitative responses**, not validated numerical scores. The same observations need not imply a single global reputation ranking. A system should be able to show *which direction changed, due to which evidence, under which perspective*.

## 7. Sail design and learning

DMS permits three levels of sail construction:

**Level 0 — Declared sails.** Experts define axes and transparent response rules. Useful for governance and initial baselines.

**Level 1 — Calibrated sails.** Parameters `θ_k` and weights are fitted against held-out directional labels or outcomes, with calibration, robustness, and subgroup checks.

**Level 2 — Discovered sails.** Recurrent residual patterns suggest new candidate directions; candidates are tested for incremental predictive or decision value before admission.

The proposed learning objective may combine directional prediction loss, calibration loss, complexity penalty, and dependence/robustness penalties:

\[
\mathcal L=\mathcal L_{\mathrm{prediction}}+\lambda_c\mathcal L_{\mathrm{calibration}}+\lambda_r\mathcal L_{\mathrm{robustness}}+\lambda_s\Omega(\theta).
\]

The objective is a design template. Exact losses depend on the task, outcome availability, and whether a direction is ordinal, probabilistic, or utility-related. When ground truth is unavailable, do not equate agreement among observers with correctness.

## 8. Counter-evidence and reversibility

Every directional reading should remain contestable. When contrary evidence arrives, the system must update the reading and preserve an audit trail. Counter-evidence may (a) oppose the direction, (b) undermine a source's credibility, (c) reveal shared provenance, or (d) invalidate the direction itself.

A useful update record contains: previous score, new evidence IDs, changed response functions or weights, revised uncertainty, and reason for revision. This aligns with Two-Way CCC and Anti-Goodhart principles: do not allow high reputation to suppress the intake of adverse evidence.

## 9. From OTHERS to structural growth

The OTHERS space should not remain permanently unstructured. Repeated, predictive, directionally consistent weak signals can generate candidate explicit features:

\[
O_t\rightarrow\text{directional effects}\rightarrow\text{candidate feature}\rightarrow\text{validation}\rightarrow K_{t+1}.
\]

Validated candidates may be promoted into formal metrics, CCC structures, principles, or reusable PIRP/PIRU units. The original signal and its provenance remain accessible; promotion is reversible if counter-evidence invalidates the abstraction.

**Crucial distinction:** *discovery* of a candidate is not *validation* of the candidate. A feature must show incremental value under appropriate controls, including leakage and distribution-shift tests.

## 10. Interfaces to SI and SSI

DMS is a scoring component within a broader architecture:

```text
Heterogeneous observations / reports / anomalies
                |
                v
     OTHERS Evidence Units
     + provenance + dependence
                |
                v
   Directional Measurement Sails
     + scores + uncertainty
                |
        +-------+-------+
        |               |
        v               v
Structural discovery   Perspective interpretation
and metric promotion   (context / declared goals)
        |               |
        v               v
SI knowledge growth   SSI / policy-governed choice
```

**SI** can manage structural representations, feature growth, evidence retrieval, and reusable scoring contracts. **SSI** can supply authorized perspective, preferences, and choice criteria. DMS must not infer that the evidence owner's preferences are the same as those of the decision-making subject. The decision plane may use DMS readings, but should not silently rewrite evidence to suit a desired action.

## 11. Governance and failure modes

The following threats require explicit tests:

1. **Echo amplification:** many reports derived from one upstream assertion.
2. **Adversarial reputation manipulation:** coordinated praise, denunciation, or strategic omissions.
3. **Context collapse:** transplanting a signal across domains without checking applicability.
4. **Proxy discrimination:** protected attributes inferred through apparently neutral signals.
5. **Overconfidence:** treating qualitative direction as calibrated probability.
6. **Feedback loops:** decisions based on a score change future observations and make the score self-fulfilling.
7. **Stale evidence:** old signals dominate despite environmental change.
8. **Sail proliferation:** unconstrained new axes produce multiple-testing artifacts and interpretability loss.

Mitigations include provenance graphs, dependency-aware aggregation, temporal decay with auditability, counter-evidence intake, held-out evaluation, access controls, human review for consequential decisions, and explicit abstention.

## 12. Research hypotheses

- **H1 — Incremental signal value:** Directional weak-evidence scoring improves specified cross-domain outcomes over matched-feature-only baselines on at least some pre-registered tasks.
- **H2 — Directional decomposition:** Multiple sails outperform a single global reputation score when goals are heterogeneous.
- **H3 — Provenance correction:** Dependence-aware aggregation reduces overconfidence under repeated or coordinated evidence.
- **H4 — Structural promotion:** Candidate features discovered from residual directional signals improve out-of-sample performance after validation.
- **H5 — Separation of planes:** Separating evidence, perspective, and action yields better auditability and error diagnosis than a monolithic score.

Each hypothesis may fail; negative findings should inform redesign rather than be concealed.

## 13. Proposed validation protocol

### 13.1 Baselines

Compare (A) matched-feature scoring, (B) context-enriched scoring, (C) standard multi-criteria or probabilistic evidence fusion, (D) DMS without dependence correction, and (E) DMS with dependence correction. For action tasks, evaluate a separate SSI/policy layer with the same evidence across competing approaches.

### 13.2 Tasks and measures

Use cross-domain analogy/ranking, early warning, partner evaluation, and noisy collective evidence datasets with documented outcomes. Report ranking quality, calibration, abstention behavior, decision utility, robustness to copied reports, distribution shift, and explanation faithfulness. Prefer temporal splits and independent source partitions over random splits when propagation or historical leakage is plausible.

### 13.3 Ablations

Remove one component at a time: source credibility, context, dependence grouping, counter-evidence, directional decomposition, and structural promotion. Test sensitivity to mislabeled axes, unreliable provenance, and adversarially injected weak signals.

### 13.4 Success and failure criteria

Pre-register metrics, baselines, sample sizes, and meaningful effect thresholds. A favorable example does not establish general superiority. If a simpler established method matches DMS, prefer the simpler method unless DMS provides separately demonstrated auditability, adaptability, or interoperability gains.

## 14. Relation to prior research

DMS should be compared with established work on **multi-criteria decision analysis** (including outranking approaches such as ELECTRE and PROMETHEE), **Bayesian evidence fusion**, **subjective logic**, **reputation and trust systems**, **weak-signal detection**, **social-network diffusion**, **robust decision-making**, and **representation learning**. These fields already address important portions of the problem. The proposed research contribution is the *integration* of open residual evidence, multiple directional response functions, provenance-aware scoring, and a pathway from weak signals to validated structural growth. Novelty and performance remain questions for literature review and experiment.

Selected foundational starting points for further bibliography verification:

- Ansoff, H. I. (1975). “Managing Strategic Surprise by Response to Weak Signals.” *California Management Review*.
- Granovetter, M. S. (1973). “The Strength of Weak Ties.” *American Journal of Sociology*.
- Roy, B. (1991). “The Outranking Approach and the Foundations of ELECTRE Methods.” *Theory and Decision*.
- Jøsang, A. (2016). *Subjective Logic: A Formalism for Reasoning Under Uncertainty*. Springer.

These references identify relevant traditions; they are not evidence that the proposed DMS algorithm has been experimentally validated.

## 15. Open questions

1. Can a sail be defined independently of an explicit semantic axis, or must all directions remain interpretable?
2. How should evidence dependence be estimated when propagation graphs are incomplete?
3. When should a sail abstain rather than aggregate?
4. What is the smallest useful set of sails for a new domain?
5. How can new directions be discovered without multiple-comparison overfitting?
6. Which weak signals are safely transferable across domains?
7. How should collective learning preserve minority counter-evidence?
8. What contracts should govern the SI-to-SSI boundary?

## 16. Conclusion

Directional Measurement Sails offer a proposed mechanism for treating weak, heterogeneous evidence as *directionally informative without pretending it is already a validated matched metric*. The key commitments are: separate evidence from preference, preserve provenance and dependence, distinguish net scores from uncertainty, allow counter-evidence, and promote residual signals into explicit structure only after validation. The central engineering opportunity is not to replace rigorous measurement with rumor; it is to prevent premature exclusion of potentially useful evidence while preserving the controls needed to discover when that evidence is misleading.

> **Not everything that matters can initially be matched; what cannot yet be matched may still be directionally sensed, evaluated, tested, and eventually structured.**

---

**Repository note:** This document specifies a research architecture and candidate algorithm. It contains no experimental claims, production implementation, or assurance of suitability for high-stakes decisions.
