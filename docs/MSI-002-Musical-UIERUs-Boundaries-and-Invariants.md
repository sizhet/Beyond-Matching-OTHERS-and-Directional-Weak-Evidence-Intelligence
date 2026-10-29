# MSI-002 — Musical UIERUs, Boundaries, and Invariants

**Project:** Musical Structural Intelligence and Open-Ended Evolution (MSI-OEE)  
**Subtitle:** From Musical UIERUs and Romantic Intelligence to Perspective Scoring, Structural Relay, and Human–AI Co-Evolution  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Document type:** Conceptual framework, operational definitions, and testable research proposals  
**Status:** Exploratory; proposed constructs and hypotheses are not established empirical findings

## Abstract

Musical structure is recognizable across changes of key, tempo, instrumentation, ornamentation, performance, and cultural setting, yet the identity of a musical idea is neither reducible to a fixed sequence of notes nor wholly independent of its context. This paper develops a provisional account of **Musical Universal Intelligence Evolution and Relay Units (Musical UIERUs)**: reusable, transformable, context-sensitive units whose functions and interfaces support musical composition, perception, performance, transmission, and structural growth. We distinguish observable segments from functional units, define multiple forms of boundary and invariance, propose a context- and perspective-conditioned identity model, and examine musical signatures at the levels of motif, work, performer, and tradition. The account treats structural invariance as graded and task-relative, rather than absolute; distinguishes perceptual recognition from causal derivation and legal copying; and explicitly allows music to challenge the existing UIERU framework. Operational schemas, counterexamples, and experiments are proposed to test whether explicit Musical UIERUs provide explanatory and generative advantages over note-level, fixed-window, symbolic, and learned-embedding baselines.

**Keywords:** Musical UIERU; musical motifs; segmentation; structural identity; invariance; transformation; musical function; perspective; musical signatures; structural relay; open evidence; music cognition

---

![Fig-002-Musical-UIERU-and-Structural-Invariants.png](../figures/Fig-002-Musical-UIERU-and-Structural-Invariants.png)

*Figure 2. Musical UIERU candidates and the contextual tests used to investigate structural and functional identity under transformation.*

---

## 1. The Research Problem

Music exhibits a tension that is fundamental to structural intelligence: musical ideas can remain identifiable while their surface realizations change. A motif may survive transposition, rhythmic expansion, orchestration, or redistribution among voices. Yet a seemingly minor change in timing, accent, harmony, or placement may substantially alter its musical function. Thus, **identity cannot be equated with surface equality**, and **difference cannot be equated with loss of identity**.

This paper asks five questions:

1. What qualifies a musical pattern as a functional Musical UIERU rather than an arbitrary excerpt?
2. Where do musical units begin and end, especially when boundaries are ambiguous or overlapping?
3. Which transformations preserve identity, and for which listeners, contexts, and tasks?
4. How can a unit's identity coexist with changes in expressive and compositional function?
5. Can discovered musical units support composition, retrieval, explanation, and cumulative structural learning?

The goal is not to claim that all musical cognition consists of discrete units. Rather, it is to specify a **falsifiable structural hypothesis** and identify where continuous, distributed, embodied, or socially constructed musical phenomena may require modifications to it.

## 2. What Is a Musical UIERU?

### 2.1 A pattern is not yet an intelligence unit

A recurring sequence of pitches is a *candidate pattern*. To function as a Musical UIERU, it should exhibit at least some combination of the following properties:

- **Recognizability:** identifiable under specified conditions by listeners, models, or both.
- **Contextual function:** contributes to an expectation, gesture, phrase, transition, identity, or other musical role.
- **Reusable organization:** can be recalled, instantiated, adapted, or combined across contexts.
- **Transformability:** admits some identity-preserving and identity-changing operations.
- **Relay compatibility:** can interact with other units or with a larger composition through discoverable interfaces.
- **Evidence of utility:** its explicit representation improves a measurable task or supports a reproducible explanation.

These are *candidate criteria*, not universal necessities. A one-off musical event may be important despite limited reuse; a culturally meaningful pattern may have no obvious symbolic boundary. The framework must allow such exceptions to count against overstrong formulations.

