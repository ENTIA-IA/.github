# Cognitive Resistance: An Operational Framework for Verifiable Economic Identity in AI-Mediated Retrieval

**Fernando Vilches**  
Founder and Architect, ENTIA Systems — operated by PrecisionAI Marketing OÜ, Estonia

**Publication status:** public conceptual working paper v0.2 — 17 November 2026, hosted by ENTIA on GitHub. **Not peer-reviewed. Not deposited at an academic preprint archive. No DOI or verified ORCID assigned to this version.**  
**Canonical author identity:** https://entia.systems/#founder  
**Related public framework:** https://entia.systems/cognitive-resistance  
**Related published working paper:** *Five-Layer Framework for Measuring LLM and Agent Interaction with Web Sources* (2026), DOI https://doi.org/10.5281/zenodo.22795758

## Abstract

Large language models and retrieval systems increasingly encounter economic entities through websites, official registers, structured markup, APIs and agent-facing interfaces. Identifying which legal entity a source denotes is distinct from merely fetching a page or generating a plausible answer. This paper proposes **Cognitive Resistance** as a descriptive framework for the unresolved identification, reconciliation and verification work between an available representation and an evidence-supported economic-identity assertion. It decomposes this work into eight observable, potentially correlated dimensions: entity ambiguity, structural friction, provenance uncertainty, temporal uncertainty, contradiction burden, verification cost, access friction and semantic-format friction. Rather than claiming to know a language model's internal computation or predicting its recommendations, the framework develops external proxies and an experimental programme that could falsify specific expectations about factual correctness, unsupported assertions and verification effort. It distinguishes observable access from retrieval, citation and influence, and situates ENTIA as an industry-originated implementation setting, not as an independently validated scientific result.

**Keywords:** entity linking; economic identity; provenance; information retrieval; retrieval-augmented generation; evidence reconciliation; data quality; large language models; agent interfaces.

## 1. Research question and motivation

An automated assistant asked about a company may encounter multiple incompatible names, addresses, business registrations, webpages and outdated records. A technically accessible representation does not ensure that the system links a mention to the correct legal person, uses current claims, or recognizes contradictions. **Research question:** can lowering externally measurable representation and evidence-reconciliation burdens, while holding underlying facts and task difficulty constant, improve correctness, calibrated abstention and reproducibility in retrieval-mediated tasks concerning economic entities?

The proposal is narrower than a global theory of recommendation. It makes no deterministic claim that the entity with the least friction will always be cited, chosen or commercially preferred. Any such historical ENTIA wording is an **unvalidated seed hypothesis**, not an observed universal law; it must not appear as an empirical finding.

## 2. Relationship to existing scholarship

Entity linking has a substantial literature on ambiguous names and mapping mentions to knowledge-base entities. Shen, Wang and Han (2015) survey entity-linking problems, algorithms and evaluation, providing an established point of comparison rather than a claim that entity disambiguation originates with this paper [1].

Provenance representation is also not new: the W3C PROV-O Recommendation (2013) defines ways to express entities, activities, agents and their relationships [2]. This work does not invent provenance semantics; it asks which provenance gaps create observable verification burdens in a particular business-identity setting.

Retrieval-augmented generation already combines external retrieval with parametric generation. Lewis et al. (2020) describe RAG for knowledge-intensive NLP tasks [3]. This conceptual paper treats retrieval as a potentially observable research layer and refrains from inferring model-internal selection purely from a publisher's server logs.

The separate Five-Layer Framework [4] distinguishes **access, eligibility, retrieval, citation and influence**. Cognitive Resistance addresses characteristics of a representation and its associated verification work; it cannot replace independent evidence that any later layer occurred.

## 3. Definition and dimensions

**Cognitive Resistance (CR)** is the unresolved, task-dependent burden of identifying, interpreting and verifying an economic entity's claims before those claims can be used with stated evidentiary confidence. “Resistance” here is a conceptual label; it is **not** a measurement of hidden neural operations.

Eight candidate dimensions are defined at the unit of a **task–entity–representation–time** tuple, not as an innate property of a company.

| Symbol | Dimension | Example observable proxy |
|---|---|---|
| E | Entity ambiguity | Competing legal-person candidates remaining after identifier resolution |
| S | Structural friction | Parser transformations needed to recover specified fields |
| P | Provenance uncertainty | Fraction of tested claims missing attributable source and verification method |
| T | Temporal uncertainty | Fraction of tested claims without interpretable valid-from, valid-to or observed-at |
| C | Contradiction burden | Number/severity of unresolved conflicting source assertions for the same field |
| V | Verification cost | Human adjudication minutes or external source lookups under a fixed protocol |
| A | Access friction | Failed/blocked/ambiguous retrieval attempts needed to obtain the representation |
| F | Semantic/format friction | Field-mapping failures across human HTML, JSON-LD, Markdown and API payloads |

Possible empirical models may estimate a function of these variables, interactions and task/context controls. **No canonical weights, parameter values, linearity, independence assumptions or universal ordering are justified at this stage.** Comparing ENTIA commercial Risk Score v6, v6.1 or v6.2 values to this construct without an explicit bridge study would be invalid.

## 4. Falsifiable hypotheses

**H1 — identity ambiguity:** paired representations anchored to verified legal-person identifiers reduce cross-entity factual misattributions on a predeclared query set relative to ambiguous-name-only variants.

