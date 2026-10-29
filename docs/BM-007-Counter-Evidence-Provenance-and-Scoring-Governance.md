# BM-007 — Counter-Evidence, Provenance, and Scoring Governance

**Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence**  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0 — October 2026  
**Status:** Conceptual and algorithmic research proposal; not experimentally validated

## Abstract

Open evidence scoring can exploit information that formal feature matching does not yet capture. The same openness creates a governance problem: heterogeneous weak signals may be duplicated, correlated, manipulated, biased, stale, or transformed into unjustified claims of authority. Reputation signals are especially vulnerable because repetition can appear to be corroboration, and a locally useful prediction can be mistaken for a universal judgment. This paper develops a governance architecture for the **OTHERS** evidence space and **Directional Measurement Sails (DMS)**. It separates evidence provenance, signal interpretation, perspective-dependent scoring, candidate structural promotion, and authorization of consequential actions. It proposes typed evidence contracts, dependency-aware aggregation, counter-evidence ledgers, calibrated uncertainty, anti-Goodhart checks, promotion and rollback gates, and policy-enforced decision boundaries. It also introduces an auditable **Scoring Governance Record (SGR)** and falsifiable validation plans. The goal is not to guarantee truth or safety through architecture alone, but to make errors detectable, contestable, attributable, and reversible.

**Keywords:** counter-evidence; evidence provenance; OTHERS; directional weak-evidence scoring; reputational intelligence; correlation control; scoring governance; anti-Goodhart; structural growth; policy control plane; SSI; auditability.

---

![Fig-006-Evidence-Perspective-Decision-Planes.png](../figures/Fig-006-Evidence-Perspective-Decision-Planes.png)

---

## 1. Why Open Scoring Requires Stronger Governance

In the series' earlier papers, **OTHERS** denotes observations not adequately represented by the currently matched feature or metric schema. DMS proposes directional responses to these observations, and Open Structural Scoring Growth (OSSG) proposes a path from weak signals to reusable structures. Each step increases both capability and potential failure surface.

A scoring system that excludes uncertain evidence may miss early warning signals. A system that admits uncertain evidence without discipline may amplify rumor, fabricate certainty, or discriminate through proxies. Neither extreme is acceptable. The governing question is:

> How can a system use uncertain directional evidence without laundering uncertainty into fact, reputation into authority, or model preference into an unauthorized decision?

The proposed answer is **governed openness**: preserve the ability to ingest and test new evidence while enforcing explicit boundaries on interpretation, aggregation, structural promotion, and action.

### 1.1 Five failure transitions

| Transition | Failure | Required control |
|---|---|---|
| Observation → evidence | Fabricated or unverifiable origin | Provenance and integrity checks |
| Evidence → directional score | Duplicate, correlated, or context-mismatched signals | Dependency and applicability controls |
| Score → asserted belief | Uncalibrated certainty; hidden negative evidence | Uncertainty and counter-evidence reporting |
| Belief → structural knowledge | Spurious patterns promoted to reusable rules | Validation and promotion gates |
| Knowledge → action | Unauthorized or disproportionate decisions | Policy, scope, and accountable authorization |

These are separable failure modes. A system can score evidence well and still make an unauthorized decision; it can act within authority and still use false evidence.

## 2. Threat Model and Trust Boundaries

The architecture assumes that evidence may originate from humans, sensors, external documents, peer BrainUnits, models, social networks, or automated agents. Some sources are honest but mistaken; others may be adversarial. The system itself can introduce error through inference, aggregation, or optimization.

**Threat classes** include:

1. **Source spoofing:** false attribution or forged origin.
2. **Repetition laundering:** one original claim recirculated through many accounts.
3. **Coordinated manipulation:** ostensibly independent signals created by a common actor.
4. **Context stripping:** accurate observations transferred to an inapplicable domain or time.
5. **Selective evidence:** supportive signals retained while disconfirming evidence disappears.
6. **Proxy bias:** reputation or context signals standing in for protected or irrelevant attributes.
7. **Goal contamination:** desired actions altering purported factual evidence scores.
8. **Reward hacking:** scoring metrics optimized at the expense of their intended purpose.
9. **Structural lock-in:** a promoted feature becoming difficult to challenge or retire.
10. **Cross-boundary leakage:** confidential or personal evidence propagated without authorization.

