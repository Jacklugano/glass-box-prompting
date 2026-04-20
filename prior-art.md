# Prior art

Glass-Box Prompting builds on and is informed by several existing bodies of work. This document acknowledges these influences openly and clarifies what GBP adds to the existing landscape.

---

## Closest relative: llms.txt

**llms.txt** was proposed by Jeremy Howard (Answer.AI) in September 2024 as a transparency convention for technical documentation: a standardized file at the root of a website containing a curated, LLM-friendly summary of the site's content.

**Similarities with GBP:**

- Both treat transparency toward AI as a first-class concern
- Both propose publication at a canonical URL (llms.txt at `/llms.txt`, GBP at issuer-defined paths)
- Both favor human-readable formats over proprietary machine-only schemas
- Both are distributed via website publication rather than centralized registries

**Differences:**

- **Target audience**: llms.txt addresses technical documentation read primarily by developers and AI agents working on technical tasks. GBP addresses commercial, contractual, and professional documents read by non-technical end users (customers, patients, contractors).
- **Content focus**: llms.txt curates summaries and pointers to existing technical content. GBP declares semantic conventions and interpretive anchors for a specific document domain.
- **Protocol scope**: llms.txt is scoped per-website. GBP is scoped per-issuer and versioned to specific documents.
- **Ethical framing**: GBP's founding principles explicitly address the prompt-injection concern and anchor conventions to external public standards. llms.txt's concerns are primarily practical rather than ethical.

GBP can be seen as a sibling protocol addressing a different document class with additional semantic and ethical requirements.

---

## Structured data: schema.org

**schema.org** (Google, Microsoft, Yandex, Yahoo, 2011) provides a vocabulary of types and properties that web content can use to declare its meaning to search engines and other structured-data consumers.

**Relation to GBP:**

- The GBP machine-readable companion (`glass-box.jsonld`) uses JSON-LD with schema.org vocabulary for structured representation
- schema.org's principle — "declare the meaning of your content rather than leave consumers to infer it" — is foundational to GBP
- However, schema.org has no equivalent of GBP's "interpretive conventions" or "domain-specific anchors" — it focuses on what things *are*, not on how to interpret them

GBP does not replace schema.org. It uses schema.org vocabulary where applicable and adds domain-specific semantic layers.

---

## Semantic web: dereferenceable URIs

The **Semantic Web** principle (Tim Berners-Lee, World Wide Web Consortium, from approximately 2001) proposes that every concept should be identified by a URI that resolves to a machine-readable definition of that concept.

**Relation to GBP:**

- GBP shares the core idea: a semantic reference that can be resolved to its authoritative definition
- GBP's "published conventions" are a simplified, human-and-AI-readable form of dereferenceable references
- GBP does not require formal RDF/OWL ontologies; it prioritizes accessibility for non-technical issuers

The Semantic Web vision remained niche partly because of the high technical barrier to adoption. GBP aims to capture some of the same benefits with a dramatically lower barrier to adoption.

---

## Healthcare informatics: HL7 FHIR

**HL7 FHIR** (Fast Healthcare Interoperability Resources, Health Level Seven International, from 2014) is the leading standard for exchanging healthcare data in structured, machine-readable form. FHIR uses StructureDefinition resources — essentially dereferenceable URIs that define the meaning of clinical concepts.

**Relation to GBP:**

- FHIR demonstrates that semantic interoperability at scale is achievable in a regulated professional domain
- The distributed multi-party extension of GBP (planned, see ROADMAP) is conceptually similar to FHIR's federated institutional model
- Future high-stakes domain extensions of GBP (healthcare specifically) must integrate with FHIR rather than compete with it — FHIR provides clinical data structure, GBP would provide LLM-friendly semantic anchoring over it

GBP's healthcare extension, when developed with appropriate domain partners, would be a presentation and disambiguation layer above FHIR, not a replacement for it.

---

## Generative Engine Optimization (GEO)

**GEO** is an emerging practice and commercial category focused on optimizing content for generative AI systems (ChatGPT, Claude, Gemini, Perplexity) rather than for traditional search engines. Several companies and consultants have positioned themselves in this space during 2024-2025.

**Relation to GBP:**

- Both recognize that AI systems now mediate access to information and that content producers benefit from considering how AI systems read their content
- GEO tends toward marketing-oriented optimization (how to get cited, how to get included in AI answers). GBP is oriented toward semantic correctness (how to ensure AI interprets the document as the issuer intended)
- GBP explicitly rejects optimization patterns that influence AI behavior beyond transparent documentation — the "Documentation, not instruction" principle directly addresses this

GBP and GEO operate in adjacent spaces with partially overlapping concerns but different ethical orientations.

---

## Document-level transparency practices

Several unrelated practices in professional document design contribute to the context in which GBP emerges:

- **Plain language movements** (legal, medical, financial) aim to make professional documents comprehensible to non-experts
- **Open data initiatives** (government, scientific) promote public availability of interpretable datasets
- **Standard cross-referencing** (ISO, industry bodies) documents how professional practices anchor to shared references

GBP synthesizes elements from these practices into an AI-aware framework for commercial documents.

---

## What GBP adds

Relative to the prior art above, Glass-Box Prompting's distinguishing contributions are:

1. **Application to consumer-facing professional documents**: most prior art addresses technical, clinical, or developer-oriented content. GBP addresses the documents ordinary people read — commercial quotes, contracts, bills.

2. **Explicit ethical framing against prompt injection**: GBP's founding principles directly address the structural similarity between AI-directed document instructions and prompt injection, and resolve it through the "documentation, not instruction" pattern.

3. **Anchoring to national and sectoral public standards**: GBP's "interoperability" principle encourages anchoring to externally-verifiable authorities (CPN, NIBT, TARDOC, FHIR) rather than vendor-internal conventions, making the protocol semantically robust across issuers.

4. **Multilingual federated scenarios**: the planned Distributed Glass-Box variant addresses ecosystems where multiple issuers operate in multiple languages, drawing on federated publication patterns familiar from other domains.

---

## Acknowledgments

Sincere intellectual gratitude to:

- **Jeremy Howard** and the Answer.AI team for the llms.txt proposal, which demonstrated that simple, human-readable publication conventions can gain adoption for AI-related purposes.
- **Tim Berners-Lee** and the Semantic Web community for the decades-long vision of dereferenceable, self-describing information.
- **HL7** and the FHIR community for proving that federated semantic interoperability is achievable in a regulated professional domain.
- **The Anthropic Claude model** whose initial refusal of Glass-Box Prompting v0.1 as a prompt-injection pattern led directly to the v0.2 reformulation. Rigorous AI alignment improved this protocol.

---

## References

- llms.txt: [https://llmstxt.org/](https://llmstxt.org/) (Jeremy Howard, 2024)
- schema.org: [https://schema.org/](https://schema.org/)
- HL7 FHIR: [https://www.hl7.org/fhir/](https://www.hl7.org/fhir/)
- Semantic Web: [https://www.w3.org/standards/semanticweb/](https://www.w3.org/standards/semanticweb/)
- JSON-LD: [https://json-ld.org/](https://json-ld.org/)
