# Glossary

**Project:** Beyond Matching: OTHERS, Directional Weak-Evidence Scoring, and Reputational Intelligence  
**Version:** 1.0.0 — Foundational Research  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual and algorithmic research framework; proposed mechanisms require empirical validation.

## Purpose and conventions

This glossary establishes consistent terminology across BM-001 through BM-008. Definitions distinguish **established mathematical or disciplinary terms** from **project-proposed constructs**. A *score* is not automatically a probability, a metric distance, or an authorized decision. All quantities must be interpreted with their specified scale, direction, evidence basis, and scope.

## A. Matching, distance, and scoring

### Matching
The process of comparing objects on explicitly specified, alignable attributes, patterns, or relations. Matching may be exact, fuzzy, semantic, or structural. A high matching score does not by itself establish low risk or high utility.

### Matched Euclidean Components (E)
Comparable numeric components represented in a shared Euclidean coordinate space. Euclidean distance is meaningful only after choosing units, scaling, and feature semantics.

### Matched Metric Components (M)
Comparable components assessed with a specified metric or other validated dissimilarity function. In mathematics, a **metric** is nonnegative, symmetric, separates distinct points, and satisfies the triangle inequality. Not every useful dissimilarity is a metric.

### Similarity Score (S)
A score describing resemblance under a defined representation and comparison rule. Its range and calibration are model-specific.

### Similarity-Derived Dissimilarity
A transformation such as `D = 1 - S` when `S` lies in `[0, 1]`. This is a valid *definition* of dissimilarity in that setting, not necessarily an approximation; it does **not** generally guarantee the metric axioms or encode perspective, asymmetric costs, or action consequences.

### Metric Distance
A mathematically defined distance satisfying the metric axioms. It should not be conflated with perspective-dependent or decision-oriented scores.

### Cross-Domain Distance Scoring
Comparing entities, situations, or structures originating in different domains. Potential difficulties include feature misalignment, missing relational information, changing context, and differences in the evaluator's objective. Whether a given AI system underperforms human judgment is an empirical question, not a universal premise.

### Perspective Distance (project construct)
A context- and perspective-conditioned assessment of how different or consequential two entities are *for a particular interpretive purpose*. It may be asymmetric and need not be a mathematical metric. Notation: `D_P(A, B | P, C)`.

### Action Scoring / Action Value
Evaluation of candidate actions given evidence, goals, expected outcomes, costs, uncertainty, and constraints. Action value is conceptually distinct from factual similarity or perspective distance.

### Competitive Action Scoring
Action evaluation that explicitly considers competitors, strategic response, opportunity cost, timing, and asymmetric consequences. Competitive preference must not be silently substituted for factual evidence.

### Non-Compensatory Scoring
A decision rule in which strength on one criterion cannot always offset a serious deficiency on another; veto thresholds are a common example. Established multi-criteria decision-analysis approaches study such rules.

## B. OTHERS and evidence

### OTHERS (project construct)
An **open evidence space** containing signals not yet adequately captured by the currently matched and formalized feature/metric representation. OTHERS is relative to the model, task, time, and available measurements—not an intrinsic permanent class of facts. It is neither synonymous with noise nor a license to treat unverified claims as true.

### Open Evidence Space
A representation and processing interface that accepts heterogeneous, partially specified, indirect, or anomalous signals while retaining provenance, uncertainty, and scope. New categories and interpretable features may emerge through validation.

### Contextual Evidence
Signals about environment, timing, situation, and background conditions that change the interpretation of an object or comparison.

### Relational Evidence
Signals describing interactions, network links, dependencies, causal hypotheses, or functional relationships among entities.

### Reputational Evidence
Socially communicated evaluations, reports, or historical judgments about an entity. Such evidence may be informative, biased, manipulated, or correlated.

### Prospective Evidence
Signals concerning possible future trajectories, opportunities, risks, or changes. Forecasts must be distinguished from observed facts.