No single trust score resolves all ten threats. Provenance, epistemic quality, permissions, and decision consequences must be separately represented.

## 3. The Evidence–Perspective–Decision Separation

The system should distinguish three planes:

- **Evidence plane:** records what was observed, reported, inferred, and contradicted, with provenance and uncertainty.
- **Perspective plane:** maps admissible evidence into scoped directional assessments; perspectives determine relevance but do not rewrite observations.
- **Decision plane:** applies objectives, utilities, risk limits, and authorized policies to select or recommend actions.

A fourth, cross-cutting **governance control plane** defines admissibility, access, promotion rights, escalation requirements, and audit obligations. It must not be confused with an additional scoring direction.

Formally, let an evidence collection be $\mathcal E$, a perspective contract $P$, context $C$, goal $G$, and policy $\Pi$:

$$
\mathcal E^{\mathrm{adm}} = operatorname{Admit}(\mathcal E; C,\Pi),
$$

$$
\mathbf R = operatorname{Score}(\mathcal E^{\mathrm{adm}};P,C),
$$

$$
 a^* \in \arg\max_{a\in\mathcal A_{\Pi}}\mathbb E[U(a,\omega)\mid \mathbf R,\mathcal E^{\mathrm{adm}},P,C,G].
$$

The last equation is a **decision proposal**, not a license to execute. Execution may require a separate authorization event. If the evidence is insufficient, abstention or escalation is an acceptable output.

![Fig-006-Evidence-Perspective-Decision-Planes.png](../figures/Fig-006-Evidence-Perspective-Decision-Planes.png)

*Fig-006. Evidence, perspective, and decision planes retain distinct responsibilities; authorization and counter-evidence apply across their interfaces.*

---

## 4. Provenance-Aware Evidence Units

Every incoming OTHERS signal should carry an explicit contract rather than only a natural-language assertion or scalar weight.

### 4.1 Minimal OTHERS Evidence Unit (OEU)

| Field | Meaning |
|---|---|
| `evidence_id` | Stable identity of this observation or claim |
| `claim_or_observation` | What is actually reported, with modality |
| `source_id` / `origin_chain` | Direct and upstream origins, where available |
| `observed_at` / `received_at` | Event time and ingestion time |
| `context_scope` | Domain, location granularity, population, and applicable conditions |
| `method` | Sensor, testimony, inference, document extraction, or derived signal |
| `lineage_ids` | Known parent evidence and transformations |
| `directional_claims` | Proposed scoring directions, not presumed facts |
| `quality_assessment` | Source/method reliability with basis and uncertainty |
| `counter_evidence_ids` | Explicitly linked contradictory or limiting observations |
| `privacy_class` | Access, retention, and sharing constraints |
| `status` | Unverified, admissible, challenged, superseded, rejected, or retired |

A missing field is not silently replaced with a favorable default. Unknown lineage and uncertain reliability remain explicit.

### 4.2 Provenance is not truth

A signed record can demonstrate who made a claim and whether it was altered; it cannot demonstrate that the claim is correct. Likewise, a reputable source can be mistaken. The system must distinguish **authenticity**, **reliability**, **relevance**, and **independent corroboration**.

### 4.3 Transformations preserve lineage

If a model summarizes ten reports into one statement, the derived statement must retain references to the ten reports. It must not become an eleventh independent witness. For collective learning, a portable PIRP/PIRU unit should include an evidence manifest or a permission-preserving reference to its source lineage.

## 5. Correlation Control: Repetition Is Not Independent Evidence

Let $z_i$ be a bounded directional contribution from signal $i$. The naive sum

$$
R_k^{\mathrm{naive}}=\sum_i w_i z_{ik}
$$

can inflate confidence when signals share the same source or causal pathway.

A first approximation is to group evidence into provenance clusters $c$, then aggregate within each cluster before combining clusters:

$$
R_k=\sum_{c=1}^{C} W_c\,h_k(\{z_i:i\in c\}),
$$

where $h_k$ is a cluster-level summary and $W_c$ reflects reliability and demonstrated independence. This is an **illustrative design**, not a statistically validated estimator. The number of clusters is not automatically the effective sample size.

