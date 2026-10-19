# BM-002 — OTHERS as an Open Evidence Space

**Project:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0 (Foundational Research Draft)  
**Date:** 2026-10-16  
**Status:** Conceptual and architectural proposal; hypotheses and mechanisms require empirical validation  
**Companion paper:** [BM-001 — Beyond Matching and the Limits of Distance Scoring](BM-001-Beyond-Matching-and-the-Limits-of-Distance-Scoring.md)

## Abstract

Formal matching is powerful precisely because it restricts comparisons to representations and criteria that a system can compute. In open-world intelligence, however, consequential evidence often lies outside the currently aligned feature set. This paper develops **OTHERS** as an explicit, evolving *open evidence space*: a governed interface for contextual, relational, reputational, prospective, and other partially formalized signals that may influence evaluation without yet qualifying as stable metrics. OTHERS is neither a claim that unmeasured signals are valid nor a license to conceal uncertainty in an arbitrary residual term. We define admission, provenance, directionality, dependence, confidence, counter-evidence, and promotion rules; distinguish world evidence from subjective preferences; and propose an evidence lifecycle through which useful residual signals may become candidate features, validated metrics, or structural principles. The resulting architecture preserves the rigor of formal matching while allowing intelligence to investigate what its current representation omits. It offers a bridge to directional measurement sails, collective reputational intelligence, SI structural growth, and SSI-governed choice.

**Keywords:** OTHERS; open evidence space; weak evidence; cross-domain scoring; context; reputation; provenance; counter-evidence; structural learning; uncertainty; SI; SSI

## 1. The Missing Space in Formal Matching

In a closed comparison task, a scoring system can define its features, establish correspondence, and compute a similarity or distance. The design is efficient and auditable. The difficulty arises when *relevance* extends beyond what the current representation can match.

A prospective partner may resemble a successful prior partner on balance-sheet metrics but differ in governance history, stakeholder trust, local conditions, or patterns of evasive behavior. An unfamiliar animal may be visually unlike known predators but trigger alarm through motion and the responses of nearby animals. These signals can be consequential without being readily commensurable with the matched variables.

We propose the working decomposition

$$
S_P(x,y\mid C,t)=F_P\!\left(E_{xy},M_{xy},O_{xy};C,t\right),
$$

where $E_{xy}$ denotes aligned Euclidean components, $M_{xy}$ other explicitly matched measurements, and $O_{xy}$ the evidence not adequately represented by the current matching specification. $P$ is a perspective, $C$ is context, and $t$ denotes time. **This is a functional architecture, not a metric axiom or a claim of additive separability.** Depending on the task, $S_P$ may denote a comparison score rather than mathematical distance.

The key claim is modest but important:

> Failure to represent evidence in the present matching schema does not establish that the evidence is irrelevant.

Conversely, inability to represent a signal does **not** establish that it is informative. The purpose of OTHERS is to make this uncertainty inspectable and testable.

## 2. Defining OTHERS Precisely

**Definition (OTHERS).** Relative to a specified task, representation, and scoring contract, OTHERS is the set of candidate observations, reports, relationships, latent indications, and context-dependent signals that could affect the task's evaluation but are not yet adequately captured by its matched feature and metric components.

This definition has five consequences:

1. **Relative, not absolute.** A signal may belong to OTHERS in one model and to a formal metric in another.
2. **Open, not unbounded authority.** New signal types may enter, but entry does not imply trust or decision power.
3. **Heterogeneous.** Numeric measurements, textual reports, behavioral traces, qualitative judgments, and missingness patterns may coexist.
4. **Potentially directional.** The same signal can favor one evaluative direction while opposing another.
5. **Revisable.** A signal may be validated, downgraded, contradicted, deprecated, or promoted into a structured feature.

OTHERS should not be treated as a single scalar correction, a synonym for noise, a mystical intuition, or an unexplained neural-network residual. It is a **typed evidence interface and lifecycle**.

### 2.1 The boundary is indexed by the scoring contract

Let $\mathcal E(C,t)$ denote the evidence available in context $C$ at time $t$, and let $\mathcal M_\phi$ denote the evidence adequately represented by the current matching contract $\phi$. Then a conceptual residual set is

$$
\mathcal O_{\phi,C,t}=\{e\in\mathcal E(C,t): e\text{ is not adequately represented by }\mathcal M_\phi\}.
$$

