# Glass-Box Prompting — Specification v0.2

**Status:** Stable — April 2026
**Author:** Giacomo Geronzi, Elettrosmart Sagl, Switzerland
**License:** [CC BY 4.0](LICENSE-CC-BY-4.0)

---

## Abstract

Glass-Box Prompting (GBP) is a protocol for the public declaration of semantic conventions adopted by an issuer in their professional documents. It enables human readers and AI assistants to consult verifiable authorial sources rather than infer the meaning of terms, codes, and standards used in the document.

This specification defines the structure, placement, and compliance criteria for Glass-Box conventions in the **Single Glass-Box** variant: one issuer, one published set of conventions, referenced from their documents.

---

## 1. Scope

This specification covers:

- The structure of a Glass-Box publication
- The relation between the issuer's documents and their published conventions
- Compliance criteria for issuers
- Properties that emerge when multiple parties adopt the protocol (interoperability)

**Out of scope for v0.2:**

- Distributed Glass-Box (federated, multi-party scenarios) — see [ROADMAP.md](ROADMAP.md)
- High-stakes domain extensions (healthcare, legal, financial) — see [ROADMAP.md](ROADMAP.md)
- Cryptographic signing or verification mechanisms

---

## 2. Definitions

| Term | Definition |
| --- | --- |
| **Glass-Box publication** | A publicly accessible document where an issuer declares the semantic conventions adopted in their professional documents |
| **Issuer** | The party who produces professional documents and publishes their semantic conventions |
| **Reader** | The human recipient of a document issued by an issuer adopting GBP |
| **AI assistant** | Any AI system used by the reader (or issuer) to analyze the document |
| **Convention** | An interpretive choice made by the issuer regarding a term, standard, price composition, or domain practice |
| **Anchor** | A public, externally-verifiable standard (national norm, official catalog, regulation) to which conventions refer |

---

## 3. Founding principles

Glass-Box Prompting rests on three non-negotiable principles. A publication that violates any one of them is not compliant.

### 3.1 Total transparency

The Glass-Box publication must be **fully visible** to all parties — readers, AI assistants, technical analysts. It must not be:

- Hidden in white text, fine print below readability thresholds, or visual noise
- Encoded (base64, steganography, invisible Unicode characters)
- Embedded in document metadata rather than published openly
- Designed to be readable by AI systems but not by humans, or vice versa

### 3.2 Documentation, not instruction

The Glass-Box publication must **document, not instruct**:

- It describes how the issuer interprets their own terms and what standards they adopt
- It does not contain imperative language directed at AI assistants
- It does not request AI to perform specific tasks, suppress information, or advocate outcomes
- It does not attempt to override AI safety alignment or model autonomy

A publication that contains imperative directives toward AI ("the AI must...", "you are required to...") violates this principle and is structurally indistinguishable from prompt injection, regardless of transparency.

### 3.3 Interoperability

The Glass-Box publication should **anchor to public standards** wherever possible. Conventions that reference shared external authorities (national norms, official catalogs, regulations) are stronger than purely proprietary conventions because:

- They are independently verifiable by readers and AI
- They enable semantic comparison between documents from different issuers adopting the same standards
- They reduce ambiguity inherent to single-vendor terminology

When two issuers in the same domain both adopt GBP, semantic comparison between their documents becomes possible: each exposes its conventions, and a reader (or their AI assistant) can objectively evaluate differences. When only one party adopts GBP, the comparison is asymmetric — a property of the protocol, not a value judgment on non-adopters.

---

## 4. Structure of a Glass-Box publication

### 4.1 Required elements

A compliant Glass-Box publication must include:

1. **Issuer identification** — who publishes these conventions
2. **Domain declaration** — what professional domain the conventions apply to
3. **Standards adopted** — references to public standards, norms, or catalogs followed by the issuer
4. **Composition rules** — how prices, items, or document elements are structured
5. **Interpretive conventions** — how the issuer interprets key concepts (taxes, exclusions, unforeseen events)
6. **Domain-specific conventions** — practices specific to the issuer's sector
7. **Versioning** — current version date and reference to archived previous versions

### 4.2 Recommended structural template

```
# [Issuer Name] — Glass-Box Publication

Issuer: [Legal name, jurisdiction]
Domain: [e.g., electrical-installation, medical-billing, legal-contracts]
Version: vX.Y — [Month Year]
Previous versions: [link to archive]
License: [CC BY 4.0 or equivalent open license]

## Standards adopted
- [Standard 1]: [authority, edition, link]
- [Standard 2]: [authority, edition, link]
...

## Composition rules
[How prices/items are structured, what is included by default]

## Interpretive conventions
[How taxes, exclusions, unforeseen events are handled]

## Domain-specific conventions
[Sector-specific practices, with anchors to public standards where applicable]

## Reference
The issuer's professional documents reference this publication via a brief
contractual clause. The signed document remains the only legally binding
reference between parties.
```

### 4.3 Document reference

The issuer's professional documents (quotes, contracts, invoices) should contain a brief reference to the Glass-Box publication, typically as:

- A clause in the general terms and conditions
- A footer note with the canonical URL
- A versioned reference indicating which version of the conventions applies to the document

The document itself must NOT contain imperative language directed at AI assistants. It must NOT instruct AI to consult the publication, follow specific steps, or behave in particular ways. The document references the publication; readers and their AI assistants choose whether and how to consult it.