For continuous measurements with a defensible covariance estimate, a generalized least-squares or Bayesian dependence model may be more appropriate. When dependencies are unknown, confidence should be widened, not inferred from raw message counts.

**Example:** 1,000 reposts of a single allegation provide evidence that the allegation circulated widely; they do not constitute 1,000 independent confirmations of the allegation.

## 6. Counter-Evidence as a First-Class Structure

Counter-evidence must not be treated merely as a negative weight added after positive evidence has already defined the conclusion.

We propose a **Counter-Evidence Ledger (CEL)** with entries that distinguish:

- Direct contradiction of a factual claim.
- Alternative causal explanation.
- Scope limitation or domain mismatch.
- Measurement failure or source unreliability.
- Distribution shift invalidating previous calibration.
- Adversarial or coordinated manipulation.
- Evidence that the claimed effect is absent in a relevant control setting.

Each counter-evidence entry references the claims and scoring directions it challenges, its provenance, its adjudication state, and the resulting revision.

### 6.1 No automatic symmetry

Evidence supporting a claim and evidence opposing it need not be commensurate. A high-quality falsifying observation may outweigh many weak supportive reports. Conversely, a single apparently contradictory event may be explained by context. Governance should preserve the underlying record and the reason for any override.

### 6.2 Reopening settled structures

Promotion to a Metric, CCC, or Principle is not irreversible. New counter-evidence can trigger a **reassessment**, scope restriction, version change, rollback, or retirement. This is essential for open-ended learning under concept drift.

## 7. Directional Scoring With Explicit Uncertainty

A DMS output should not be just a scalar $R_k$. We propose a scoped score record:

$$
\mathcal S_k=(R_k,\;Q_k,\;I_k,\;C_k,\;A_k),
$$

where:

- $R_k$: directional assessment;
- $Q_k$: evidence quality descriptor;
- $I_k$: uncertainty interval or distribution, if defensible;
- $C_k$: counter-evidence summary;
- $A_k$: applicability and abstention status.

Uncertainty intervals should be labeled according to their actual construction. A heuristic range must not be presented as a statistically calibrated confidence interval. Calibration should be tested on held-out, time-separated, and out-of-domain samples where possible.

### 7.1 Abstention is a valid scoring result

If a score is based on poorly attributed, heavily dependent, stale, or inapplicable evidence, the system may return **insufficient evidence** instead of a numerical ranking. This prevents a display convention from being mistaken for knowledge.

### 7.2 Asymmetry is permitted, fabrication is not

Perspective distance and action cost can be directional or asymmetric. But the directionality must come from an explicit perspective, context, or action model—not from silently rewriting evidence to favor a desired outcome.

## 8. Scoring Governance Record (SGR)

We propose a compact auditable record for each consequential scoring event.

```yaml
scoring_event_id: <unique-id>
model_version: <version>
perspective_contract_id: <contract-id>
context_id: <context-id>
policy_version: <version>
evidence_manifest: [<evidence-id>, ...]
lineage_assessment: <known-dependencies-and-unknowns>
admissibility_decisions: [<rule-and-rationale>, ...]
directional_outputs: [<score-quality-uncertainty>, ...]
counter_evidence_manifest: [<counter-evidence-id>, ...]
calibration_status: <validated|heuristic|unknown>
structural_candidates: [<candidate-id>, ...]
action_authorization: <none|recommendation|approved>
review_and_rollback_ref: <reference>
```

This is a **proposed schema**, not a production standard. Sensitive data should be referenced or redacted according to policy; auditability does not justify indiscriminate collection or disclosure.

The SGR should enable reconstruction of *which evidence was available, which rules were applied, which outputs were produced, and who authorized downstream action*. It need not expose protected private inputs to every reviewer.

## 9. Policy Control Plane and Authority

The policy control plane should specify at least five independent controls:

1. **Evidence admissibility:** what data types and sources may enter a task.
2. **Perspective authority:** who may define or alter scoring directions.
3. **Structural promotion:** who may approve new reusable Metrics, CCCs, or Principles.
4. **Action authority:** which recommendations can be executed and under what approvals.
5. **Audit and contestation:** who may challenge, correct, or retire a score or structure.

