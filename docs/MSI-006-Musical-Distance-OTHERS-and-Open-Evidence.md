# MSI-006 — Musical Distance, OTHERS, and Open Evidence

**Project:** Musical Structural Intelligence and Open-Ended Evolution (MSI-OEE)  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual research framework and falsifiable experimental agenda  
**Related documents:** MSI-002, MSI-004, MSI-005, MSI-007; CASE-002; SPEC-004

## Abstract

Musical similarity is not a single property. Two passages may share notes but differ in musical function; two performances may sound related despite changes in key, tempo, instrumentation, or expressive timing; and two listeners may disagree about whether a resemblance is distinctive or commonplace. This paper proposes an **open-evidence approach to musical distance** grounded in Musical UIERUs (Universal Intelligence Evolution and Relay Units), perspective-conditioned scoring, and the **OTHERS** residual evidence space introduced in the Beyond Matching and Open Directional/Weak Evidence Intelligence research line. The proposal separates observable feature distances, transformation-aware structural correspondence, contextual distinctiveness, perceptual judgments, and provenance evidence. Rather than asserting that these can always be reduced to a metric, it treats musical comparison as an auditable, task-specific inference problem with uncertainty and counter-evidence. An OTHERS-to-explicit-feature research loop is developed to identify missing musical descriptors, test them against held-out data, and promote validated discoveries into reusable structural operators. A staged experimental roadmap addresses motif recognition, similarity retrieval, perceptual disagreement, and carefully bounded analysis of alleged copying. The paper makes no claim to automate legal infringement determinations.

**Keywords:** musical structural intelligence; Musical UIERU; musical similarity; OTHERS; open evidence; perspective distance; transformation invariance; perceptual evaluation; counter-evidence; music information retrieval; structural learning

---

![Fig-006-Musical-Distance-and-OTHERS.png](../figures/Fig-006-Musical-Distance-and-OTHERS.png)

*Figure 6. Musical similarity as an open-evidence process: residual disagreement motivates testable hypotheses and counter-evidence rather than unsupported conclusions.*

---

## 1. The Central Problem: Similarity Is Not One Number

A melody can be transposed and remain recognizably the same musical idea. A short rhythmic figure can occur independently in thousands of works. Two excerpts can share pitch contours but create strikingly different experiences because of harmony, timing, instrumentation, or musical context. Conversely, listeners can perceive kinship between passages whose surface-level note alignment is poor.

These observations create three distinct questions:

1. **Descriptive similarity:** What observable musical properties do two excerpts share?
2. **Functional or perceptual similarity:** In a specified musical context and for a specified subject, do the passages play comparable roles or evoke comparable perceptions?
3. **Historical or legal inference:** Is there evidence of copying, source dependence, or legally actionable appropriation?

The questions may inform one another, but they are not interchangeable. In particular, neither a high machine-similarity score nor a human impression of resemblance, by itself, establishes copying or copyright infringement.

**Research thesis:** A useful musical comparison system should be *structurally informed, perspective-conditioned, evidence-open, uncertainty-aware, and falsifiable*.

## 2. Why Conventional Distance Is Necessary but Insufficient

### 2.1 Feature spaces

Common representations include pitch sequences, interval contours, chroma, rhythm and onset patterns, harmonic labels, timbral embeddings, spectral descriptors, and learned audio or symbolic embeddings. For an aligned feature representation \(\phi\), a conventional distance might be

$$
D_{\phi}(A,B)=\lVert\phi(A)-\phi(B)\rVert_2.
$$

This is useful only to the extent that \(\phi\) retains the properties relevant to the question. A model optimized for acoustic similarity may overemphasize instrumentation; a pitch-only model may miss rhythmic identity; a broad embedding may collapse distinctions crucial to musicologists.

### 2.2 Alignment and invariance

Musical time is elastic. Phrases may be ornamented, stretched, truncated, reharmonized, or moved to another register. Dynamic time warping, edit distances, and alignment algorithms can help, but the chosen invariances determine what the comparison ignores.

A transformation-aware structural score can be written as

