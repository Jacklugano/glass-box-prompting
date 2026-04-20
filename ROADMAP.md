# Roadmap

This document outlines planned extensions to the Glass-Box Prompting framework. Items listed here are not committed to any timeline and may evolve based on community feedback, domain partnerships, and available resources.

---

## Current version

**v0.2** — Single Glass-Box variant. One issuer, one published set of semantic conventions, referenced from their professional documents. See [SPECIFICATION.md](SPECIFICATION.md).

---

## Planned extensions

### Distributed Glass-Box

A planned extension addressing federated multi-party communication scenarios (e.g., inter-institutional document exchange in multilingual contexts). Each party in a federated system publishes their own conventions consultable by other parties' AI assistants. Particularly relevant for multilingual jurisdictions.

Specification forthcoming in a future version.

---

## High-stakes domain extensions (planned, requires domain partners)

The framework can potentially extend to professional domains where misinterpretation carries significant consequences. These extensions are out of scope for the current author acting alone and require collaboration with domain authorities, regulators, and specialists.

### Healthcare (planned)

Application of Glass-Box Prompting to healthcare documents — clinical letters, discharge summaries, laboratory reports, medical invoices (e.g., Swiss TARDOC system) — requires:

- Integration with existing clinical standards: HL7 FHIR for data structure, SNOMED CT for clinical terminology, ICD-10/11 for diagnoses, LOINC for laboratory codes
- Co-authorship with qualified medical professionals
- Regulatory review under applicable medical device software regulations (e.g., Swiss MedDO)
- Collaboration with healthcare institutions for validation
- Handling of multilingual federated contexts (particularly relevant in countries with multiple official languages such as Switzerland, Belgium, Canada)

A healthcare-specific specification is not included in this version and will require the collaborations listed above. The present author welcomes inquiries from qualified domain partners interested in pursuing this extension.

### Other high-stakes domains

Similar considerations apply to legal contracts with binding interpretive consequences, financial statements with regulatory implications, and insurance policies. Each domain requires its own combination of standards integration, co-authorship, and regulatory review.

---

## Sector-specific templates

Alongside domain extensions, the framework plans to publish reusable structural templates for specific sectors:

- `electrical-installation` / CPN (in progress — see [examples/electrical-quote-it.md](examples/electrical-quote-it.md))
- `medical-billing` / TARDOC (requires healthcare domain partnership)
- Others to be defined with community input

---

## Machine-readable tooling

- Validation tooling for Glass-Box publication compliance (JSON Schema, linter)
- Additional `@type` vocabulary for domain-specific publications

---

## How to contribute

See [CONTRIBUTING.md](CONTRIBUTING.md). Feedback on the roadmap — including domain partnership inquiries — is welcome via GitHub Issues.