**H2 — provenance and time:** field-level source, method and validity annotations reduce independently scored unsupported definitive assertions, subject to comparable content and retrieval availability.

**H3 — conflict surfacing:** explicit unresolved-conflict states improve calibrated abstention versus silent source preference when evidence genuinely conflicts.

**H4 — boundary condition:** lower external verification burden does **not necessarily** increase mention, recommendation, citation, web visits or conversions. These are different dependent variables requiring their own instruments.

**H5 — representation invariance:** where HTML, JSON-LD, Markdown and API express equivalent facts, independently scored factual answers should be less variable in the treatment with coherent canonical identifiers and explicit field provenance. This is an empirical question, not a built-in performance promise.

## 5. Proposed experimental protocol (prospective)

### 5.1 Sample and treatments
Create an entity sample spanning jurisdictions, legal forms, bilingual name collisions, stale records, contradictory sources and complete/partial identifiers. Pre-register inclusion/exclusion rules, sampling seed and source-license eligibility. Preserve a held-out evaluation set. Use **synthetic or authorized public facts** for examples where necessary, never inferentially invented official IDs.

For each task–entity pair, construct at least two representation conditions: (A) unstructured or ambiguous but factually equivalent baseline; (B) canonical identifiers with machine-readable provenance, dates and explicit conflicts. Factorial variants may isolate components E/P/T/C without changing underlying truth. Record checksums of the presented bytes and prevent leakage across treatment and control hosts.

### 5.2 Measurement and outcomes
Predefine a primary endpoint such as cross-entity factual error rate under blinded adjudication, and secondary endpoints including unsupported assertion rate, abstention calibration, entity match accuracy, human verification minutes, consistency across repeated runs, and measurable retrieval/citation only where the instrument truly exposes them. Record model name/version, query, timestamp, access regime, sampling configuration, output, latency, availability and exclusions.

**Access telemetry alone cannot establish retrieved context, operator comprehension, training, answer-time source use or commercial influence.** A self-declared User-Agent without independent authentication does not prove the vendor's identity.

### 5.3 Assignment, controls and uncertainty
Randomize task–condition assignment, rotate order, use blinded reviewers and an adjudication rubric. Run matched negative controls and placebo representations. Group repeated observations by entity and task in statistical inference to avoid falsely treating correlated samples as independent. Report effect sizes with uncertainty intervals, multiple-testing treatment, missing partitions and negative/null results. Choose sample size only after an explicit power or precision analysis using a declared minimally meaningful effect; **none is claimed here**.

### 5.4 Reproducibility and data release
Release a protocol, test prompts, synthetic/authorized entity representations, anonymized adjudications, code/dependency lockfiles, version and consent/rights statements, and SHA-256 manifests when approved. Keep restricted event-level telemetry, personal data, proprietary corpus extracts and secrets out of the public supplement. Versioned public aggregate results must describe their population, denominators, noncoverage, attribution confidence and time cutoff. For any generated article, disclose substantive AI drafting assistance and human author review in accordance with venue rules.

## 6. Validity threats and disconfirming results

A model may benefit from standardized structure without using the declared provenance; that would not validate a semantic account of “Cognitive Resistance.” Some tools may ignore JSON-LD. A task may be answerable from parametric memory or unrelated sources. Entity difficulty, corpus coverage, language, vendor-side changes, rate limiting, caching and retrieval policies may confound effects. Overexposure to treatment data during prompting could bias a test. Genuine failures and effects limited to one system must be reported without universalization.

The construct may prove redundant with existing data-quality or entity-linking variables; discriminant validity should be tested. The commercial desirability of ENTIA's architecture does not establish incremental scientific novelty.

## 7. Ethics, commercial interest and publication status

The author founded ENTIA, the infrastructure proposed as an implementation context, and has a commercial interest in machine-readable business identity and verification. No external scientific endorsement, public funding, independent experimental validation or peer review is asserted. This document is a **theory and preregistration-plan draft**, not a registration receipt, benchmark result or published scholarly article. The research hypotheses, software implementation and any future underlying dataset must be separately evaluated. Licensing and a final author-approved deposition version remain undecided.

## References

1. Shen, W., Wang, J., & Han, J. (2015). Entity Linking with a Knowledge Base: Issues, Techniques, and Solutions. *IEEE Transactions on Knowledge and Data Engineering*, 27(2), 443–460. DOI: https://doi.org/10.1109/TKDE.2014.2327028
2. W3C (2013). *PROV-O: The PROV Ontology*. W3C Recommendation, 30 April 2013. https://www.w3.org/TR/prov-o/
3. Lewis, P. et al. (2020). Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks. *Advances in Neural Information Processing Systems*, 33. https://proceedings.neurips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html
4. Vilches, F. (2026). *Five-Layer Framework for Measuring LLM and Agent Interaction with Web Sources*, version 0.2. ENTIA research working paper. https://doi.org/10.5281/zenodo.22795758

**Public-release boundary:** This is an openly readable conceptual working paper on the ENTIA organization's public GitHub repository, not a journal article or institutional endorsement. Text preparation used AI-assisted drafting under the author's direction; independent scientific peer review, formal academic deposit and licensing decisions remain outstanding. No permission to reuse proprietary ENTIA datasets or code is granted by the publication of this note.