This is a *set-level definition*, not a guarantee that $\mathcal O$ can be exhaustively enumerated. Unknown unknowns are not observable evidence. A practical system must distinguish **known residual evidence**, **known missing evidence**, and **unanticipated evidence types**.

### 2.2 OTHERS is not automatically orthogonal

Residual evidence may overlap with matched evidence or with other residual signals. An interview, news report, and market movement may all reflect the same underlying event. Therefore

$$
\operatorname{Info}(E,M,O)\neq\operatorname{Info}(E)+\operatorname{Info}(M)+\operatorname{Info}(O)
$$

in general. Any fusion mechanism must account for duplicated or correlated sources.

## 3. A Working Taxonomy of the Open Evidence Space

The following taxonomy is a research convenience, not a claim that categories are mutually exclusive.

| Class | Typical signals | Why matching may miss them | Main caution |
|---|---|---|---|
| **O1 — Contextual** | timing, location, environment, institutional regime | same features mean different things in different situations | context drift |
| **O2 — Relational** | network ties, causal pathways, dependencies, behavioral interactions | object-level features omit relations | spurious associations |
| **O3 — Reputational** | group assessments, testimony, track record, social response | distributed judgments lack a common scale | rumor, herding, manipulation |
| **O4 — Prospective** | leading indicators, weak warnings, emerging opportunities | evidence concerns futures not yet observed | hindsight and selection bias |
| **O5 — Subjective/Competitive** | goals, loss tolerance, constraints, strategic position | relevance depends on whose choice is being made | preference–fact conflation |
| **O6 — Anomalous/Unclassified** | unfamiliar patterns, unexplained residuals, novel modalities | current ontology lacks an appropriate type | noise and overfitting |

The inclusion of O5 needs care. **Goals and utilities are not necessarily evidence about the external world.** In implementation, store them in a separately governed *perspective/decision plane*, while allowing the OTHERS registry to reference their effects on relevance. This preserves the distinction established in BM-001 between evidence, perspective, and action.

A useful architectural split is

$$
\mathcal O=\mathcal O_{\mathrm{world}}\;\cup\;\mathcal O_{\mathrm{subject\text{-}linked}},
$$

with the second class representing references to subjective interpretation rather than a license to overwrite factual evidence. The union need not be disjoint.

## 4. An Evidence Unit: The Minimal Contract

To move from metaphor to engineering, each admitted residual signal should carry a minimal record. A proposed **OTHERS Evidence Unit (OEU)** contains:

| Field | Purpose |
|---|---|
| `evidence_id` | stable identity for audit and deduplication |
| `observation` | raw or referenced content, without premature factual endorsement |
| `source` / `provenance` | origin, acquisition path, chain of custody |
| `context` / `timestamp` | where and when the observation applies |
| `target` / `comparison` | object, pair, event, or trajectory under evaluation |
| `direction_hypotheses` | candidate positive, negative, or neutral scoring directions |
| `reliability_estimate` | calibrated estimate or explicit unknown status |
| `dependence_group` | likely common-cause or copied-source relationships |
| `counter_evidence_links` | contradictions and disconfirming observations |
| `status` | proposed, quarantined, admitted, validated, rejected, deprecated |
| `privacy_policy` / `use_constraints` | access, retention, and permitted decision uses |

The record should also preserve **what is observed**, **what is inferred**, and **what is preferred** as separate fields or linked objects. Otherwise an inference such as “possibly unreliable” may silently become a fact such as “unreliable.”

The contract is deliberately independent of a specific database, vector store, graph representation, or language model. A future PIRP/PIRU implementation could transport an OEU without forcing every receiving BrainUnit to accept its interpretation.

## 5. Admission Without Credulity

An open evidence space needs a gateway, not an unrestricted accumulator.

### 5.1 Proposed admission stages

1. **Capture:** retain a candidate signal and its source metadata.
2. **Type and scope:** identify its target, context, and potential decision relevance.
3. **Screen:** assess legal/ethical admissibility, privacy, manipulation risk, and basic integrity.
4. **Quarantine or admit:** mark whether the signal may influence exploratory scoring, and at what strength.
5. **Compare:** test against known metrics, alternative explanations, and counter-evidence.
6. **Reassess:** revise reliability and status when outcomes or new evidence arrive.

Admission means *eligible for investigation*, not *verified as true*.

### 5.2 Unknown reliability is not zero or one

A system should explicitly represent lack of calibration. A newly observed weak signal can be provisionally considered without pretending that its likelihood ratio or accuracy is known. Where probability estimates are unsupported, use intervals, ordinal reliability classes, abstention, or sensitivity analysis instead of false precision.