**Whose choice is it?** is not a minor field of a Scoring Forest. It is an independent authorization question. SSI can represent the subject's preferences and objectives; the policy plane determines whether and how those preferences may affect a particular action. The evidence plane must remain contestable by authorized reviewers.

### 9.1 Competitive optimization under constraints

Competitive action scoring may optimize expected utility within authorized constraints:

$$
a^*\in\arg\max_{a\in\mathcal A_{\Pi}} \mathbb E[U(a,\omega)\mid\mathcal E,P,C,G].
$$

But competitive advantage does not legitimize evidence manipulation, discriminatory proxy use, or violations of authorization. **Winning a decision** and **warranting a belief** are different objectives.

## 10. Anti-Goodhart and Incentive Compatibility

A scoring system that rewards high reputation, confidence, or frequent structural promotion may encourage agents to optimize those proxies rather than underlying outcomes.

Candidate controls include:

- Independent outcome metrics not directly optimized by the scorer.
- Negative controls and placebo directions.
- Source diversity tests and adversarial reputation campaigns.
- Penalties for unjustified certainty and unnecessary complexity.
- Separate scoring and promotion authorities for consequential changes.
- Holdout evaluation across time, domains, and user populations.
- Explicit records of rejected and failed candidate structures.

No single penalty guarantees immunity to Goodhart effects. The goal is to expose failure modes and reduce incentives for gaming.

## 11. Governance of Open Structural Scoring Growth

BM-006 proposes the growth cycle **Capture → Sense → Propose → Challenge → Promote → Reassess**. This paper adds operational governance gates.

| Gate | Required evidence | Failure response |
|---|---|---|
| G0: Capture | Provenance and permitted ingestion | Quarantine or reject |
| G1: Sense | Applicability and dependency assessment | Abstain or restrict scope |
| G2: Propose | Candidate contract and baseline comparison | Keep as hypothesis |
| G3: Challenge | Counter-evidence, leakage, bias, and shift tests | Revise or reject |
| G4: Promote | Demonstrated incremental value and authorization | Local-only or defer |
| G5: Reassess | Monitoring, versioning, rollback trigger | Downgrade, rollback, retire |

Promotion must be **scope-specific**. A weak-signal pattern validated in one domain must not silently become a universal Principle. Every promoted object needs an owner or accountable steward, validation manifest, version, and rollback path.

## 12. Collective Intelligence and Portable Evidence

Collective Structural Learning creates an opportunity to share weak signals before they become fully formalized knowledge. It also creates a propagation risk: a mistaken claim can spread across BrainUnits and return as apparently independent confirmation.

A safe exchange contract should carry:

- Source lineage or privacy-preserving attestations.
- Domain and temporal applicability.
- Evidence status and counter-evidence references.
- Confidence or calibration metadata.
- Use, retention, and redistribution permissions.
- Revocation and supersession identifiers.

A PIRP/PIRU package should distinguish a **portable observation**, a **candidate interpretation**, and a **validated structural unit**. Receiving systems must not treat these as equivalent.

### 12.1 Privacy and fairness

Reputation scoring can affect individuals and groups. Applications involving people should minimize personal data, test for proxy discrimination, provide appropriate contestation mechanisms, and comply with applicable law and organizational policy. Historical reputation data may reflect unequal exposure, feedback loops, and social bias; provenance alone does not solve these problems.

## 13. Worked Example: A Supplier Risk Signal

Consider a company evaluating a potential supplier. Formal matching shows acceptable price, capacity, and delivery history. OTHERS contains indirect reports of recent operational stress.

**Step 1 — Capture.** Three online reports, one trade contact, and one public filing are recorded as distinct evidence units with timestamps and lineage.

**Step 2 — Dependency check.** The three online reports trace back to the same original post. They form one provenance cluster, not three independent confirmations.

**Step 3 — Directional sails.** The evidence affects *delivery reliability*, *financial resilience*, and *reputational trust* differently. The score records quality and uncertainty for each direction.

**Step 4 — Counter-evidence.** A recent verified shipment record and a credible explanation of the public filing constrain the negative interpretation.

**Step 5 — Decision.** A purchasing manager may choose a small pilot order or request additional verification. That action depends on contractual requirements, costs, and authorization—not on an automatic declaration that the supplier is unreliable.