### Subjective / Competitive Evidence Context
Information about a decision subject's goals, priorities, resources, risk tolerance, or competitive position. In this framework these inputs belong to perspective and decision interpretation; they must remain distinguishable from claims about the external world.

### Anomalous Evidence
Signals that do not fit the existing representation or expectations. An anomaly is a candidate for investigation, not proof of a novel structure.

### Weak Evidence / Weak Signal
Information with limited specificity, reliability, coverage, or explanatory clarity that may nonetheless be directionally relevant. Weakness can arise from low signal strength, uncertain sourcing, or incomplete interpretation; these dimensions should not be collapsed.

### OTHERS Evidence Unit (OEU; proposed interface)
A traceable record for an individual evidence item. Suggested fields include identifier, content/observation, source, timestamp, domain, context, claimed direction, reliability estimate, dependency group, uncertainty, access policy, and links to supporting or contradicting evidence. The OEU is a design proposal, not an adopted external standard.

### Evidence Provenance
The documented origin and transformation history of a signal, including source, collection method, intermediaries, and revisions.

### Evidence Independence
The degree to which multiple signals provide genuinely distinct information. Repeated reports derived from one origin are not independent corroboration.

### Correlation Control
Methods to avoid overstating confidence when evidence items share sources, causes, social networks, or measurement artifacts.

### Evidence Quality (Q)
A multidimensional characterization of reliability, relevance, source quality, and corroboration. It should not be assumed to be a calibrated probability without a defined estimation procedure.

### Uncertainty (U)
The remaining ambiguity or lack of knowledge in a score, claim, or decision. It may include aleatoric variability, epistemic uncertainty, and uncertainty about the model's scope.

### Abstention
A valid system response that withholds a score, classification, promotion, or action when evidence is inadequate or governance conditions are unmet.

## C. Directional Measurement Sails

### Directional Measurement Sail (DMS; project construct)
A conceptual and computational evaluator oriented toward one scoring dimension, such as safety, trust, or opportunity. It measures how heterogeneous signals affect that direction without requiring all signals to share a strict matching representation.

### Directional Weak-Evidence Scoring (DWES; project construct)
The proposed family of methods that maps weak evidence into a vector of direction-specific responses, with explicit reliability, dependence, uncertainty, and scope controls.

### Scoring Direction / Sail Axis (`u_k`)
The interpretive dimension along which a sail responds. Axes may be predefined, learned, or proposed through structural discovery; their semantics and ownership must be recorded.

### Signal Representation (`v_i`)
A feature or embedding representation of evidence item `i`, potentially including direction, polarity, context, and provenance.

### Directional Response Function (`g`)
A function describing the response of a sail to a signal, e.g., a dot product, kernel, or learned nonlinear mapping. The response function must be tested for calibration and robustness.

### Illustrative Sail Aggregator

`R_k(x) = sum_i w_i q_i g(v_i, u_k)`

Here `w_i` is a weighting factor and `q_i` an estimated quality factor. This is a **baseline illustration**, not a generally calibrated or correlation-safe estimator. Practical systems require normalization, dependence handling, missing-data policy, and uncertainty reporting.

### Directional Score Vector (`R(x)`)
The collection `[R_1(x), ..., R_m(x)]` of scores across distinct sails. It should not automatically be collapsed into a single universal reputation or utility number.

### Sail Discovery
The proposed process of identifying a new meaningful scoring direction from recurring unexplained evidence-response patterns, subject to validation and governance.

### Sail Calibration
Testing whether a sail's numerical outputs correspond to specified empirical frequencies, rankings, or outcomes. Calibration targets depend on the interpretation of the score.

## D. Reputation and collective signals

### Reputational Intelligence
The use of socially communicated assessments and historical judgments as evidence for domain- and direction-specific evaluation. Reputation is a subset of the wider weak-evidence space, not a substitute for verification.