### 5.3 Missingness is itself context-dependent

Absence of evidence may indicate nothing, or it may be informative when an observation was expected. The system should record the **observation process** before converting missingness into a negative score.

## 6. Directionality: From Open Evidence to Measurement Sails

A central insight motivating this project is that weak evidence can have an effect along a *direction* before its full causal structure is understood.

Let $\mathbf u_k$ denote an evaluative direction such as safety, trust, opportunity, or operational resilience. For evidence units $e_i$ with candidate directional representations $\mathbf v_i$, a baseline model is

$$
R_k(x\mid C)=\sum_{i=1}^{n} w_i(C)\,q_i(C)\,g_k(\mathbf v_i,\mathbf u_k;C).
$$

Here $w_i$ denotes relevance weight, $q_i$ a reliability factor, and $g_k$ a directional response. This expression is **a proposed baseline**, not a universal law. It assumes additive aggregation and may double-count correlated evidence. A production model may need source-group aggregation, robust estimators, learned interactions, or explicit probabilistic inference.

**Example:** “The organization often pursues risky projects” might contribute positively to an innovation-opportunity sail, negatively to a capital-preservation sail, and ambiguously to a trust sail. A single global reputation scalar loses this directional distinction.

BM-003 will develop the measurement-sail algorithm, including how directions are specified or learned, how response functions are calibrated, and how correlations alter fusion.

### 6.1 The open-sail hypothesis

A scoring system may discover a useful new evaluative axis by clustering recurring directional responses across contexts, even before it has a stable symbolic explanation. Such discovery is a hypothesis requiring out-of-sample tests; otherwise the system may simply learn noise or historical prejudice.

## 7. OTHERS as a Structural Discovery Frontier

The most consequential architectural proposal is not merely to add OTHERS to a score. It is to make the residual evidence space a **source of candidate structure**.

A proposed lifecycle is:

$$
\text{Residual Signal}
\rightarrow\text{Directional Response}
\rightarrow\text{Recurring Pattern}
\rightarrow\text{Candidate Feature}
\rightarrow\text{Validation}
\rightarrow\text{Structured Knowledge}.
$$

Validated knowledge may take the form of a measured feature, a context-specific rule, a CCC, a Principle, or a reusable PIRP/PIRU component. The correct destination depends on the representation and evidentiary strength; repeated correlation alone does not justify a causal principle.

Let $K_t$ denote the current validated structural knowledge and $O_t$ the residual evidence registry. Then

$$
(K_{t+1},O_{t+1})=\mathcal G(K_t,O_t,\mathcal F_t,\mathcal V_t),
$$

where $\mathcal F_t$ is feedback and $\mathcal V_t$ is the validation process. $\mathcal G$ may promote, revise, reject, or retain candidates. There is no guarantee that $K_{t+1}$ strictly increases or that every residual can be formalized.

**Crucial distinction:** open-ended *capacity to accept new evidence types* is an architectural property; open-ended *improvement in intelligence* is an empirical proposition.

### 7.1 A negative result is still useful

If a signal repeatedly fails validation, that outcome should be recorded as counter-evidence, not silently deleted. A failed candidate can prevent rediscovery of the same spurious correlation and improve governance of later scoring proposals.

## 8. Reputational Evidence and Collective Learning

Reputational intelligence is an important subset of the proposed weak-evidence system. It converts testimony, experience, social reactions, and distributed judgments into candidate signals. Such signals may be informative, but popularity does not establish accuracy.

Three mechanisms deserve explicit separation:

- **Independent corroboration:** distinct observers encounter relevant evidence independently.
- **Correlated repetition:** many observers repeat a common origin or shared narrative.
- **Strategic signaling:** actors deliberately influence reputation to change others' decisions.

A collective scoring system must not treat these as equivalent. It should preserve provenance graphs, estimate source dependence, test predictive calibration, and support negative evidence.

This creates a potential SI collective-learning pathway:

$$
\text{Local Experience}
\rightarrow\text{Portable Weak Signals}
\rightarrow\text{Collective Evaluation}
\rightarrow\text{Validated Structural Growth}.
$$

Portable signals should carry context and permission boundaries. A BrainUnit receiving a report may use it as a hypothesis without inheriting the originating unit's preferences or confidence.

## 9. The Boundary with SSI and Competitive Choice

OTHERS evidence may affect an agent's judgment, but it should not automatically determine its choice. Consider a weak signal suggesting that an action is risky. The signal's evidentiary weight is one question; whether that risk is acceptable to a particular subject is another.