**Step 6 — Growth.** If a particular pattern repeatedly predicts disruptions in prospective evaluations, it may become a candidate feature. Promotion requires out-of-sample evidence, counter-evidence review, and a scoped contract.

The example illustrates workflow, not a claim of predictive success.

## 14. Reference Architecture and Runtime Interfaces

```text
External / Internal Evidence Sources
                |
                v
      OEU Intake + Provenance
                |
                v
   Admissibility / Privacy Filter <------ Policy Control Plane
                |
                v
   Dependency & Counter-Evidence Ledger
                |
                v
    Directional Measurement Sails
                |
                v
   Score + Quality + Uncertainty + Scope
          /                     \
         v                       v
Perspective Interpretation   Candidate Structure
         |                       |
         v                       v
Authorized Decision Gate    Challenge / Promotion Gates
         |                       |
         v                       v
Action / Abstain / Escalate  MDT / CCC / Principle / PIRP-PIRU
         \                       /
          v                     v
       Outcome Monitoring + Reassessment
                     |
                     v
            Scoring Governance Record
```

### 14.1 Proposed interface boundaries

- `EvidenceIntake`: records and validates OEU metadata without asserting truth.
- `DependencyResolver`: links copied, derived, or correlated evidence.
- `CounterEvidenceRegistry`: stores challenges, rebuttals, and unresolved conflicts.
- `DirectionalScorer`: emits scoped score records with uncertainty.
- `PerspectiveContract`: declares authorized interpretation dimensions.
- `PromotionEvaluator`: checks candidate structural contracts against baselines.
- `PolicyGate`: controls access, execution, and escalation.
- `AuditRecorder`: generates and retains SGRs under privacy constraints.

Interfaces are conceptual. Implementation contracts and conformance tests are future work.

## 15. Validation and Falsifiable Hypotheses

The following hypotheses are proposals for testing, not empirical findings.

**H1 — Correlation control:** dependency-aware aggregation reduces overconfidence under duplicated and coordinated weak signals relative to naive aggregation.

**H2 — Counter-evidence:** explicit counter-evidence ledgers improve error detection and revision latency relative to post hoc negative weights alone.

**H3 — Separation of planes:** explicit evidence/perspective/decision boundaries reduce unauthorized preference contamination without unacceptable degradation in task utility.

**H4 — Governed promotion:** scope-specific validation and rollback reduce harmful structural lock-in under distribution shift.

**H5 — Provenance-aware collective exchange:** lineage-preserving PIRP/PIRU sharing reduces false corroboration across BrainUnits.

**H6 — Calibrated abstention:** permitting abstention improves selective risk and calibration on low-quality or out-of-domain evidence compared with forced ranking.

### 15.1 Experimental matrix

| System | Provenance | Dependencies | Counter-evidence | Promotion gates | Policy gate |
|---|---|---|---|---|---|
| A: Naive weak-signal scorer | Minimal | No | No | No | No |
| B: Provenance only | Yes | No | No | No | Basic |
| C: Evidence governance | Yes | Yes | Yes | No | Basic |
| D: Full proposed architecture | Yes | Yes | Yes | Yes | Yes |

Evaluate on controlled synthetic evidence networks **and** real, appropriately licensed, time-stamped datasets. Synthetic tests permit known ground truth and manipulation intensity; real-world tests reveal unmodeled dependencies and transfer limitations.

### 15.2 Metrics

- Calibration: Brier score, log loss, and reliability diagrams where probabilistic claims are made.
- Ranking: task-appropriate precision/recall or pairwise ranking quality.
- Selective prediction: risk–coverage curves and abstention utility.
- Manipulation resistance: score movement under injected duplicates or coordinated sources.
- Structural stability: false-promotion rate, rollback latency, and performance after shift.
- Governance: unauthorized-action rate, trace completeness, and contestation resolution time.
- Fairness and privacy: task-specific disparity, proxy sensitivity, and disclosure incidents.

All baselines should receive comparable underlying evidence and computational budgets. Evaluation should report confidence intervals or other appropriate uncertainty estimates, not only average improvements.

## 16. Related Research and Novelty Boundaries