### Directional Reputation Field (proposed construct)
A multi-axis representation of reputation, e.g., trustworthiness, competence, cooperation, or risk, with source dependence and uncertainty retained.

### Collective Weak Signals
Heterogeneous indirect observations exchanged among individuals, groups, agents, or systems. Collective aggregation can improve coverage but can also amplify correlated error.

### Information Cascade
A process in which actors increasingly follow observed prior choices or reports rather than independent information, potentially producing self-reinforcing errors.

### Collective Structural Learning (CSL; SI ecosystem)
A proposed process in which knowledge-bearing units exchange evidence, candidate structures, validation results, and reusable artifacts to support distributed structural improvement.

### BrainUnit (SI ecosystem)
An independently scoped intelligence unit with its own context, capabilities, interfaces, and governance boundaries.

### PIRP / PIRU (SI ecosystem)
**Portable Intelligence Runtime Piece / Unit**: proposed reusable and relayable intelligence artifacts or units, with distinctions in packaging and formalization specified in their dedicated project. Here they are potential carriers of evidence and learned structures.

## E. Structural growth and validation

### Open Structural Scoring Growth (OSSG; project construct)
A proposed process by which informative residual signals become candidate features, scoring dimensions, metrics, CCC structures, or principles after repeated challenge and validation.

### OTHERS-to-Structure Loop
`Capture → Sense → Propose → Challenge → Promote → Reassess`. This loop is a research architecture, not a claim that all weak signals can be formalized.

### Candidate Structural Contract (proposed interface)
A specification for a proposed new feature, metric, sail, CCC, or principle, documenting semantics, evidence, expected benefit, scope, counter-evidence, tests, rollback criteria, and responsible authority.

### Promotion Gate
A validation requirement that a candidate must satisfy before receiving greater structural authority. Example dimensions: provenance, independence, predictive increment, cross-domain generalization, robustness, and governance approval.

### Structural Promotion
The controlled adoption of a validated candidate into the explicit scoring or knowledge architecture. Promotion may be provisional, scoped, reversible, or rejected.

### Residual OTHERS
Signals that remain unexplained, unvalidated, or inadequately modeled after a growth cycle. Residual evidence must remain available for reconsideration without acquiring unjustified authority.

### Counter-Evidence
Observations, arguments, or tests that challenge a claim, score, or proposed structure. Counter-evidence is a first-class input to validation and reassessment.

### Counter-Evidence Ledger (CEL; proposed interface)
A versioned record connecting claims and candidate structures to supporting and contradicting evidence, status changes, and review outcomes.

### Anti-Goodhart
Design practices intended to reduce failure when a proxy score becomes an optimization target and ceases to track the underlying objective. Relevant practices include holdout evaluation, independent checks, and explicit counter-evidence.

### Metric Differential Tree (MDT; SI ecosystem)
A structural representation organizing differences across domains or nodes, potentially supporting localization, comparison, and incremental growth.

### CCC (SI ecosystem)
A reusable structured concept/condition/context construct within the broader SI research program. This glossary does not redefine the canonical CCC specification; refer to the relevant SI repositories for formal semantics.

### Principle Intelligence (SI ecosystem)
A research approach that extracts and applies more generalizable principles from evidence and structured learning, rather than relying only on instance-level matching.

## F. Subjectivity, decisions, and governance

### Perspective (`P`)
The explicitly declared viewpoint, interpretation frame, or evaluation lens under which differences and signals acquire relevance.

### Context (`C`)
The environmental, temporal, domain, and task conditions constraining an evaluation.

### Goal (`G`)
The target outcomes or objectives that inform action selection; goals must not silently rewrite evidence.

### Subjective Structural Intelligence (SSI; related project)
A research framework concerned with the identity and authority of the evaluating/choosing subject: **whose perspective, whose goals, and whose choice?** This project provides possible evidence and scoring inputs to SSI but does not replace SSI governance.