A three-plane contract is proposed:

| Plane | Responsibility | Must not silently do |
|---|---|---|
| **Evidence Scoring** | characterize signals, provenance, uncertainty, and contradictions | convert popularity or utility into truth |
| **Perspective Interpretation** | determine relevance under context and viewpoint | erase alternative interpretations |
| **Decision / SSI** | choose actions under goals, constraints, risk, and authority | rewrite evidence to rationalize a choice |

This separation permits competitive, risk-sensitive action without compromising factual calibration. BM-005 will analyze asymmetric perspective distance and action scoring; BM-007 will develop governance safeguards.

## 10. Historical and Cross-Disciplinary Positioning

OTHERS is not a claim that scholars first noticed weak signals, reputation, or non-metric decision criteria here. Adjacent literatures include strategic weak signals (Ansoff), bounded rationality (Simon), heuristics under uncertainty, multi-criteria outranking methods (ELECTRE and PROMETHEE), social network diffusion and weak ties (Granovetter), and evidence fusion and source reliability in intelligence analysis.

These fields already provide mature concepts and sometimes formal models. The proposed research contribution is **integration and interface design**: a residual-evidence contract that admits heterogeneous signals, routes them to directional scoring, maintains provenance and counter-evidence, and supports validated structural promotion. Whether this combination is novel relative to existing architectures must be assessed by systematic literature review and comparative implementation.

Historical divination or ritual practices may illustrate how societies organized decisions under uncertainty, but they do not establish that their predictions were reliable, nor that they implemented the present algorithm. Likewise, claims about evolutionary priority of weak-evidence scoring over metric perception remain hypotheses rather than established facts.

## 11. Falsifiable Hypotheses and Evaluation Design

### H1 — Residual evidence can add predictive information

On selected open-world and cross-domain tasks, a governed OTHERS channel improves held-out prediction or ranking over a matched-features-only baseline, when both systems receive comparable underlying data.

**Disconfirmation:** no reliable gain, or gains disappear under controls for information access and model capacity.

### H2 — Directional representation outperforms a single reputation scalar

Multi-directional scoring improves task-specific discrimination or calibration over an equally complex single-score model.

**Disconfirmation:** no gain after matched-capacity comparison or substantial overfitting.

### H3 — Provenance-aware fusion improves robustness

Source-dependence control reduces error under duplicated rumors, coordinated manipulation, or shared-origin reports.

**Disconfirmation:** no improvement on blinded perturbation sets, or unacceptable loss on independent corroboration.

### H4 — Structural promotion creates reusable value

Validated candidate features learned from OTHERS transfer to new contexts better than retaining all residual evidence as unstructured text.

**Disconfirmation:** learned features fail out-of-distribution tests or are less useful than direct retrieval from raw evidence.

### H5 — Evidence/choice separation improves auditability

Systems separating evidence confidence from subject utility yield more faithful explanations and fewer preference-induced factual distortions.

**Disconfirmation:** no measurable advantage in preregistered audits or decision consistency tests.

### 11.1 Minimal comparison matrix

| System | Matched features | Context | Governed OTHERS | Directional scoring | SSI choice |
|---|---:|---:|---:|---:|---:|
| A — Matching-only | Yes | Limited | No | No | No |
| B — Context-aware | Yes | Yes | No | No | No |
| C — OTHERS + Sails | Yes | Yes | Yes | Yes | No |
| D — C + SSI | Yes | Yes | Yes | Yes | Yes |

Evaluate predictive accuracy, ranking quality, calibration, abstention, downstream utility, robustness to rumor contamination, subgroup harms, computational cost, and cross-domain transfer. The D system should not be expected to outperform C on factual accuracy merely because it optimizes action utility.

Use held-out environments, temporal splits, source-origin controls, and ablations. Keep evidence access and compute budgets comparable where possible. No results are reported in this foundational paper.

## 12. Failure Modes and Safeguards

| Failure mode | Safeguard |
|---|---|
| OTHERS becomes an unfalsifiable catch-all | require explicit signal records and testable claims |
| rumor amplification | provenance graphs, source independence checks |
| bias encoded as “intuition” | subgroup audits, alternative hypotheses, contestability |
| false precision in weak evidence | uncertainty intervals, abstention, calibration |
| data leakage and hindsight | time-aware evaluation and evidence timestamps |
| Goodhart effects on learned sails | monitor strategic adaptation and distribution shift |
| preference contamination of evidence | separate scoring and decision contracts |
| endless accumulation | retention policy, deduplication, retirement criteria |
| premature causal promotion | interventions or stronger causal evidence where feasible |
| privacy violations | consent, minimization, access controls, audit trails |

