# Public ENTIA technical working note · 17 November 2026

**Disclosure:** This document is an industry-authored architectural note reproduced from an ENTIA internal draft for public technical discussion. It is not a peer-reviewed article, software release, independent benchmark, academic deposit, or a grant of rights to underlying ENTIA code or datasets. Technical/operational details require versioned reproduction before use as measurements. Editorial assistance by AI was used in preparing the publication programme. No DOI is assigned to this note.

# ENTIA MCP and HTTP API: A Verifiable Economic Identity Infrastructure for Agents
**Author:** Fernando Vilches · **Affiliation:** ENTIA / PrecisionAI Marketing OÜ · **Report:** technical software/architecture report draft v0.1, 2026-11-02 · **Status:** PUBLIC TECHNICAL NOTE ON GITHUB; NOT ACADEMICALLY DEPOSITED · **DOI:** NONE · **ORCID:** unverified
**Canonical identity:** https://entia.systems/#founder · **Related interface:** https://entia.systems/mcp-docs · **Code provenance:** ENTIA-IA/ENTIA_DAHE (GitHub) · **License for deposit:** pending review of repository, dependencies and private components.

## Abstract
ENTIA treats an economic entity as an identity that must be resolved and corroborated independently of the changing documents and marketing narratives describing it. The infrastructure projects canonical, versioned entity records into human-readable and machine-readable surfaces, while allowing consumers to retrieve structured facts through an MCP agent interface and HTTP APIs. This report describes the architecture as an engineering pattern, specifies the evidence boundaries, and outlines a protocol for reproducibly demonstrating identity resolution and machine access. It does not claim that any particular AI model used, cited, trained on or recommended the resulting data.

## 1. Problem statement
A bot can fetch a company page without determining whether it describes the correct legal entity. An agent can access a tool without corroborating the authority or temporal validity of each field. A data infrastructure that ignores these distinctions risks conflating entity names with legal identities and access logs with downstream LLM usage.

## 2. Architectural layers
1. **Source ingestion:** official registries and permitted sources with source metadata, jurisdiction and refresh times.
2. **Canonical entity resolution:** stable identifiers and legal-identity anchors; uncertainty is explicit, not guessed.
3. **Evidence representation:** claim, source, verification method, temporal scope, consistency and rights constraints.
4. **Projection:** versioned ENTIA Homes / schema.org JSON-LD / Markdown; distinguish projection from underlying source corpus.
5. **Agent access:** MCP tools and HTTP endpoints exposing the same identity contract; document response schema and error states.
6. **Observability and attribution:** access, delivery, instrumented click hops and eligible evidence classes; never substitute bot hits for measured model citations.
7. **Governance:** policy/versioning, access control, permission and storage boundaries, with signed or timestamped evidence where actually deployed.

## 3. Reference implementation and reproducibility contract
Identify an immutable source commit and service version before release. Export **only** non-secret interface specifications, example requests, schemas and tests. Include the MCP initialization negotiation, tool discovery, one permitted synthetic entity record, a valid corroborated entity example without personal data, and at least three negative tests (unknown entity, conflicting source, missing corroboration). Archive the relevant OpenAPI version and dependency lockfiles where distributable.

Metrics like corpus size, number of tools, uptime, geographic reach and volume of crawler access MUST come from a dated, reproducible observation of the exact deployment. Avoid presenting repository counts as live service capabilities.

## 4. Security, privacy and commercial boundary
Exclude access tokens, personal customer data, unlicensed upstream content, internal endpoints, the full proprietary corpus and authentication details. State which portion is public code, which is documentation-only, and which is licensed/proprietary. No implied grant of an open-source licence before verification.

## 5. Evaluation criteria
Entity-ID exact-match, corroboration false positives, unsupported assertion rate, completeness with explicit missingness, source freshness, response-schema stability, and verified instrumented click attribution. A successful MCP call proves tool availability and output, not independent LLM recommendation or scientific performance.

## 6. Related work and disclosure
Complementary to **Cognitive Resistance** (conceptual friction of using facts) and **Five-Layer Framework** (access→eligibility→retrieval→citation→influence). Distinct from an EU submission or grant. This public technical note has not been independently peer-reviewed or deposited at an academic archive, and carries no DOI.