### Evidence Plane
The layer that records observations, sources, quality, counter-evidence, and evidence-grounded directional responses. It answers: **What can be believed, and with what uncertainty?**

### Perspective Plane
The layer that interprets evidence under an explicit viewpoint and context. It answers: **What does the evidence mean for this subject and situation?**

### Decision Plane
The layer that evaluates available actions, expected consequences, tradeoffs, and constraints. It answers: **What should be done?**

### Policy Control Plane
The governance layer specifying what evidence may be used, what structural changes are permitted, who can authorize decisions, and how actions are audited or reversed.

### Scoring Governance Record (SGR; proposed interface)
An auditable record of a scoring event: model/version, evidence references, perspective, sail configuration, outputs, uncertainty, applicable policy, and review trail.

### Authorized Choice
An action selected by an agent or human with explicit decision rights under the relevant policy. A high score alone does not grant authority.

## G. Research and evidence standards

### Baseline
A comparison method against which a proposed mechanism is evaluated. Suggested baselines include matched-features-only, context-aware, weak-evidence, and goal-aware decision models.

### Ablation Study
An experiment removing or modifying a component—such as reputation, dependence correction, sail discovery, or governance—to estimate its incremental contribution.

### Cross-Domain Generalization
The ability of a scoring system to perform under domain shifts or on previously unseen domains. Evaluation must avoid leakage and report the test setting.

### Falsifiable Hypothesis
A claim accompanied by a test that could show it to be unsupported or false. Proposed superiority of DWES, DMS, or OSSG remains a hypothesis until independently evaluated.

### Structural Authority
The permission and operational weight assigned to a learned feature, metric, CCC, principle, or decision rule. Authority should follow validation and governance rather than mere popularity or score magnitude.

## H. Terminology guardrails

1. **Similarity is not distance by default.** `1 - similarity` need not be a metric.
2. **Perspective distance is not a metric by default.** It may be directional, contextual, and asymmetric.
3. **Weak evidence is not established fact.** Preserve source, uncertainty, and counter-evidence.
4. **Reputation is not truth.** Repetition, popularity, and consensus can share a single origin.
5. **Scoring is not choosing.** Evidence, perspective, utility, and authorization remain distinct.
6. **OTHERS is not a permanent ontology.** Validated components can migrate into explicit structure.
7. **A new sail is not automatically useful.** Demonstrate incremental predictive or decision value.
8. **A proposed interface is not a standard.** OEU, CEL, SGR, and Candidate Structural Contract require implementation and validation.

## I. Reading map

| Topic | Primary paper |
|---|---|
| Matching and distance boundaries | [BM-001](docs/BM-001-Beyond-Matching-and-the-Limits-of-Distance-Scoring.md) |
| OTHERS and evidence units | [BM-002](docs/BM-002-OTHERS-as-an-Open-Evidence-Space.md) |
| Directional sails and scoring | [BM-003](docs/BM-003-Directional-Measurement-Sails-and-Weak-Evidence-Scoring.md) |
| Reputation and collective signals | [BM-004](docs/BM-004-Reputational-Intelligence-and-Collective-Weak-Signals.md) |
| Perspective and action | [BM-005](docs/BM-005-Perspective-Distance-and-Competitive-Action-Scoring.md) |
| Structural scoring growth | [BM-006](docs/BM-006-From-OTHERS-to-Open-Structural-Scoring-Growth.md) |
| Counter-evidence and governance | [BM-007](docs/BM-007-Counter-Evidence-Provenance-and-Scoring-Governance.md) |
| Unified architecture and validation | [BM-008](docs/BM-008-Unified-Architecture-Research-Agenda-and-Validation.md) |

For navigation see [README](README.md), [START-HERE](START-HERE.md), and [CONTENTS](CONTENTS.md).

---

**Research note:** This glossary is a vocabulary contract for the v1.0.0 conceptual release. It should evolve under explicit version control as empirical validation clarifies or changes the proposed constructs.