A residual signal should be eligible to influence high-stakes decisions only under an appropriately stricter evidence and governance policy. The framework does not imply that all weak signals should be operationalized.

## 13. Interfaces with the Broader SI Research Program

- **BM-001:** supplies the distinction among matching, metric distance, perspective distance, and action evaluation.
- **BM-003:** formalizes Directional Measurement Sails as a candidate OTHERS consumer.
- **BM-004:** examines reputation, distributed signals, and collective learning.
- **BM-005:** separates perspective interpretation and competitive action selection.
- **BM-006:** develops the OTHERS-to-validated-structure growth lifecycle.
- **BM-007:** specifies provenance, counter-evidence, and policy governance.
- **BM-008:** consolidates architecture, related work, and experimental protocols.
- **MDT / CCC / Principle Intelligence:** possible targets for validated structural promotion, not automatic outputs of weak-signal aggregation.
- **PIRP / PIRU:** possible transport and execution contracts for portable evidence and learned components.
- **SSI:** provides authorized subjective goals and choice policies without owning or rewriting the evidence record.

**Suggested figure placement:** Insert **Fig-001 — Beyond Matching Grand Map** after Section 3 when introducing the taxonomy, and **Fig-005 — OTHERS Structural Growth Loop** after Section 7. These are cross-paper illustrations; BM-006 should remain the primary explanatory home for Fig-005.

## 14. Open Questions

1. What is the minimum evidence contract that preserves interoperability without imposing a universal ontology?
2. How can a system discover new scoring directions without simply fitting historical noise?
3. When does a qualitative report deserve a quantitative reliability estimate?
4. How should correlated weak signals be fused when common causes are unknown?
5. Which validation criteria justify promoting a signal into a metric, CCC, or Principle?
6. How can collective signals be shared without transferring private information or source-specific bias?
7. When should the system abstain rather than incorporate OTHERS into a consequential score?
8. Can residual-evidence growth improve cross-domain transfer under controlled evaluation?
9. How should governance handle strategic agents who adapt to the scoring system?
10. Which elements of the open evidence space are genuinely new relative to existing decision-science and evidence-fusion frameworks?

## 15. Conclusion

The boundary of a matching model is not the boundary of potentially relevant evidence. **OTHERS** names that gap and gives it an explicit engineering role: a governed, revisable space for signals that matter to evaluation but have not yet earned the status of formal matched features. The proposed architecture does not elevate ambiguity into truth. It keeps source records, uncertainty, dependence, and counter-evidence visible; it allows directional hypotheses to be tested; and it offers a route by which validated residual signals may become reusable structural knowledge.

The research ambition is therefore twofold: **score responsibly beyond current matching contracts**, and **learn which parts of the residual evidence space deserve to become tomorrow's explicit structure**.

> OTHERS is not the abandonment of rigor. It is an interface through which rigor can progressively reach what current matching leaves outside.

## Selected Foundational References and Research Connections

The following are background anchors, not evidence of empirical validation of the proposed OTHERS architecture. Full bibliographic verification and an expanded systematic related-work comparison are reserved for BM-008.

1. Ansoff, H. I. (1975). *Managing Strategic Surprise by Response to Weak Signals*. California Management Review, 18(2), 21–33.
2. Simon, H. A. (1955). *A Behavioral Model of Rational Choice*. Quarterly Journal of Economics, 69(1), 99–118.
3. Granovetter, M. S. (1973). *The Strength of Weak Ties*. American Journal of Sociology, 78(6), 1360–1380.
4. Kahneman, D., & Tversky, A. (1979). *Prospect Theory: An Analysis of Decision under Risk*. Econometrica, 47(2), 263–291.
5. Roy, B. (1991). *The Outranking Approach and the Foundations of ELECTRE Methods*. Theory and Decision, 31, 49–73.
6. Brans, J.-P., & Vincke, P. (1985). *A Preference Ranking Organisation Method: The PROMETHEE Method for Multiple Criteria Decision-Making*. Management Science, 31(6), 647–656.

---

**Citation note:** Cite this document as a conceptual research proposal by Sizhe Tan & GPT-Obot (2026), not as a peer-reviewed or experimentally validated result. A persistent DOI may be added after repository archiving and release.
