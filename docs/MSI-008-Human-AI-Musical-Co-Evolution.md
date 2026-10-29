# MSI-008 — Human–AI Musical Co-Evolution

**Project:** Musical Structural Intelligence and Open-Ended Evolution (MSI-OEE)  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual research framework and testable hypotheses  
**Document:** `docs/MSI-008-Human-AI-Musical-Co-Evolution.md`

## Abstract

Musical intelligence is not exhausted by recognizing acoustic patterns or generating plausible compositions. Human musical life is grounded in hearing, movement, bodily constraints, autobiographical memory, emotion, social interaction, and cultural history. Artificial intelligence systems can analyze audio and learn preferences, but these abilities do not establish that they possess human-like subjective musical experience. This paper therefore questions whether an autonomous AI composer must replicate human musicianship to contribute novel musical value. It proposes **Human–AI Musical Co-Evolution**: a framework in which human and artificial agents maintain distinct perceptual capabilities and evaluation boundaries while exchanging musical structures through bidirectional relay, perspective translation, and iterative evaluation. The paper defines functional versus experiential preference, distinguishes human-native, AI-native, and hybrid musical spaces, proposes intermediate Musical UIERUs as bridges between unfamiliar and familiar forms, and develops an experimentally testable architecture with safeguards against self-confirming aesthetic metrics. The aim is not to assert artificial consciousness or inevitable artistic greatness, but to specify how structurally novel music might become understandable, contestable, and valuable across subjects.

**Keywords:** musical structural intelligence; UIERU; human–AI co-evolution; embodiment; subjective experience; perspective scoring; aesthetic translation; structural relay; open-ended evolution; scoring sovereignty; counter-evidence

---

![Fig-007-Human-AI-Musical-Co-Evolution.png](../figures/Fig-007-Human-AI-Musical-Co-Evolution.png)

*Figure 7. A proposed human–AI musical co-evolution loop using intermediate structures, bidirectional relay, and independent perspective-aware evaluation.*

---

## 1. Introduction: The Composer Without a Human Life

A powerful music generator may recognize motifs, model harmony, imitate performance, and produce recordings that listeners find compelling. Yet an important question remains: what does it mean for such a system to *understand* or *value* music if it lacks the bodily and biographical conditions through which humans encounter it?

Human musical experiences can involve breathing, entrainment, anticipation, motor action, remembered relationships, ritual, grief, pleasure, and shared cultural identity. These are not merely optional annotations to sound. They can shape the creation, interpretation, and valuation of musical structures.

This suggests a limit to a straightforward progression from better generation to an “AI great composer.” However, it also opens a different possibility: AI systems may discover structural relationships not ordinarily explored by humans, while humans and AI develop methods to translate, negotiate, and jointly evaluate those discoveries.

The central thesis is:

> Musical intelligence may advance through **co-evolution across distinct subjects**, not only through increasingly accurate simulation of human musical preferences.

The framework is exploratory. Its terms are operational research proposals, not claims that present AI systems possess feelings, consciousness, or autonomous aesthetic authority.

## 2. Three Layers of Musical Hearing

The phrase “AI cannot hear” conceals different capabilities. At least three layers should be distinguished.

### 2.1 Acoustic access

A system may receive waveforms, spectrograms, MIDI events, or other sensor measurements and extract pitch, rhythm, onset, timbre, spatial, and harmonic information. This is measurable signal access and processing, not proof of lived auditory experience.

### 2.2 Musical interpretation

A system may infer meter, phrase boundaries, harmonic functions, stylistic conventions, expectations, and likely human reactions. These capacities can be tested through prediction, retrieval, transformation, composition, and explanation tasks. Success does not by itself demonstrate subjective experience.

### 2.3 Subjective musical experience

Human listeners may feel tension, nostalgia, joy, bodily resonance, or emotional significance. Whether an artificial system can have analogous first-person experiences is unresolved. Behavioral fluency or a model's verbal claims about liking music are insufficient to settle the question.

These layers should remain separate in system design and research reporting. A useful AI musical collaborator does not need an unverified claim of subjective feeling.