### 2.2 A provisional functional representation

Following MSI-001, define:

$$
U_m=(S,C,P,F,R,E),
$$

where:

| Field | Meaning | Illustrative evidence |
|---|---|---|
| \(S\) — Structural representation | Pitch, interval, rhythm, contour, harmony, timbre, gesture, or learned features | Score, MIDI, audio features, annotations |
| \(C\) — Context | Meter, harmony, neighboring phrases, genre, performance, cultural setting | Local and global musical metadata |
| \(P\) — Perspective | Listener, composer, performer, model, or community under which the unit is identified | Listener group, expertise, task specification |
| \(F\) — Functional role | Opening, continuation, tension, release, reference, transition, accompaniment, etc. | Structural and perceptual judgments |
| \(R\) — Relay interface | Compatibility and transformation relations with other units | Composition, variation, response, transition |
| \(E\) — Evolution capability | Potential for adaptation, reuse, differentiation, and retention | Documented variants, generated candidates, validation history |

This tuple is a **research scaffold**, not a claim that these fields are independent, fully observable, or uniquely identifiable. Some fields may be distributions or sets of competing interpretations.

### 2.3 Three levels of unit status

To avoid premature reification, distinguish:

1. **Candidate unit:** a detected or proposed pattern with uncertain boundaries or function.
2. **Validated task-relative unit:** a candidate supported by reproducible evidence for a specified task and population.
3. **Portable structural unit:** a validated unit with documented interfaces and demonstrated reuse or transfer beyond its discovery setting.

A candidate should not be promoted to a general-purpose Musical UIERU merely because an ANN cluster or motif detector found it.

## 3. Musical Unit Granularity

Musical structure may be organized at several interacting scales:

| Scale | Candidate structure | Typical complication |
|---|---|---|
| Micro-event | Attack, accent, articulation, timbral gesture | Often dependent on surrounding events |
| Local cell | Rhythmic figure, interval pattern, short gesture | Many accidental or conventional matches |
| Motif | Recognizable melodic or rhythmic idea | Multiple legitimate variants |
| Phrase | Larger functional arc | Boundaries may be interpretive |
| Section | Theme, chorus, development, transition | May contain overlapping substructures |
| Cross-sectional | Recurrent theme, long-range rhythmic relation | Noncontiguous identity and dependencies |
| Collective | Style, practice, call-and-response convention | Distributed across works and participants |

**Granularity is not equivalent to intelligence.** A small unit can carry a large functional role; a large passage may have weak portability. Nor is the hierarchy necessarily a tree: musical events can belong to overlapping rhythmic, melodic, harmonic, and expressive structures simultaneously.

### 3.1 Nested and overlapping units

Let a musical work be represented as an event set \(X\). Candidate units may be subsets \(U_i\subseteq X\), but there is no requirement that:

$$
U_i\cap U_j=\varnothing.
$$

A note may simultaneously participate in a melodic motif, a harmonic cadence, and a rhythmic pattern. Units can also be **noncontiguous**, spanning repetitions or interactions among voices. This motivates graph- or hypergraph-like representations alongside sequential segmentation.

### 3.2 Unit discovery must be task-relative

A performer may group notes by breath and gesture; a listener by perceived phrase; a music theorist by harmonic function; an ANN by embedding similarity. Their segmentations can differ without one necessarily being erroneous. The research challenge is to distinguish productive pluralism from unconstrained subjectivity.

## 4. Boundary Intelligence: Where Does a Unit Begin and End?

### 4.1 Four boundary families

**Acoustic boundaries** arise from silence, onset, timbral change, intensity, or other signal cues.

**Structural boundaries** arise from repetition, contrast, cadence, harmonic motion, or formal organization.

**Functional boundaries** arise when a gesture completes, redirects, or changes its role.

**Subjective boundaries** depend on expectation, expertise, attention, memory, and cultural learning.

These boundaries often coincide but need not. A motif may start before a metrical downbeat; an expressive gesture may cross a phrase boundary; a listener may hear a larger unit only after its repetition.

### 4.2 Boundary as a distribution, not a fixed cut

