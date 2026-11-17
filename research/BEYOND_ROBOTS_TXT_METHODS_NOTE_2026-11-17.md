# Beyond robots.txt: What Machine-Access Logs Can — and Cannot — Establish About AI-Use Rights

**Fernando Vilches** · Founder and Architect, ENTIA Systems  
**Publication form:** public methods/research note · 17 November 2026  
**Scientific status:** author-led technical note. **Not peer-reviewed. Not an accepted journal paper. Not the finalized longitudinal observational study. No DOI is assigned to this note.**

## Abstract

The Robots Exclusion Protocol (REP), standardized as RFC 9309, governs requests to paths by automated clients; it does not itself authorize access or encode every possible legal condition on subsequent uses of information. In AI-related environments, publishers may simultaneously make routes accessible, express reservations concerning particular content uses, serve versioned policy documents, and observe requests from clients that claim different names and purposes. These are separate facts. This note proposes an evidence model distinguishing **policy declaration, availability, HTTP delivery, explicit policy retrieval, interpretation and downstream use**. It explains which observations a publisher can test and what remains unobserved, and proposes a prospective experiment to investigate interoperability without mistaking correlation for proof of compliance, training or infringement. ENTIA's ongoing operational series motivates the work but is **not** published here as a frozen or certified statistical dataset.

## 1. Why the distinction matters

A `robots.txt` access rule addresses a crawler's handling of URI paths. Article 4(3) of Directive (EU) 2019/790 concerns express reservations of rights in a specific legal context. Article 53(1)(c) of Regulation (EU) 2024/1689 defines obligations for relevant general-purpose AI model providers concerning respect for copyright-related reservations. These are different technical and legal questions. The legal applicability of a reservation depends on rights, circumstances and conditions; the presence of a string does not settle the issue.

The publisher-side observation of a GET request is a network event. It is **not** evidence that a downstream model has incorporated a resource into training data, parsed a policy correctly, retrieved the information for an answer, cited it to a user, infringed a protected right, or complied with every applicable obligation. Conversely, absence of an observed policy-file request does not by itself establish non-compliance, because caching, intermediary access and alternative discovery mechanisms may exist.

## 2. Six separable levels

| Level | Claim that may be investigated | Evidence boundary |
|---|---|---|
| L0 Declaration | The publisher expressed a particular rights or use policy, with version, time and scope | Does not establish ownership of every item or legal effect in every circumstance |
| L1 Availability | A policy URL or document could be fetched under defined conditions | Does not prove the particular client fetched it |
| L2 Delivery | A logged HTTP response delivered bytes/status/headers to an observed request | Does not prove the client understood or retained them |
| L3 Retrieval | A client requested a policy artifact at an identifiable time | Does not prove its parser processed the relevant terms |
| L4 Interpretation | A supported client implementation recognized and acted on particular semantics | Requires implementer cooperation, controlled probe or another independent instrument |
| L5 Subsequent use | Content entered training, indexing, answer-time retrieval or redistribution | Requires purpose-specific independent evidence, not a request count |

A client identity inferred from a User-Agent label or shared-host ASN is not automatically authenticated. ENTIA's operational classification can inform exploratory measurement, but it cannot be equated with verified operator identity without corroboration.

## 3. Prospective experimental questions

**H1:** Do verified client implementations differ in how they treat non-REP rights-signal records while complying with REP path controls?

**H2:** Following a time-stamped rights-signal change on randomized synthetic pages, do route choices or status distributions differ from unchanged matched controls after adjustment for known operational factors? The null hypothesis is no attributable difference.

**H3:** Does a logged policy fetch predict any separately observable implementation behaviour? HTTP delivery alone should be reported as insufficient unless an independent test confirms a parser response.

**H4:** How sensitive are operator-level volume estimates to changing from self-declared labels to network-corroborated attribution and to excluding owned tests?

**Design proposal:** prospective baseline and follow-up intervals, randomized policy variants on non-sensitive dummy content, unchanged control hosts, independent authentication where available, exact policy/version hashes and edge response captures, hourly outcome windows, negative controls, placebo boundaries and missingness accounting. Report null results, uncertainty and sensitivity analyses. Do not characterize historical ENTIA logs as a prospectively preregistered experiment.

## 4. Data-quality disclosure

The underlying ENTIA investigation maintains different data populations: time-limited classified operational snapshots, original hourly event files and signed daily evidentiary indexes. They are **not interchangeable or additive**. A November 2026 validation recovered one missing day's raw compacted partitions and separately calculated a machine-external classification under the versioned `entia.medicion-operadores/v2.6` predicate; an older daily-acta methodology uses a different population definition. That partial check does not repair the entire historical index, validate 463 technical labels as authenticated vendors, freeze a longitudinal dataset, or prove a legal conclusion.

A publishable longitudinal dataset must have explicit start/end dates, unit of analysis, route/status definitions, owner-probe exclusions, missing-day treatment, immutable exact-byte SHA-256 hashes, source lineage, an attribution-tier dictionary, permissions and a privacy review. The authoritative source must be the approved frozen artifact, not an automatically refreshed `latest.json` snapshot.

## 5. Relationship to other ENTIA research

The *Five-Layer Framework* separates Access, Eligibility, Retrieval, Citation and Influence in measuring the interaction between AI systems and web resources. This note's L0–L5 levels address **rights-policy semantics and observation of machine access** instead. They overlap in observational discipline but do not claim to be the same taxonomy.

## 6. Limits, ethics and commercial-interest declaration

I founded ENTIA and have a commercial interest in governed business-identity infrastructure and machine-readable rights. Neither this note nor any associated policy correspondence implies endorsement, funding or research collaboration by European institutions. This text does not allege that any named vendor violated law, ignored a particular signal internally, or used ENTIA information for model training.

This note was prepared with AI-assisted editorial drafting under the author's research direction; formal academic review, legal advice, a licensing decision, a freeze of the larger dataset and an external scientific submission have **not** occurred.

## Primary sources

- IETF, *RFC 9309: Robots Exclusion Protocol* (2022): https://www.rfc-editor.org/rfc/rfc9309.html
- Directive (EU) 2019/790, Articles 3–4: https://eur-lex.europa.eu/eli/dir/2019/790/oj/eng
- Regulation (EU) 2024/1689, Article 53(1)(c): https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng
- ENTIA public observatory: https://entia.systems/bot
- ENTIA rights policy: https://entia.systems/.well-known/tdm-policy.json
- Vilches (2026), *Five-Layer Framework*: https://doi.org/10.5281/zenodo.22795758

**Publication is of this methods note only.** The empirical V3 manuscript and its dataset remain separate, under scientific and legal validation, and are not claimed as published or certified by this note.
