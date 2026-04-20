# Changelog

All notable changes to the Glass-Box Prompting specification are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.2.0] — 2026-04-19

### Major reformulation

This version reformulates the core framing of Glass-Box Prompting in response to feedback from rigorous AI safety alignment. The contribution remains attributed to the same author and the v0.1 timestamp remains the original publication date of the concept name and approach.

### Changed

- **Core framing** changed from "transparent AI-interpretive instructions embedded in documents" to "publication of semantic conventions adopted by the issuer".
- **Principle 2** changed from "Bidirectional alignment" to "Documentation, not instruction" — clarifying that the protocol describes issuer conventions rather than directing AI behavior.
- **Principle 3** changed from "Frame, not command" to "Interoperability" — emphasizing that the protocol's value grows with adoption and enables semantic comparison between documents from different issuers.
- **Document structure**: documents themselves no longer contain imperative AI-directed instructions. They reference a separately published conventions document.
- **Anchoring**: explicit emphasis on referencing public, externally-verifiable standards (national norms, official catalogs) rather than purely proprietary vendor conventions.

### Rationale

During testing of v0.1, the Anthropic Claude model identified the embedded interpretive instructions as structurally indistinguishable from prompt injection, regardless of their transparency. Even when openly declared, instructions inside a document directed at AI assistants share the same architectural pattern as injection attacks: a third party (the document issuer) attempts to influence the conversation between the AI and its user.

This feedback was correct and led to a fundamental rethinking of the protocol. The v0.2 reformulation separates two things that v0.1 conflated:

1. **The professional document** (quote, contract, invoice) — which contains only substantive content and a brief contractual reference to the conventions publication.
2. **The conventions publication** — which lives separately on the issuer's website, documents the issuer's interpretive choices, and anchors them to public standards.

This separation resolves the prompt injection ambiguity: there are no AI-directed instructions in the document itself. The conventions publication is reference material, consultable but not directive. AI systems treat it as legitimate authorial reference, not as manipulation.

### Added

- Section "What this protocol is NOT" in README, explicitly distancing GBP from prompt injection patterns.
- Section "Why publication, not embedding" in README, explaining the architectural separation.
- Section 12 in SPECIFICATION ("Evolution from v0.1") documenting the reasoning publicly.
- Section 10 in SPECIFICATION ("Machine-readable companion") referencing the new JSON-LD representation.
- Section 11 in SPECIFICATION ("Future work") including high-stakes domain extensions placeholder.
- New file `glass-box.jsonld` providing machine-readable representation in JSON-LD / schema.org format.
- New section in ROADMAP.md for high-stakes domain extensions (healthcare, legal, financial) — explicitly requiring collaboration with domain authorities.
- Reference to live multilingual implementation at elettrosmart.ch/glass-box-prompting/ (Italian, English, German, French).
- Validation data: promptfoo audit showing framework citation rates across models (Claude 100%, Gemini 100%, ChatGPT 30%).

### Removed

- All imperative language toward AI assistants throughout the specification.
- Section "AI assistant behavior" reformulated as non-normative descriptive section, removing prescriptive verbs.
- The "embedded Glass-Box block" pattern from v0.1 — replaced by "published Glass-Box conventions" pattern.

### Migration notes for v0.1 adopters

Issuers who implemented v0.1 with embedded instructions in their documents should:

1. Move the interpretive content from inside the document to a separately published conventions page on their website.
2. Replace the embedded instruction block with a brief contractual clause referencing the published conventions URL.
3. Reformulate the conventions in descriptive language (declaring what the issuer means) rather than directive language (instructing AI behavior).
4. Anchor conventions to public standards wherever possible.

The substantive content — the actual interpretive choices, technical conventions, sector-specific practices — typically remains identical. Only the framing and placement change.

---

## [0.1.0] — 2026-04-18

### Initial release

First public publication of the Glass-Box Prompting concept. Established:

- The term "Glass-Box Prompting" and its public attribution to Giacomo Geronzi (Elettrosmart Sagl, Switzerland)
- The transparency principle as alternative to hidden prompt injection
- Three founding principles: total transparency, bidirectional alignment, frame not command
- Single Glass-Box variant: one document, one declared interpretive frame
- License terms: CC BY 4.0 for specification, MIT for code
- Repository structure: README, SPECIFICATION, examples, prior-art, FAQ, ROADMAP, CONTRIBUTING

This version was tested with real commercial quotes in the Swiss electrical-installation sector. ChatGPT and Gemini interpreted documents according to the embedded frame; Anthropic Claude flagged the embedded instructions as a manipulation attempt and refused to apply them. This feedback led to the v0.2 reformulation.

The v0.1 release remains historically significant as the first formulation of the concept and is preserved in git history. Adopters are encouraged to migrate to v0.2 (see migration notes above).

---

## Unreleased

### Planned for future versions

- Distributed Glass-Box specification — federated multi-party scenarios with particular focus on multilingual ecosystems (see ROADMAP.md)
- High-stakes domain extensions — healthcare (integration with HL7 FHIR, SNOMED CT, TARDOC), legal, financial — requiring collaboration with domain authorities (see ROADMAP.md)
- Sector-specific schema templates (electrical-installation/CPN, medical-billing/TARDOC, others)