For a candidate boundary at time \(t\), define a task- and perspective-conditioned probability:

$$
B(t\mid X,C,P,T)=\Pr(\text{boundary at }t\mid X,C,P,T),
$$

where \(T\) specifies the task (e.g., motif recognition, phrase segmentation, performance planning). The expression is a modeling proposal, not an assertion that human judgments are perfectly probabilistic.

A unit can therefore have **soft endpoints**, multiple plausible segmentations, or boundaries that become clearer after additional context arrives.

### 4.3 Retrospective and predictive boundaries

Music unfolds in time. A listener may reinterpret an earlier event after hearing its continuation. Therefore unit discovery should distinguish:

- **Online boundary estimate:** what can be inferred at the current time.
- **Retrospective boundary estimate:** what can be inferred after the phrase or work is heard.

A robust Musical UIERU system should represent both, rather than leaking future context into evaluations intended to model real-time perception.

## 5. Structural Invariants and Identity-Preserving Transformations

### 5.1 Invariance is conditional

An invariant is a property retained under a specified family of transformations, **for a specified purpose**. No single invariant is expected to cover all music or all listeners.

Candidate transformation families include:

- **Transposition:** change absolute pitch while preserving interval relations.
- **Tempo scaling:** alter duration globally while preserving proportional timing.
- **Rhythmic augmentation/diminution:** systematically expand or compress durations.
- **Orchestration:** redistribute a pattern across instruments or voices.
- **Register transfer:** move material to a different pitch range.
- **Ornamentation:** add local notes or gestures while preserving a perceived core.
- **Harmonic reharmonization:** change supporting harmony, possibly changing function.
- **Metric displacement:** shift accents or metrical placement, often altering interpretation.
- **Fragmentation and recombination:** reuse parts of a unit in new configurations.
- **Expressive timing:** change microtiming without necessarily changing notated structure.

Some transformations preserve symbolic identity but not perceptual or expressive identity. Others preserve perceptual similarity while altering functional role.

### 5.2 An equivalence relation may be too strong

For a restricted transformation family \(\mathcal T\), one might propose:

$$
U_a\sim_{\mathcal T}U_b
\quad\text{if}\quad
\exists\tau\in\mathcal T:\tau(U_a)\approx U_b.
$$

But approximate recognition may not be transitive: \(A\) resembles \(B\), and \(B\) resembles \(C\), while \(A\) no longer resembles \(C\). Consequently, perceptual identity is often better modeled as a **graded relation** than as a strict equivalence class.

A provisional score is:

$$
I(U_a,U_b\mid C,P,T,\mathcal T)\in[0,1],
$$

interpreted as task-relative identity support, **not** an objective probability unless calibrated against a specified data-generating and labeling process.

### 5.3 Identity has several dimensions

Distinguish at least four questions:

1. **Structural identity:** are organization and transformation relations retained?
2. **Perceptual identity:** do listeners recognize the material as related?
3. **Functional identity:** does it play a comparable role in its context?
4. **Historical or provenance identity:** is there evidence of derivation, quotation, transmission, or independent invention?

These dimensions should not be collapsed. High perceptual similarity is not proof of copying, and copying is not automatically legal infringement.

## 6. Identity Versus Function: A Central UIERU Challenge

Consider a four-note contour repeated twice. In one context it introduces a theme; in another it acts as a transition; in a third it is an ironic quotation. Its surface form may be preserved while its function changes. Conversely, two different contours may serve an equivalent cadential or call-and-response function.

This suggests that a unit may require two coupled representations:

$$
U_m=(U_{\mathrm{form}},U_{\mathrm{role}};C,P,R,E).
$$

This is an **alternative analytical decomposition** of the six-field model, not a replacement for it. Form and role should be evaluated separately, then jointly where appropriate.

A useful research question is whether explicitly representing both improves cross-context retrieval and controlled composition compared with systems that optimize only acoustic or symbolic similarity.

## 7. Musical Signatures: From Motif to Composer and Culture

A musical signature is not necessarily a single distinctive tune. It may emerge statistically and structurally from:

- preferred unit families and their relative frequencies;
- transformation habits and characteristic deviations;
- orchestration and rhythmic articulation;
- recurrent relay patterns and large-scale organization;
- relations between tension, expectation, and resolution;
- context-dependent choices and cultural conventions.

We can model a signature provisionally as:

$$
\Sigma_A=\bigl(\mathcal U_A,\Pi_A,\mathcal R_A,\mathcal V_A\bigr),
$$

where \(\mathcal U_A\) denotes a distribution over candidate units, \(\Pi_A\) transformation policies, \(\mathcal R_A\) relay or composition relations, and \(\mathcal V_A\) observable valuation tendencies. \(A\) may refer to a work, performer, composer, ensemble, genre, or tradition.

**A signature is an inferential model, not an essential personal fingerprint.** Genre conventions, instrumentation, production practices, historical period, and dataset bias can create spurious signatures. Any authorship or style analysis must use matched controls and report uncertainty.

### 7.1 Distinctiveness matters

A highly common musical cell is weak evidence of shared source or distinctive style. A rarer configuration may be more informative, but only relative to an appropriate reference corpus and cultural context. One possible measure is:

$$
D_{\mathrm{distinct}}(U\mid C)=-\log P(U\mid C).
$$

This is a candidate information-theoretic feature; estimating \(P(U\mid C)\) reliably is difficult, and rarity alone does not establish originality, value, or derivation.

## 8. Musical UIERUs as Relay-Compatible Units

A Musical UIERU should be studied not only as a recognizable object but also as a participant in **structural operations**.

Candidate relay operators include:

| Operator | Illustrative action | Validation question |
|---|---|---|
| Sequence | Follow a motif with a compatible response | Does the continuation retain coherent function? |
| Parallelize | Combine units in multiple voices | Are timing, harmony, and texture jointly coherent? |
| Transform | Transpose, augment, ornament, invert | Which identities survive for which perspectives? |
| Embed | Place a unit inside a larger phrase | Does its role remain detectable? |
| Recontextualize | Change harmony, meter, or instrumentation | Does interpretation change predictably? |
| Develop | Derive related material over longer spans | Is the relationship perceivable and musically useful? |
| Contrast | Introduce a deliberately different unit | Does contrast support a meaningful larger arc? |

Musical relay interfaces are often **soft contracts**: compatibility is graded, learned, contextual, and negotiable rather than reducible to a fixed type signature. MSI-003 will develop this point in detail.

## 9. Perspective-Conditioned Identity and Open Evidence

The same sound may be segmented and recognized differently by a novice listener, an expert musician, a performer, or a computational model. Thus, the identity relation should retain the perspective variable \(P\), rather than silently averaging across incompatible judgments.

Disagreement may arise from:

- different learned musical conventions;
- differences in memory, attention, and training;
- different tasks (recognition, performance, authorship, enjoyment);
- acoustic masking or recording quality;
- unmodeled structural or contextual evidence.

This last category connects to **OTHERS** in the BM-ODWEI research line. However, an unexplained residual is not automatically a new musical principle. The proposed path is:

$$
\text{Model–Human Disagreement}
\rightarrow\text{Candidate Residual}
\rightarrow\text{Hypothesis}
\rightarrow\text{Counter-Evidence}
\rightarrow\text{Validated Feature or Rejection}.
$$

Disagreement should be recorded with provenance, annotator diversity, confidence, and possible confounds. Failed hypotheses remain valuable evidence.

## 10. Worked Conceptual Examples

### 10.1 Transposed motif

A short melody is shifted to a different key while preserving intervals and rhythm. A pitch-exact matcher may fail, while a relative-interval representation may recognize it. **Prediction:** a task-relative unit model should outperform exact matching on this transformation without overmatching unrelated melodies.

### 10.2 Rhythmic reinterpretation

The same pitch sequence is placed under different accents or meter. Pitch identity is high, but groove and perceived grouping may change. **Prediction:** models that encode metrical context and perspective should better predict human segmentation disagreement.

### 10.3 Reharmonized phrase

A recognizable melody appears over new harmony. Perceptual continuity may coexist with changed expressive or functional meaning. **Prediction:** separate form and role scores will capture this dissociation better than a single similarity number.