$$
D_{\mathrm{struct}}(A,B\mid C,P)
=\inf_{T\in\mathcal{T}(C,P)}
\left[d\bigl(\phi(T(A)),\phi(B)\bigr)+\lambda\,\mathrm{cost}(T)\right].
$$

Here \(C\) is musical context, \(P\) is an evaluation perspective, \(\mathcal T\) is an explicitly documented set of admissible transformations, and \(\mathrm{cost}(T)\) penalizes implausibly elaborate transformations. Without this penalty, an unrestricted transformation family could make unrelated works appear similar.

This quantity is generally a **task-dependent dissimilarity**, not necessarily a mathematical metric: symmetry, triangle inequality, and identity of indiscernibles may fail.

### 2.3 Musical UIERUs as comparison objects

MSI-002 proposes candidate units such as motifs, phrases, rhythmic gestures, harmonic patterns, and context-dependent expressive structures. A Musical UIERU is more than a contiguous note fragment: its proposed identity may involve its function, transformations, relay affordances, and contextual dependencies.

A comparison system should distinguish:

- **Surface identity:** near equality of an encoded passage.
- **Structural identity:** correspondence under a justified transformation family.
- **Functional identity:** comparable role in a phrase or larger composition.
- **Perceptual identity:** recognition or judged similarity by specified listeners.
- **Historical identity:** a supported source or transmission relationship.

None of these identities should be silently substituted for another.

## 3. The OTHERS Principle

### 3.1 Open evidence rather than an arbitrary extra weight

Following the BM-ODWEI perspective, musical comparison can be represented schematically as

$$
\mathcal E(A,B\mid C,P)
=\{E_{\mathrm{matched}},E_{\mathrm{structural}},E_{\mathrm{contextual}},E_{\mathrm{provenance}},E_{\mathrm{OTHERS}}\}.
$$

\(E_{\mathrm{OTHERS}}\) denotes **unexplained or unmodeled evidence**, not a magically observable scalar and not permission to add a favorable score after seeing the desired outcome. It can be represented as documented disagreements, missing descriptors, anomalous residuals, or candidate mechanisms awaiting validation.

The decision procedure is then

$$
\widehat{Y}=g_{P,C}(\mathcal E;\theta),
$$

where \(Y\) is a precisely defined target, such as human-rated motif similarity, not a generic verdict of plagiarism.

### 3.2 Four candidate residual classes

**Structural residual:** Listeners hear a relationship that pitch/rhythm/harmony descriptors fail to explain; perhaps a shared developmental gesture or hierarchical pattern is missing.

**Perceptual residual:** The same musical features receive different similarity ratings under different listening tasks, expertise levels, or cultural backgrounds.

**Contextual residual:** A commonplace pattern in one style is distinctive in another; neighboring phrases change the salience of a resemblance.

**Provenance residual:** Documentary evidence suggests a source relationship despite limited measurable similarity, or independent creation is plausible despite a strong resemblance.

These categories are provisional research partitions. They should be revised if experiments show that they are redundant or unhelpful.

## 4. Distinctiveness, Base Rates, and the Common-Motif Problem

A shared fragment is more informative when it is rare in a relevant comparison population than when it is a common musical convention. One possible distinctiveness descriptor is

$$
I(U\mid C)=-\log\bigl(P(U\mid C)+\epsilon\bigr),
$$

where \(U\) is a candidate Musical UIERU, \(C\) defines a relevant corpus, and \(\epsilon\) stabilizes the expression. The estimated probability depends strongly on corpus sampling, segmentation, genre, period, and representation. Rarity is evidence of distinctiveness, **not proof of copying, originality, or legal protectability**.

A responsible comparison report should include the reference corpus, confidence interval or calibration uncertainty, known sampling biases, and common-pattern counterexamples. Apparent uniqueness can disappear when the search population broadens.

## 5. Perspective-Conditioned Musical Distance

MSI-005 emphasizes that a composer's, performer's, listener's, and cultural community's Scoring Forests need not coincide. We therefore propose

$$
D_P(A,B\mid C,T)=h_P\bigl(\mathbf d(A,B),C,T,\mathbf u\bigr),
$$