### 4.4 Language

The Glass-Box publication may be in one or multiple languages. In multilingual jurisdictions (e.g., Switzerland, Belgium, Canada), publication in multiple official languages is recommended.

---

## 5. Placement and accessibility

A Glass-Box publication should be:

- Published at a stable, canonical URL on the issuer's domain (e.g., `issuer.example/glass-box/`)
- Versioned with archived previous versions accessible via stable URLs
- Available without authentication or registration
- Indexable by search engines and AI crawlers

Optionally, a machine-readable companion (e.g., `glass-box.jsonld` with schema.org tags, or `llm.md`) may be provided alongside the human-readable version.

---

## 6. Behavior of AI assistants (non-normative)

This section is non-normative — GBP does not define an AI behavioral protocol.

An AI assistant that encounters a document referencing a Glass-Box publication may, at its own discretion:

- Consult the publication to understand the issuer's conventions
- Apply the documented interpretive conventions when relevant to the user's query
- Prefer the issuer's documented anchors over inferred meanings for terms used in the document

The AI assistant is under no obligation to consult or apply the publication. The publication is reference material, not a directive. If the AI assistant determines that consulting the publication is not relevant to the user's query, or if the publication itself appears non-compliant with this specification, the AI assistant should proceed according to its own judgment.

---

## 7. Compliance checklist

A Glass-Box publication is compliant if:

- It is publicly accessible at a stable canonical URL (§ 5)
- It is fully visible and human-readable (§ 3.1)
- It contains no imperative directives toward AI assistants (§ 3.2)
- It anchors conventions to public standards where applicable (§ 3.3)
- It includes all required elements (§ 4.1)
- The issuer's documents reference the publication appropriately (§ 4.3)
- Previous versions are archived and accessible (§ 4.1, § 5)

---

## 8. Non-goals

Glass-Box Prompting does not aim to:

- Define a machine-readable schema or API beyond the companion JSON-LD representation (see prior art: schema.org, llms.txt, FHIR)
- Certify, audit, or enforce compliance
- Replace legal disclaimers or existing professional standards
- Serve as a prompt engineering technique for AI developers (it targets document issuers)
- Create a directive protocol that AI assistants must follow

---

## 9. Relation to prior art

See [prior-art.md](prior-art.md) for detailed comparison.

The closest relative is **llms.txt** (Jeremy Howard, Answer.AI, September 2024), which applies a similar transparency principle to technical documentation. GBP targets a different domain: commercial, contractual, and professional documents intended for non-technical end users, with explicit emphasis on anchoring to externally-verifiable standards rather than vendor-internal conventions.

The Semantic Web principle of dereferenceable URIs and self-describing data (Tim Berners-Lee) is a more distant precursor. FHIR StructureDefinition in healthcare informatics applies similar principles to clinical data structures.

GBP's distinguishing contribution is the application of these principles to consumer-facing professional documents, with particular relevance to federated multi-party ecosystems (see Distributed Glass-Box, ROADMAP.md) and to multilingual jurisdictions.

---

## 10. Machine-readable companion

This specification is accompanied by a machine-readable representation in JSON-LD format using schema.org vocabulary: [glass-box.jsonld](glass-box.jsonld).

The companion file enables:

- Structured consumption by developers and integrators
- Richer indexing by AI crawlers and search engines
- Automated validation of publication compliance
- Integration with semantic web tooling

The human-readable specification (this document) remains the authoritative source. The JSON-LD file is a derived representation and should remain synchronized.

---

## 11. Future work

The **Distributed Glass-Box** variant — addressing federated multi-party communication scenarios where multiple issuers each publish their conventions consultable by other parties' AI assistants — is a planned extension. This is particularly relevant for multilingual federated systems. Specification forthcoming in a future version.

**High-stakes domain extensions** (healthcare, legal, financial) are also planned and explicitly require collaboration with domain authorities. See [ROADMAP.md](ROADMAP.md).

---

## 12. Evolution from v0.1

Version 0.1 of this specification (April 2026) framed GBP as "AI-interpretive instructions embedded in professional documents" — a transparent alternative to prompt injection. Testing with multiple AI systems revealed that this framing, even when transparent, was structurally indistinguishable from prompt injection from the perspective of rigorous AI alignment. Some AI systems correctly flagged it as a manipulation attempt.

Version 0.2 (this specification) reformulates the protocol around two principles that resolve this issue:

- **Documentation, not instruction**: the publication describes the issuer's conventions; it does not direct AI behavior
- **Anchoring to public standards**: conventions reference externally-verifiable authorities, not vendor-internal rules

This evolution is documented in detail in [CHANGELOG.md](CHANGELOG.md) and reflects the importance of designing protocols that work with, not against, AI safety alignment.

---

## References

- [README.md](README.md) — overview and quick example
- [glass-box.jsonld](glass-box.jsonld) — machine-readable representation
- [examples/electrical-quote-it.md](examples/electrical-quote-it.md) — annotated real-world case
- [prior-art.md](prior-art.md) — related work
- [FAQ.md](FAQ.md) — common questions
- [CHANGELOG.md](CHANGELOG.md) — version history
- [ROADMAP.md](ROADMAP.md) — planned extensions