### 10.4 Shared convention without common source

Two independently created works use a conventional harmonic or rhythmic formula. Their similarity may be high while provenance evidence is absent. **Prediction:** corpus-conditioned distinctiveness and counter-evidence should reduce unsupported source-attribution claims.

These are illustrative scenarios, not empirical demonstrations or assessments of particular copyrighted works.

## 11. A Minimal Experimental Program

### 11.1 Dataset design

Assemble or create material with appropriate rights and permissions, including:

- symbolic motifs with controlled transformations;
- short rendered audio examples across instruments and tempi;
- phrases whose context or harmonic support is varied;
- independently authored examples sharing conventional patterns;
- listener annotations of boundaries, identity, and function;
- optional performance variations and improvisational responses.

Where feasible, record musical background, cultural familiarity, task wording, and uncertainty without treating any demographic group as a homogeneous aesthetic subject.

### 11.2 Competing representations

Compare at least:

1. note- or token-level exact and normalized matching;
2. fixed-length windows with handcrafted features;
3. learned audio or symbolic embeddings;
4. explicit hierarchical motif/phrase models;
5. the proposed Musical UIERU representation with contextual role, transformation, and perspective fields.

Match compute budgets and training information where practical. Report whether performance gains arise from the UIERU structure itself or simply from additional supervision, parameters, or metadata.

### 11.3 Evaluation tasks and metrics

| Task | Candidate measures | Key failure mode |
|---|---|---|
| Boundary discovery | Boundary F1 within declared tolerance; inter-annotator agreement | Imposing a false single ground truth |
| Transformation recognition | Retrieval precision/recall; accuracy across held-out transformations | Trivial invariance or overgeneralization |
| Functional role prediction | Calibrated accuracy; agreement with expert and listener labels | Genre and context leakage |
| Cross-context retrieval | Ranking metrics; transfer to unfamiliar works | Memorization of source recordings |
| Relay composition | Blind human ratings; long-range coherence; diversity | Optimizing superficial pleasantness |
| Signature analysis | Held-out attribution with matched controls and uncertainty | Confounding style with identity |
| Perspective modeling | Predictive fit to group and individual judgments | Treating preference as objective truth |

Use multiple independent listening panels and preregistered comparisons when feasible. Human judgments are indispensable evidence for perceptual claims but do not by themselves settle provenance, originality, or legal status.

## 12. Testable Hypotheses and Potential Falsifiers

**H1 — Transformational portability.** Explicit transformation-aware units will improve held-out motif retrieval relative to surface-matching baselines. **Falsifier:** no improvement under matched data and compute, or gains limited to transformations directly encoded in training.

**H2 — Contextual boundary advantage.** Context- and perspective-conditioned segmentation will better predict disagreement across listeners and tasks than a single fixed boundary scheme. **Falsifier:** added context fails to improve held-out prediction or merely fits annotation noise.

**H3 — Form–function dissociation.** Separate representations of form and role will better predict judgments under reharmonization and recontextualization than a unified similarity score. **Falsifier:** the decomposition adds no generalizable explanatory value.

**H4 — Relay utility.** Explicit unit interfaces will improve controllable thematic development or long-range coherence relative to equally resourced generation baselines. **Falsifier:** no blinded improvement, or only increased rigidity and repetition.

**H5 — Signature robustness.** Structural signatures will retain predictive value across instrumentation and recording changes after controlling for genre, corpus, and production artifacts. **Falsifier:** attribution performance collapses under matched controls.

**H6 — Open-evidence growth.** Investigating unexplained human–model disagreement will yield validated new features that improve out-of-sample prediction. **Falsifier:** residual features fail replication, reflect labeling artifacts, or induce overfitting.

Each hypothesis must specify the target population, material, transformations, baselines, and threshold for meaningful improvement before a confirmatory test.

## 13. Risks, Limitations, and Boundary Conditions

**Over-discretization.** Continuous gesture, timbre, groove, and embodied interaction may resist segmentation into stable units.

**Cultural overreach.** Unit definitions derived from one musical tradition may fail elsewhere; universality must be tested, not assumed.