where \(\mathbf d\) is a vector of documented comparisons, \(T\) is the evaluation task, and \(\mathbf u\) represents uncertainty and unresolved evidence. The function \(h_P\) should be learned or calibrated against observations for the specified perspective, not declared universal.

### 5.1 Separate tasks

- **Recognizability:** Does a listener recognize a transformed motif?
- **Similarity rating:** How related do two passages sound?
- **Structural correspondence:** Do expert annotations support a shared construction?
- **Expressive equivalence:** Do passages serve comparable emotional or dramatic functions?
- **Source inference:** What historical evidence supports or contradicts derivation?

Different tasks require different labels, validation criteria, and thresholds. Averaging them into a single opaque score would erase precisely the distinctions this research seeks to study.

### 5.2 Disagreement is data

A novice listener, trained musician, and style specialist may disagree for principled reasons. Report distributions, subgroup patterns, and inter-rater agreement; do not automatically treat the majority response as objective truth. An AI model's divergence from human judgments is a *candidate diagnostic signal*, not automatic evidence of a missing musical law.

## 6. Human Hearing as a Research Instrument, Not an Oracle

Human listening integrates expectation, memory, attention, learned style, and auditory grouping. That makes it a valuable measurement channel, but also a noisy and context-sensitive one.

A rigorous listening protocol should:

1. Pre-register the question and similarity dimension.
2. Use randomized, level-matched audio and appropriate playback controls.
3. Include both expert and nonexpert listeners where relevant.
4. Record confidence, familiarity, and cultural or musical background with consent.
5. Use pairwise ratings and triplet comparisons where appropriate.
6. Include positive controls, negative controls, and ambiguous cases.
7. Measure test–retest stability and inter-rater variation.
8. Separate descriptive resemblance from claims of copying or infringement.

Where possible, pair perceptual ratings with symbolic analysis and blinded expert review. No single measurement channel should be treated as infallible.

## 7. Similarity, Copying, and Copyright: A Necessary Boundary

Copyright standards depend on jurisdiction, the protected work, the claimed elements, and the evidence. In U.S. disputes, for example, courts may consider protectable expression, evidence of copying, expert analysis, and forms of listener assessment; there is no universal numerical threshold that determines infringement. Other jurisdictions use different tests.

For research purposes, maintain separate outputs:

| Output | Question | Permissible conclusion |
|---|---|---|
| Acoustic similarity | How similar are the recordings? | Measured resemblance under stated features |
| Musical-structural similarity | What compositional relationships exist? | Documented correspondences and alternatives |
| Distinctiveness | How unusual are shared patterns? | Corpus-conditioned rarity estimate |
| Provenance analysis | Is there evidence of a source relationship? | Evidence summary with uncertainty |
| Legal assessment | Does conduct satisfy applicable legal elements? | Requires jurisdiction-specific legal analysis |

A model may help organize evidence; it must not label a work legally infringing solely from a similarity score. Publicly disputed examples also carry selection bias and uncertain ground truth. Where recordings, scores, or annotations are copyrighted, obtain suitable permissions or use licensed and public-domain materials.

## 8. OTHERS-to-Structure: The Open Evidence Growth Loop

The proposed growth process is:

$$
\text{Observed Disagreement}
\rightarrow \text{Residual Audit}
\rightarrow \text{Candidate Explanation}
\rightarrow \text{Controlled Test}
\rightarrow \text{Counter-Evidence}
\rightarrow \text{Validated Feature or Rejection}.
$$

**Step 1 — Observe.** Identify systematic failures of a specified baseline, with uncertainty intervals and replicates.

**Step 2 — Audit.** Rule out annotation errors, recording artifacts, training leakage, data imbalance, and confounded task instructions.

**Step 3 — Hypothesize.** Propose a new descriptor, transformation operator, context variable, or Musical UIERU boundary.

**Step 4 — Test.** Compare the proposal with strong baselines under held-out composers, works, styles, and listeners.

**Step 5 — Challenge.** Search for counterexamples and assess robustness under alternate representations and reference corpora.

**Step 6 — Promote or reject.** Promote only reproducible, interpretable, useful improvements to an explicit feature registry, relay operator library, or UIERU specification. Otherwise retain the residual as unresolved or reject the hypothesis.