This proposal intersects several established bodies of work:

1. **Bayesian evidence integration and dependence modeling:** uncertainty, priors, and correlated observations.
2. **Trust and reputation systems:** source reliability, feedback manipulation, and distributed trust.
3. **Data provenance and lineage:** origin tracking and reproducibility.
4. **Robust statistics and adversarial ML:** contamination, strategic manipulation, and distribution shift.
5. **Decision analysis and multi-criteria methods:** preference relations, uncertainty, and non-compensatory constraints.
6. **AI governance and assurance:** authorization, documentation, accountability, and monitoring.

The proposed contribution is not the invention of provenance, counter-evidence, or policy controls. It is a **candidate integration architecture** linking these controls to an explicitly open OTHERS evidence space, directional scoring sails, governed structural promotion, and SSI-compatible action boundaries. Demonstrating novelty requires a systematic comparison against concrete prior architectures and implementations.

### Selected references

- Jøsang, A., Ismail, R., & Boyd, C. (2007). *A Survey of Trust and Reputation Systems for Online Service Provision*. Decision Support Systems, 43(2), 618–644.
- Buneman, P., Khanna, S., & Tan, W.-C. (2001). *Why and Where: A Characterization of Data Provenance*. International Conference on Database Theory (ICDT).
- Pearl, J. (1988). *Probabilistic Reasoning in Intelligent Systems*. Morgan Kaufmann.
- Huber, P. J., & Ronchetti, E. M. (2009). *Robust Statistics*, 2nd ed. Wiley.
- Goodhart, C. A. E. (1975). *Problems of Monetary Management: The U.K. Experience*. Papers in Monetary Economics, Reserve Bank of Australia.
- NIST (2023). *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. NIST AI 100-1.
- Gama, J., Žliobaitė, I., Bifet, A., Pechenizkiy, M., & Bouchachia, A. (2014). *A Survey on Concept Drift Adaptation*. ACM Computing Surveys, 46(4), Article 44.

These references provide neighboring foundations; they are not evidence that the proposed integrated architecture has been validated.

## 17. Open Questions

1. How can lineage be verified when sources are partially anonymous or privacy-constrained?
2. Which dependence models are robust enough for sparse, adversarial weak-signal streams?
3. How should contradictory evidence be represented when both sides are partially credible?
4. When should a directional sail abstain rather than produce a low-confidence score?
5. What constitutes sufficient evidence for promoting a local pattern into a reusable Principle?
6. Who has authority to create, revise, or disable a perspective contract?
7. How can collective learning share useful signals without spreading private data or rumor?
8. What is the minimum SGR that supports meaningful audit without excessive storage and exposure?
9. How can an agent be rewarded for discovering genuine new dimensions rather than producing ever more complex scoring structures?
10. How should governance adapt when a deployed structure changes its own scoring ontology?

## 18. Conclusion

The OTHERS space should remain open to signals that formal matching does not yet capture, but openness cannot mean unaccountable scoring. Directional weak-evidence intelligence needs provenance, dependency awareness, explicit counter-evidence, calibrated uncertainty, bounded structural promotion, and independently enforced action authority.

This paper proposes a **governed open-scoring architecture** in which observations remain traceable, scores remain scoped, claims remain contestable, structural growth remains reversible, and consequential actions remain subject to authorization. These safeguards are design requirements and research hypotheses, not guarantees. Their effectiveness must be demonstrated under ordinary uncertainty, coordinated manipulation, distribution shift, and competitive incentives.

> **An open intelligence system must be free to notice weak signals, but never free to convert unverified signals into unquestionable authority.**

---

## Repository Notes

- **Series:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence.
- **Previous paper:** `BM-006-From-OTHERS-to-Open-Structural-Scoring-Growth.md`.
- **Next paper:** `BM-008-Unified-Architecture-Research-Agenda-and-Validation.md`.
- **Primary figure:** `figures/Fig-006-Evidence-Perspective-Decision-Planes.png` (recommended after Section 3).
- **Related figures:** `figures/Fig-004-Reputational-Collective-Signals.png` and `figures/Fig-005-OTHERS-Structural-Growth-Loop.png`.
- **License:** See repository `LICENSE` (Apache-2.0).
