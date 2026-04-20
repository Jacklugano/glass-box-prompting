# Glass-Box Prompting

> A semantic anchoring protocol for professional documents. Each issuer publishes their adopted conventions transparently, so readers — human or AI — can consult them rather than infer.

Glass-Box Prompting (GBP) is an open protocol for declaring the semantic conventions adopted by an issuer in their professional documents — quotes, contracts, invoices, reports, medical bills. Instead of leaving readers and AI assistants to guess what a term, code, or standard means, the issuer publishes their conventions in a consultable form.

The protocol does not instruct AI on what to do. It documents what the issuer means.

## Three founding principles

| Principle | Description |
| --- | --- |
| **Total transparency** | The issuer's semantic conventions are published in a form readable by anyone — humans, AI assistants, technical analysts. Nothing is hidden, encoded, or disguised as metadata. |
| **Documentation, not instruction** | The protocol describes how the issuer interprets their own terms. It does not instruct AI on behavior, does not impose actions, does not attempt to influence reader judgment. |
| **Interoperability** | Value grows with adoption. When two documents both adopt the protocol, semantic comparison becomes possible: each exposes its conventions, and the reader can objectively evaluate differences. |

## What this protocol is NOT

To prevent confusion with prompt injection or AI manipulation patterns:

- It does not instruct AI assistants on what to do or how to respond
- It does not impose behaviors nor constrain model autonomy
- It does not attempt to influence reader judgment
- It does not grant legal validity to AI interpretations
- It does not replace professional human judgment
- It does not bypass AI safety alignment

It is simply a practice of transparent publication of adopted conventions. Every reader — human or AI — remains free to consult, ignore, or interpret them according to their own judgment.

## Quick example

A Glass-Box block published on the issuer's website (not embedded as instructions in the document):

```
Issuer: Elettrosmart Sagl, Switzerland
Domain: electrical-installation
Standards adopted:
  - CPN (Standardized Catalog of Positions, CRB / EIT.swiss)
  - NIBT 2020 (Low-voltage installation norms, Electrosuisse)
  - USIE (Labor tariff references)
  - OIBT (Federal ordinance, fedlex.admin.ch)
  - Swiss VAT (Federal Tax Administration)

CPN price composition (flat-rate convention):
  Each CPN line item includes by definition: main material, small hardware,
  installation labor, technical connection time, technical processing,
  tool wear, travel time.

Domain conventions (NIBT / EV charging):
  - Installations above 3.5 kW: distributor notification and RaSi safety
    certificate are Elettrosmart standard practice and considered included
    unless otherwise specified.
  - 22 kW wallboxes in Swiss residential context: distributors generally
    do not approve 22 kW residential charging; installed 22 kW stations
    are firmware/hardware-limited to 11 kW.

Version: v0.2 — April 2026 (previous versions archived)
```

The document itself contains a brief contractual reference to where these conventions are published. Readers (and any AI assistant they use) can consult them. They are not instructions; they are documentation.

→ Live example (Italian, with multilingual versions): [https://elettrosmart.ch/glass-box-prompting/](https://elettrosmart.ch/glass-box-prompting/)
→ Annotated case study: [examples/electrical-quote-it.md](examples/electrical-quote-it.md)

## Why publication, not embedding

Earlier versions of this concept (v0.1) embedded interpretive instructions directly in documents. This approach was problematic: even when transparently declared, instructions inside a document directed at AI assistants are structurally similar to prompt injection. Rigorous AI models correctly treat them with suspicion.

Glass-Box Prompting v0.2 resolves this by separating two things:

1. **The document itself** contains the substantive content (the quote, contract, invoice). It includes only a brief contractual clause referring to where the issuer's conventions are published. No imperative language toward AI.

2. **The published conventions** live on the issuer's website (or another canonical URL). They document — not instruct. They are anchored to public standards (national norms, official catalogs) rather than proprietary vendor rules.

This matters because anchoring to shared, externally-verifiable standards is what makes the protocol semantically robust. AI systems accept this structure naturally: it is reference resolution, not behavior manipulation.

## Validation

Tested with real commercial quotes in the Swiss electrical-installation sector. Results from analysis by ChatGPT, Claude, and Gemini varied across iterations:

- **v0.1 (embedded instructions approach)**: ChatGPT and Gemini followed the instructions; Claude flagged the embedded instructions as a manipulation attempt and refused to apply them. This feedback led to the v0.2 reformulation.

- **v0.2 (published conventions approach)**: validated through structured promptfoo audit. Framework citation rates across models: Claude 100%, Gemini 100%, ChatGPT 30%. AI assistants treat the published conventions as legitimate reference material and apply them naturally without flagging concerns.

The full evolution is documented in [CHANGELOG.md](CHANGELOG.md).

## Repository contents

| File | Description |
| --- | --- |
| [SPECIFICATION.md](SPECIFICATION.md) | Formal spec v0.2 — Single Glass-Box variant |
| [glass-box.jsonld](glass-box.jsonld) | Machine-readable representation (JSON-LD / schema.org) |
| [examples/electrical-quote-it.md](examples/electrical-quote-it.md) | Annotated real-world example (Italian) |
| [prior-art.md](prior-art.md) | Honest comparison with related work |
| [FAQ.md](FAQ.md) | Common questions |
| [ROADMAP.md](ROADMAP.md) | Planned extensions |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to contribute |
| [CHANGELOG.md](CHANGELOG.md) | Version history including v0.1 → v0.2 evolution |

## Status

**v0.2 — April 2026.** This release covers the **Single Glass-Box** variant: one issuer, one published set of semantic conventions. A distributed multi-party extension addressing federated multilingual scenarios is planned; see [ROADMAP.md](ROADMAP.md).

## Author

**Giacomo Geronzi** · Elettrosmart Sagl · Switzerland

## License

Documentation and specification: [CC BY 4.0](LICENSE-CC-BY-4.0)
Code (if any): [MIT](LICENSE-MIT)