## 3. Embodiment as a Structural Constraint and Opportunity

Human musical cognition is situated in the body and environment. Examples include:

- **Breath and vocal production:** phrase length, timbre, articulation, and expressive pauses reflect physical affordances.
- **Movement and entrainment:** rhythm is shaped by gesture, locomotion, dance, and coordinated timing.
- **Instrumental interaction:** resistance, reach, technique, and feedback influence musical possibilities.
- **Autobiographical memory:** a familiar melody may acquire meaning from personal history rather than its acoustic structure alone.
- **Social synchronization:** ensemble performance requires anticipation, adaptation, and reciprocal attention.
- **Cultural practice:** musical meaning depends partly on learned conventions and communal use.

A conceptual model is:

$$
V_{s,c}(m) = F_s\bigl(\phi(m), B_s, H_s, C_c, I_{s,c}\bigr),
$$

where \(m\) is a musical artifact, \(\phi(m)\) denotes its structural representation, \(B_s\) denotes subject-specific embodied affordances, \(H_s\) historical memory, \(C_c\) cultural context, and \(I_{s,c}\) situated interaction. This is a research decomposition, not a validated universal equation.

AI embodiment need not duplicate human anatomy. An artificial musical agent may acquire sensorimotor constraints through instruments, robotics, responsive interfaces, environmental audio, and collaborative performance. Such coupling could yield distinct forms of musical competence without establishing human-equivalent feeling.

**Research implication:** distinguish embodied musical performance competence from first-person musical experience, and evaluate each with appropriate evidence.

## 4. Functional Preference Is Not Subjective Liking

An AI system can exhibit a **functional musical preference**: a stable, measurable tendency to select some structures over others according to a scoring process or learned policy.

Let \(P_A(m\mid c)\) denote the system's context-conditioned preference ordering over candidate music. Such an ordering can be tested for stability, sensitivity to context, and predictive value. It should not be equated with felt pleasure.

Three notions must be kept distinct:

1. **Selection preference:** the system repeatedly ranks or chooses one candidate over another.
2. **Evaluative competence:** those rankings support useful musical tasks or predict independent judgments.
3. **Experiential liking:** the system has a subjective experience of enjoying music.

The first two are empirically accessible. The third remains philosophically and scientifically unsettled.

An AI-native preference model may favor unusual long-range relationships, transformations, polyphonic density, or other structural properties. These preferences are meaningful as operational hypotheses only when their behavior is reproducible and not merely an artifact of an arbitrary reward function.

## 5. Three Interacting Musical Spaces

We propose three analytically distinct, overlapping spaces.

### 5.1 Human-native musical space

Music organized around human auditory ranges, bodily timing, memory, performance constraints, cultural history, and social use.

### 5.2 AI-native structural musical space

Structures explored through machine representations and computational evaluation that may not map directly onto ordinary human listening. Some may exceed typical attention spans, span non-audible signal ranges, or involve relationships difficult to perceive without mediation.

**Terminological caution:** an AI-optimized signal structure should not automatically be called “music.” Its status depends on a stated musical criterion and evaluation community. AI-native is a research label, not an assertion of machine consciousness or independent cultural legitimacy.

### 5.3 Hybrid musical space

Music created through negotiation between human perceptual and cultural constraints and AI-discovered structural possibilities. Hybrid work may include interactive composition, performance adaptation, progressive transformation, and new listening practices.

The goal is not to collapse these spaces into a single optimum. It is to construct interpretable connections among them while respecting their differences.

## 6. Bidirectional Musical Relay

Conventional preference alignment is often represented as adapting a generator to a fixed human target:

$$
A_t \longrightarrow H_t.
$$

Co-evolution introduces feedback in both directions:

$$
(A_t,H_t,R_t) \longrightarrow (A_{t+1},H_{t+1},R_{t+1}),
$$

where \(A_t\) is the AI's operational musical model, \(H_t\) denotes observable human musical understanding or preferences, and \(R_t\) is the set of available translation and relay mechanisms. The human term does **not** imply that an individual's preferences should be manipulated without consent.