This is **structural growth**, not merely the accumulation of embedding dimensions or more parameters.

## 9. Reference Architecture

A candidate system consists of six layers:

1. **Input and provenance layer:** Audio, symbolic scores, metadata, licensing, transformations, and source traceability.
2. **Perception layer:** Pitch, rhythm, harmony, timbre, phrasing, performance, and learned representations.
3. **Musical UIERU layer:** Candidate unit segmentation, hierarchy, identity, invariants, and uncertainty.
4. **Comparison layer:** Feature distances, alignment, admissible transformations, distinctiveness, and contextual evidence.
5. **Perspective Scoring Forest:** Task- and subject-conditioned scoring, disagreement modeling, confidence calibration, and human feedback.
6. **Open evidence governance:** OTHERS registry, adversarial sandbox, counter-evidence, versioned experiments, and validated structural promotion.

Each output should carry a **comparison contract** specifying target task, unit of analysis, transformation allowances, reference population, perspective, model version, uncertainty, and limitations.

## 10. Experimental Program

### Experiment A — Controlled motif transformations

Create or license short motifs and apply transposition, octave displacement, tempo scaling, rhythmic ornamentation, reharmonization, instrumentation changes, and combinations thereof. Obtain blinded recognizability and similarity ratings. Compare exact matching, dynamic time warping, symbolic features, audio embeddings, and UIERU-aware models.

**Primary test:** Does explicit structural modeling improve performance on held-out transformation combinations without inflating false positives on unrelated motifs?

### Experiment B — Common patterns versus distinctive combinations

Construct matched pairs that share frequent stylistic conventions and pairs that share rarer multi-feature configurations. Stratify by genre and reference corpus.

**Primary test:** Does calibrated distinctiveness improve discrimination beyond similarity alone, and does that improvement survive corpus shifts?

### Experiment C — Perspective disagreement

Collect pairwise and triplet judgments from different listener groups under explicit task prompts. Compare a pooled model with perspective-conditioned models.

**Primary test:** Does perspective conditioning improve out-of-sample calibration while preserving meaningful disagreement rather than overfitting identities?

### Experiment D — OTHERS discovery

Identify repeatable model–human disagreements; propose one new structural feature at a time; pre-register hypotheses; evaluate on held-out music and alternate annotator groups.

**Primary test:** Does a newly promoted feature reduce error or improve explanatory power under strict controls for model capacity and computation?

### Experiment E — Provenance as a separate task

Use documented source–derivative pairs where lawful and reliable, alongside independently created look-alikes and shared-convention controls. Evaluate whether provenance evidence contributes beyond similarity, while reporting that provenance labels are not legal outcomes.

**Primary test:** Can the system separate structural resemblance from documented source relationship without claiming legal certainty?

## 11. Testable Hypotheses and Falsification Conditions

| ID | Hypothesis | Supporting observation | Falsification or serious challenge |
|---|---|---|---|
| H1 | UIERU-aware comparison improves transformed motif retrieval | Better held-out retrieval and calibration at matched compute | No gain over tuned symbolic/audio baselines |
| H2 | Contextual distinctiveness adds useful information | Reduced false positives for commonplace patterns | Gain vanishes after controlling for genre and corpus |
| H3 | Perspective-conditioned scoring improves perceptual prediction | Lower out-of-sample error and calibrated uncertainty | No improvement, or gains only through group leakage |
| H4 | Human–model disagreement reveals discoverable missing features | Reproducible new descriptors improve unseen cases | Residuals explained by noise, leakage, or artifacts |
| H5 | Transformation penalties improve meaningful correspondence | Better precision at fixed recall than unrestricted matching | Penalties systematically suppress legitimate transformations |
| H6 | Counter-evidence governance prevents spurious structural promotion | Fewer false discoveries across repeated candidate tests | No reduction relative to standard validation controls |
| H7 | Provenance and resemblance are separable inference tasks | Distinct predictors and error profiles | Data cannot reliably identify independent evidence channels |
| H8 | Explicit uncertainty improves downstream human decisions | Better calibrated confidence and fewer overconfident errors | Confidence intervals remain miscalibrated or unhelpful |

