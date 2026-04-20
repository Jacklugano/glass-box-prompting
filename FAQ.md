# Frequently Asked Questions

---

## About the protocol

**What problem does Glass-Box Prompting solve?**

Professional documents — quotes, contracts, invoices, medical bills — are increasingly analyzed by AI assistants on behalf of readers. When an AI reads a CPN-coded electrical quote or a TARDOC-based medical bill, it has no reliable way to know what conventions the issuer used: what is included in a flat-rate line item, how taxes are applied, what domain-specific practices govern the document. Glass-Box Prompting gives issuers a standard way to publish those conventions so readers and their AI assistants can consult them rather than infer.

**Is this a new form of prompt injection?**

No. This is the most important distinction to understand.

Prompt injection is when a third party embeds instructions inside a document to influence how an AI assistant behaves on behalf of a user — typically without the user's knowledge. Glass-Box Prompting v0.2 does the opposite: the issuer publishes semantic conventions at a public URL, in plain language, visible to everyone. There are no instructions directed at AI in the document itself. The published conventions are reference material, not directives. Every reader — human or AI — remains free to consult, ignore, or interpret them.

An earlier version of the protocol (v0.1) did embed interpretive instructions directly in documents. A rigorous AI model correctly identified this as structurally similar to prompt injection and refused to apply it. That feedback led to the v0.2 reformulation. See [CHANGELOG.md](CHANGELOG.md).

**Does GBP instruct AI assistants to behave in specific ways?**

No. The published conventions do not contain imperative language toward AI. They document what the issuer means by their terms. An AI assistant that encounters a document referencing a Glass-Box publication may consult it, ignore it, or apply it — at its own discretion. The protocol imposes no behavioral obligations on any AI system.

**What is the difference between a "Glass-Box publication" and a regular terms-and-conditions page?**

Three things:

1. **Semantic anchoring**: a Glass-Box publication anchors its conventions to public, externally-verifiable standards (national norms, official catalogs, regulations). Generic T&C pages rarely do this.
2. **AI-readable structure**: a Glass-Box publication is structured to be legible to AI assistants as reference material, not just to lawyers.
3. **Versioning with archiving**: the publication is versioned, and previous versions are archived at stable URLs so that a document can always be matched to the conventions that applied when it was issued.

---

## Adoption

**How do I adopt Glass-Box Prompting as an issuer?**

1. Identify the professional standards and conventions you already follow (national norms, official catalogs, sector practices).
2. Write a Glass-Box publication documenting them — use the structural template in [SPECIFICATION.md §4.2](SPECIFICATION.md).
3. Publish it at a stable URL on your domain (e.g., `yourdomain.com/glass-box/`).
4. Add a brief reference clause to your standard document template (quote, contract, invoice) pointing to the published URL.

No registration, certification, or fee is required. The protocol is open under CC BY 4.0.

**Do I need technical expertise to adopt the protocol?**

No. A Glass-Box publication is a plain-text or Markdown document. The only technical requirement is that it is publicly accessible at a stable URL. See the [live example](https://elettrosmart.ch/glass-box-prompting/) for reference.

**Does adoption require changing my existing documents significantly?**

Typically not. The document body remains unchanged. You add a brief reference clause (usually one or two sentences) in the general terms or footer pointing to the published conventions URL. The substantive content — your actual pricing conventions, standards, practices — stays where it is; you are simply making it explicitly and publicly documented.

**Can I adopt GBP if I am not in the electrical-installation sector?**

Yes. The protocol is sector-agnostic. The electrical-installation case is the reference implementation and the domain where validation has been performed. Any professional document domain with identifiable semantic conventions and publicly available standards is a candidate for adoption.

**Is Glass-Box Prompting legally binding?**

No. The published conventions are informational and consultative. The signed document (the quote, contract, invoice) remains the sole legally binding reference between parties. AI interpretations based on the published conventions have no legal force. See [SPECIFICATION.md §4.3](SPECIFICATION.md) and the example clause in [examples/electrical-quote-it.md](examples/electrical-quote-it.md) §13.4.

---

## AI behavior

**What happens when an AI assistant reads a document that references a Glass-Box publication?**

The AI may consult the published conventions at its discretion. If it does, it can use the documented composition rules, standard anchors, and domain practices to give more accurate and specific answers to the reader's questions. In testing (see README Validation section), Claude and Gemini cited the framework in 100% of test cases; ChatGPT in 30%.

**What if an AI assistant ignores the Glass-Box publication?**

That is a valid outcome. The protocol does not require AI compliance. If the AI ignores the publication, the document is still a standard professional document and the AI will interpret it using its general knowledge. The issuers' conventions remain documented and available for future reference.

**Can an issuer use Glass-Box Prompting to make AI assistants say favorable things about their documents?**

No — and attempting this would make the publication non-compliant with the protocol. The "Documentation, not instruction" principle (§3.2 of the specification) explicitly prohibits imperative language that advocates outcomes, suppresses information, or attempts to influence reader judgment. A publication that does these things is not Glass-Box compliant and would correctly be treated as prompt injection by rigorous AI systems.

---

## Protocol and versioning

**How is the protocol versioned?**

The protocol specification follows semantic versioning. The issuer's own publication also carries a version number tied to a publication date. When an issuer updates their conventions, they publish a new version and archive the previous one. Documents reference the version that was current at signing.

**What was different in v0.1?**

v0.1 framed GBP as "transparent AI-interpretive instructions embedded in professional documents." The instructions lived inside the document and were directed at AI assistants. v0.2 separates the document (which contains only substantive content and a reference clause) from the conventions publication (which lives separately and is descriptive, not directive). Full rationale in [CHANGELOG.md](CHANGELOG.md).

**Is there a certification or compliance audit process?**

No. Compliance is self-declared by issuers. The specification provides a checklist (§7) that any issuer can use to evaluate their own publication. The protocol does not involve any central authority, registry, or certification body.

---

## Licensing and attribution

**Can I adopt and adapt the protocol for my own use?**

Yes. The specification is released under [CC BY 4.0](LICENSE-CC-BY-4.0). You may use, adapt, and republish it with attribution to the original author (Giacomo Geronzi, Elettrosmart Sagl).

**Can I implement Glass-Box Prompting in a different language?**

Yes. The protocol is language-agnostic. The reference implementation is in Italian (the working language of Elettrosmart Sagl's documents) with an English specification. Implementations in other languages are encouraged, particularly in multilingual jurisdictions.