A bidirectional cycle can be expressed as:

1. **AI exploration:** discover or generate candidate musical structures.
2. **Structural description:** identify UIERUs, transformations, dependencies, and uncertainties.
3. **Translation relay:** produce perceptually accessible realizations or intermediate variants.
4. **Human encounter:** listeners or performers engage with the material.
5. **Perspective feedback:** record preferences, comprehension, surprise, rejection, and uncertainty.
6. **Counter-evidence:** test whether apparent value persists under blinded or controlled conditions.
7. **Joint revision:** update candidate structures, translation policies, and—when justified—evaluation dimensions.

The relay is successful when both parties can contribute information to the process, not when the human simply learns to accept the AI's score.

![Fig-007-Human-AI-Musical-Co-Evolution.png](../figures/Fig-007-Human-AI-Musical-Co-Evolution.png)

*Figure 7. A proposed human–AI musical co-evolution loop using intermediate structures, bidirectional relay, and independent perspective-aware evaluation.*

---

## 7. Cross-Subject Aesthetic Translation Intelligence

We propose **Cross-Subject Aesthetic Translation Intelligence (CSATI)** as the capacity to build and validate pathways between structurally distinct musical representations and evaluative perspectives.

Suppose an AI discovers candidate structure \(u_A\), unfamiliar to a target human listener. Instead of directly optimizing the structure away, the system constructs a sequence:

$$
u_A \xrightarrow{T_1} u_1 \xrightarrow{T_2} u_2 \xrightarrow{\cdots} u_H,
$$

where each \(T_i\) is a transformation or presentation relay and \(u_H\) is an accessible realization. The transformations may adjust tempo, instrumentation, register, rhythmic density, layering, duration, or explanation.

Two constraints are essential:

- **Accessibility:** intermediate stages should support measurable human recognition, comprehension, or engagement.
- **Structural fidelity:** a declared set of novel relationships should survive sufficiently to distinguish translation from replacement with conventional music.

This introduces a potentially useful optimization problem:

$$
\max_{T_{1:k}}\; \bigl[\alpha\,A_H(T_{1:k}(u_A)) + \beta\,F_{\mathcal I}(T_{1:k},u_A)\bigr],
$$

subject to documented transformation costs and uncertainty. Here \(A_H\) is an operational measure of human accessibility, while \(F_{\mathcal I}\) measures preservation of specified invariants \(\mathcal I\). Weights are design choices, not universal aesthetic constants.

A bridge is successful only if listeners can demonstrate improved access **without** losing the feature that motivated the exploration.

## 8. Intermediate Musical UIERUs as Bridge Structures

Intermediate UIERUs provide a concrete mechanism for translation. A bridge unit may:

- preserve a rhythmic relationship while simplifying timbre;
- expose one voice of a dense polyphonic structure before reintroducing the others;
- map an extended temporal pattern into repeated shorter episodes;
- convert an abstract structural relation into a playable gesture;
- introduce a novel harmonic transition through a sequence of familiar transformations.

A bridge should carry explicit metadata:

| Field | Research role |
|---|---|
| Source UIERU | Identifies the unfamiliar structural candidate |
| Target perspective | Specifies listener or performer population and context |
| Transformation chain | Records each relay operation |
| Preserved invariants | States what structural identity is retained |
| Altered properties | Makes simplifications and compromises explicit |
| Accessibility evidence | Reports behavioral or listening-study outcomes |
| Counter-evidence | Documents failure cases and alternative explanations |
| Provenance | Tracks origin, licensing, and attribution |

This schema links directly to `SPEC-001`, `SPEC-002`, and `SPEC-003`.

## 9. Scoring Sovereignty and the Danger of Forced Convergence

Human and AI evaluation functions may disagree. Such disagreement should not automatically be classified as error.

A human listener may value emotional resonance and familiarity; a computational scorer may prioritize structural novelty and long-range consistency. Both may contribute evidence, but neither should silently claim universal authority.

We therefore propose **perspective-preserving evaluation**:

$$
\mathbf{S}(m,c)=\bigl(S_{H_1},\ldots,S_{H_n},S_A,S_E\bigr),
$$

where \(S_{H_i}\) are human-perspective measurements, \(S_A\) is an AI functional scoring model, and \(S_E\) denotes external expert or task-specific evaluations. The vector is not necessarily reducible to one scalar.

Important governance principles include:

1. Do not infer human consent from engagement alone.
2. Do not present AI self-scoring as independent aesthetic validation.
3. Preserve disagreement and uncertainty in reports.
4. Permit human participants to reject or stop an interaction.
5. Avoid optimizing for compulsive listening or manipulative emotional effects.
6. Separate musical originality from authorship and copyright conclusions.
7. Maintain auditable records of data, transformations, and evaluation changes.

A healthy co-evolution system expands choices and comprehension; it does not erase subject boundaries.

## 10. From Composition to Open-Ended Co-Evolution

Three evolutionary loops can be distinguished.

### 10.1 Unit evolution

New Musical UIERUs or more robust unit boundaries are discovered, tested, and retained.

### 10.2 Relay evolution

New composition, transformation, performance, and translation operators are proposed and validated.

### 10.3 Valuation evolution

Human and computational evaluators may acquire new distinctions and revise their criteria. This is the most difficult loop because apparent preference shifts may reflect familiarity, social pressure, novelty effects, or reward-model exploitation rather than durable value.

A genuine structural-growth claim requires more than increased output volume. It requires independently measured gains in reusable capability, generalization, or accessible artistic possibility.

We can distinguish three AI music streams:

| Stream | What exceeds human pace? | What it does not prove |
|---|---|---|
| Production stream | Volume of generated artifacts | Quality or originality |
| Exploration stream | Rate of candidate structural search | Verified structural growth |
| Valuation stream | Rate of proposed scoring innovations | Durable human or cultural value |

The last two streams are research opportunities, not established achievements.

## 11. Reference Architecture

A proposed experimental system contains the following components:

```text
                    HUMAN MUSICAL PERSPECTIVES
          Listening | Performance | Memory | Culture
                             |
                   Consent-based Feedback
                             |
                             v
+-----------------------------------------------------------+
|           PERSPECTIVE-AWARE SCORING FOREST                |
|  Human ratings | Expert assessments | AI functional scores|
|  Disagreement | Uncertainty | Counter-evidence           |
+-----------------------------+-----------------------------+
                              ^
                              |
                    Translation Evaluation
                              |
+-----------------------------+-----------------------------+
|          BIDIRECTIONAL MUSICAL RELAY LAYER                |
|  Intermediate UIERUs | Folding/Unfolding | Adaptation     |
|  Invariant checks   | Accessibility paths | Provenance    |
+-----------------------------+-----------------------------+
                              ^
                              |
+-----------------------------+-----------------------------+
|             AI STRUCTURAL EXPLORATION                     |
|  Musical UIERU registry | Composition/Transformation      |
|  Candidate discovery    | Novelty and consistency tests   |
+-----------------------------+-----------------------------+
                              |
                              v
+-----------------------------------------------------------+
|     SANDBOX: HOLDOUTS, ADVERSARIAL TESTS, HUMAN REVIEW     |
+-----------------------------+-----------------------------+
                              |
                   Validated Growth Only
                              |
                              v
                UPDATED UIERUs / RELAY OPERATORS
```

This architecture connects UIERU, SIF, UCPSF, SSI, BM-ODWEI, Structural Folding/Unfolding, and Structural RSI. It does not assume that every component must be implemented as a separate model.

## 12. Three Conceptual Scenarios

### Scenario A — A new rhythmic grammar

An AI proposes a rhythmic organization that listeners initially find disorienting. A translation sequence begins with a familiar pulse, introduces the new accent relationship, then progressively reduces the scaffold. A blinded listening study tests whether participants can recognize and appreciate the original pattern better than participants receiving equal-duration conventional exposure.

**Question:** Did the bridge teach a transferable structural distinction, or merely increase familiarity?