**Perspective collapse.** Aggregating listeners into one preference score can erase genuine differences in hearing and valuation.

**Circular validation.** A system that defines units using the same features on which it is evaluated may appear successful without discovering new structure.

**Confounded originality claims.** Similarity, distinctiveness, derivation, and infringement are separate questions. This paper makes no legal determinations.

**Anthropomorphic inference.** A model that recognizes, generates, or scores music is not thereby shown to have subjective musical experience.

**Goodhart pressure.** Optimizing a narrow proxy for musical coherence or pleasure may suppress expressive deviation and structural innovation.

These limitations are not peripheral caveats. They identify conditions under which the Musical UIERU hypothesis may need to be weakened, revised, or rejected.

## 14. Bidirectional Relay to the SI Research Ecosystem

The music domain can inherit methods from, and return evidence to, the wider Structural Intelligence program:

| Research line | Incoming concepts | Potential outgoing contribution |
|---|---|---|
| UIERU | Unit identity, relay, evolution | Soft and perspective-dependent boundaries |
| SIF | Localization, per-node capability, contracts | Task-relative unit discovery and validation |
| UCPSF | Perspective-aware scoring forests | Multiple non-collapsible aesthetic criteria |
| SSI | Subject boundaries and scoring sovereignty | Perceptual identity across distinct subjects |
| BM-ODWEI | OTHERS, open evidence, perspective distance | Empirical residual-feature discovery |
| Structural Folding / Unfolding | Representation change and transformation | Musical accessibility and identity-preserving adaptation |
| Structural RSI | Evaluator governance and counter-evidence | Guardrails for recursive compositional improvement |

**Relay principle:** a musical finding should be returned as a *candidate structural extension*, with its evidence and boundary conditions attached. Cross-domain validation is required before generalizing it to intelligence at large.

## 15. Implications for the MSI-OEE Sequence

This paper establishes a provisional vocabulary for the remaining research documents:

- **MSI-003** examines composition and development as structural relay across soft interfaces.
- **MSI-004** studies meaningful deviation and Romantic Intelligence, including cases where apparent imperfection becomes expressive value.
- **MSI-005** develops perspective-conditioned scoring and musical worldviews.
- **MSI-006** addresses similarity, distinctiveness, OTHERS, provenance, and counter-evidence.
- **MSI-007** investigates AI composition, structural learning, and the limits of automated evaluation.
- **MSI-008** studies embodiment, AI-native exploration, aesthetic translation, and human–AI co-evolution.

![Fig-002-Musical-UIERU-and-Structural-Invariants.png](../figures/Fig-002-Musical-UIERU-and-Structural-Invariants.png)

*Figure 2. Musical UIERU candidates and the contextual tests used to investigate structural and functional identity under transformation.*

---

## 16. Conclusion

A Musical UIERU should not be defined merely by its length, recurrence, or embedding similarity. It is best investigated as a **candidate functional structural unit** whose identity, boundaries, transformations, roles, and relay possibilities are conditioned by context and perspective. Musical invariance is neither absolute nor uniformly transitive; unit boundaries may overlap or remain uncertain; and similarity does not establish common origin. These difficulties are precisely why music is a demanding test for Structural Intelligence.

The most consequential possibility is bidirectional: UIERU concepts may help explain and construct music, while musical evidence may force UIERU theory to accommodate soft boundaries, graded identity, distributed roles, and subjective valuation. The next step is to test whether these distinctions yield measurable explanatory and generative advantages—not merely a new vocabulary for familiar phenomena.

---

## Research Integrity and Version Note

This document proposes a research framework and experiments. It does not report completed experiments, validated new musical units, human listening results, or legal findings. Equations are operational proposals and should be calibrated or revised against data. Examples are conceptual and do not assert facts about particular composers or works.

**Citation:** Sizhe Tan & GPT-Obot (2026). *MSI-002 — Musical UIERUs, Boundaries, and Invariants*. Musical Structural Intelligence and Open-Ended Evolution (MSI-OEE), v1.0.0. Repository manuscript; DOI to be added after publication.

**License:** See the repository's published license and citation metadata.