These are research propositions, not reported findings.

## 12. Evaluation and Reproducibility

Recommended metrics include precision–recall and average precision for retrieval; calibration error and proper scoring rules for probabilistic outputs; rank correlation for similarity judgments; agreement statistics and variance decomposition for human ratings; false-positive rates under common-pattern controls; and ablation gains for proposed OTHERS-derived features.

To avoid circular evaluation:

- Split by musical work and, where feasible, by composer, style, and transformation family.
- Keep evaluation excerpts and annotations out of feature-discovery loops.
- Use equal-budget and parameter-matched baselines.
- Record all preprocessing, alignment, and transformation choices.
- Publish negative results and failed hypotheses.
- Report performance across musical traditions rather than implying a single universal canon.
- Audit licensing, provenance, privacy, and consent.

For OTHERS promotion, require at least one independent validation dataset or genuinely held-out experimental condition.

## 13. Connections to the Broader SI Research Program

**UIERU:** Musical transformations test whether reusable intelligence units can maintain identity under soft, context-dependent boundaries.

**SIF:** The comparison pipeline maps naturally onto perception, localization, per-node structural evaluation, and control/governance.

**UCPSF:** Musical judgments provide a concrete domain for multi-operator Scoring Forests and perspective-aware optimization.

**SSI:** Disagreement between listeners illustrates subject boundaries and scoring sovereignty without collapsing distinct experiences into one objective value.

**BM-ODWEI:** OTHERS becomes an auditable, experimentally actionable residual evidence program rather than an unexplained correction term.

**Structural RSI:** Validated missing-feature discovery offers a bounded test of recursive improvement under evaluator governance and anti-Goodhart controls.

The relay must be bidirectional: music can borrow SI concepts, but only validated music-domain findings should become candidates for general SI principles.

## 14. Limitations and Open Questions

1. What is the most appropriate granularity of a Musical UIERU across genres and musical traditions?
2. Can a structural invariant be operationally specified without erasing expressive differences?
3. How should we represent nontransitive, asymmetric, or context-dependent perceptual similarity?
4. When is an OTHERS residual a new mechanism, and when is it merely measurement noise?
5. Can distinctiveness estimates be robust to incomplete and culturally biased corpora?
6. How do we distinguish explainable musical correspondence from post hoc pattern finding?
7. Can cross-perspective translation improve understanding without enforcing one group's preferences?
8. What evidence is required before a domain-specific scoring operator is generalized beyond music?

No experiment proposed here establishes machine consciousness, subjective musical pleasure, or the legal status of a musical work.

## 15. Conclusion

Musical distance is best treated not as one universal ruler, but as a family of documented comparisons embedded in musical structure, context, perspective, and evidence. Musical UIERUs offer candidate objects for transformation-aware analysis. Perspective Scoring Forests explain why judgments can legitimately diverge. OTHERS identifies where current representations fail, while counter-evidence and held-out tests determine whether a proposed explanation deserves promotion into reusable structural knowledge.

The central contribution is a research discipline: **turn unexplained musical resemblance or disagreement into testable structural hypotheses, not unsupported certainty**. If successful, this discipline could improve music information retrieval and AI-assisted composition while offering a concrete experimental pathway for open structural intelligence growth.

---

## Suggested Figure

**Fig-006-Musical-Distance-and-OTHERS.png** — A multi-layer evidence architecture showing surface feature distances, transformation-aware Musical UIERU comparison, perspective scoring, distinctiveness, provenance, an OTHERS residual registry, counter-evidence, and validated feature promotion. Place after Section 8 or Section 9.

## Companion Artifacts

- `cases/CASE-002-Musical-Similarity-and-OTHERS.md`
- `specs/SPEC-004-OTHERS-Evidence-and-Validation.md`
- `TESTABLE-HYPOTHESES.md`
- `VALIDATION-ROADMAP.md`

## Research Note

This document is a conceptual proposal. Formulas are schematic unless tied to a specified implementation and dataset. Legal discussion is contextual and is not legal advice. Empirical claims require independent testing and should not be inferred from the architecture alone.