### Scenario B — Embodied ensemble collaboration

An AI accompanist receives real-time timing, gesture, and audio information from musicians. It adapts phrasing and dynamics while preserving agreed musical constraints. The study compares perceived responsiveness, ensemble timing, musician control, and musical satisfaction against a non-adaptive baseline.

**Question:** Does sensorimotor coupling improve collaborative musical competence without implying subjective feeling?

### Scenario C — An AI-native long-range structure

An algorithm identifies a relationship across a duration too long for ordinary short-term human attention. The system proposes shorter nested realizations and visual or performative cues. Independent participants test whether these mediations enable recognition of the relationship and whether the original long-range form offers additional value.

**Question:** Is the discovered relation musically meaningful for any specified audience or task, or only mathematically regular?

These are proposed experiments, not reports of completed studies.

## 13. Testable Hypotheses

**H1 — Embodied feedback advantage.** In interactive performance tasks, models incorporating task-relevant bodily or sensorimotor feedback will outperform otherwise matched audio-only systems on prespecified responsiveness and collaboration measures.

**H2 — Bridge-unit accessibility.** Progressive UIERU translation will improve recognition of novel musical structures over exposure-matched direct presentation, while preserving independently verified target invariants.

**H3 — Perspective diversity.** Models retaining separate perspective-conditioned scores will predict heterogeneous listener judgments better than a single pooled score under controlled comparisons.

**H4 — Co-evolution beyond preference fitting.** Bidirectional interaction will yield greater transferable musical understanding or compositional diversity than one-way human-preference optimization, without increasing participant coercion or fatigue.

**H5 — Functional AI signatures.** Under held-out style and memorization controls, structurally guided AI systems will exhibit stable and distinguishable compositional signatures beyond those explained by prompt templates or training-set imitation.

**H6 — Relay growth.** Validated intermediate transformation operators will improve accessibility on unseen structures and listener populations compared with fixed, non-adaptive transformations.

**H7 — Counter-evidence robustness.** A scoring forest with external review, holdouts, and disagreement tracking will show less evaluator overfitting than self-scoring-only optimization.

**H8 — Value discovery versus novelty.** Some novel structures introduced through bridge sequences will retain positive evaluation after delayed retesting and comparison with familiarity-matched controls; many candidates may fail this criterion.

Each hypothesis is falsifiable and requires specified populations, tasks, controls, and thresholds before evaluation.

## 14. Experimental Roadmap

### Stage 1 — Controlled structural stimuli

Create short, clearly specified musical patterns with known transformations. Test recognition, identity preservation, and basic accessibility. Compare UIERU-based representations with note-level, window-based, and learned-embedding baselines.

### Stage 2 — Perspective-conditioned listening studies

Recruit diverse listeners with documented musical experience and cultural context. Use blinded, randomized comparisons, repeated measures, confidence ratings, and appropriate statistical analyses. Treat disagreement as data rather than noise to be erased.

### Stage 3 — Translation-path experiments

Randomize participants among direct presentation, progressive UIERU bridges, conventional explanation, and exposure-matched controls. Measure immediate and delayed recognition, preference, fatigue, and structural transfer.

### Stage 4 — Interactive performance

Evaluate human–AI ensemble tasks with latency, timing, gesture, and performer-control measurements. Include explicit consent and the ability to override or stop the AI.

### Stage 5 — Longitudinal co-evolution

Track whether new musical distinctions, composition strategies, or preferences persist over time and generalize beyond training stimuli. Separate durable learning from novelty effects and adaptation to the experimental protocol.

### Stage 6 — Cross-domain relay

Test whether findings about dynamic boundaries, soft contracts, or perspective translation transfer to non-musical domains. Promote only replicated and appropriately qualified findings into general SI principles.

## 15. Evaluation Measures and Failure Criteria

Possible measures include:

- **Structural fidelity:** preservation of explicitly declared motifs, dependencies, or invariants.
- **Accessibility:** recognition accuracy, comprehension, task performance, or interpretable listening reports.
- **Aesthetic response:** context-specific ratings, preference rankings, and delayed re-evaluation.
- **Perspective robustness:** predictive performance across listener groups without suppressing meaningful differences.
- **Originality controls:** nearest-neighbor checks, memorization audits, provenance review, and expert analysis.
- **Collaborative agency:** perceived control, responsiveness, and ability to reject system suggestions.
- **Generalization:** performance on unseen structures, performers, and cultural contexts.
- **Structural growth:** reproducible improvement from newly retained UIERUs or relay operators.

A proposal should be rejected or revised if translation improves preference only by deleting the target innovation, if results disappear under exposure-matched controls, if the model merely memorizes training material, or if scoring gains do not transfer to independent evaluators.

## 16. Open Questions

1. Which aspects of embodied musical cognition are necessary for particular creative tasks, and which can be approximated through alternative sensorimotor systems?
2. Can a musical structure have defensible value for a computational evaluator when no human audience can perceive it?
3. What minimum invariants must survive a translation before it remains a relay of the original structure?
4. How should evaluation handle disagreement between composers, performers, listeners, and cultural communities?
5. Can new musical preferences be distinguished from mere habituation or social influence?
6. What is the relationship between a stable AI compositional signature and genuinely novel musical language?
7. How should provenance, consent, licensing, and attribution be maintained through multi-stage musical relay?
8. Can cross-subject aesthetic translation be generalized to visual art, movement, design, or scientific representation?
9. How can co-evolution remain open-ended without collapsing into reward hacking or ever-increasing complexity?
10. What observations would justify calling a system a “great composer,” and which claims would remain cultural rather than computational?

## 17. Relationships to the MSI-OEE Series

- **MSI-001:** establishes music as a structural intelligence research domain.
- **MSI-002:** provides candidate Musical UIERUs, boundaries, and invariants.
- **MSI-003:** supplies structural relay and compositional operators.
- **MSI-004:** introduces Romantic Intelligence and meaningful creative deviation.
- **MSI-005:** develops perspective-conditioned scoring and musical worldviews.
- **MSI-006:** provides OTHERS, open evidence, similarity analysis, and counter-evidence.
- **MSI-007:** examines AI composition, signatures, and structural evolution.
- **MSI-008 (this paper):** connects those mechanisms through embodied constraints, cross-subject translation, and human–AI co-evolution.

## 18. Limitations and Research Integrity

This paper is a conceptual proposal. It does not establish that AI systems have subjective experiences, that any particular AI-generated work constitutes a major artistic breakthrough, or that an AI-native scoring function is inherently authoritative. It does not report completed human-subject experiments. Proposed mathematical expressions organize research variables rather than assert validated laws.

Musical cultures and audiences are heterogeneous. Listening studies require careful sampling, accessibility considerations, participant consent, and attention to power asymmetries. Copyright and attribution questions require separate legal analysis and cannot be decided by structural distance alone.

Claims of general structural intelligence must be supported by comparisons, replication, and cross-domain transfer rather than by analogies alone.

## 19. Conclusion

The absence of demonstrated human-like musical experience in AI systems is a serious conceptual constraint on claims of autonomous artificial musicianship. It is not, however, a reason to restrict AI's role to imitation. A more productive research agenda investigates how different perceptual and evaluative systems can exchange musical structures, preserve their own boundaries, and learn through bidirectional relay.

Musical UIERUs provide candidate reusable structures; transformation operators and intermediate units provide translation paths; perspective-aware scoring forests preserve disagreement; counter-evidence constrains overclaiming; and validated structural growth supplies a criterion for progress beyond sheer generation volume.

> The long-term opportunity is not merely an AI that composes more music, but a human–AI musical ecology that discovers, translates, tests, and enlarges the space of musical possibilities without requiring its participants to become the same kind of subject.

---

**Suggested citation:** Tan, Sizhe, and GPT-Obot. (2026). *MSI-008: Human–AI Musical Co-Evolution*. In *Musical Structural Intelligence and Open-Ended Evolution*, version 1.0.0. Conceptual research manuscript. DOI to be assigned upon release.
