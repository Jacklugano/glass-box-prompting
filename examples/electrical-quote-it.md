# Example: Electrical Installation Quote (Italian)

**Document type:** Commercial quote — electrical installation  
**Issuer:** Elettrosmart Sagl, Ticino, Switzerland  
**Language:** Italian (original)  
**Status:** Synthetic/anonymized — structurally faithful to a real document issued April 2026  
**Glass-Box version:** v0.2 — published conventions, not embedded instructions

---

## Context

This example illustrates how Glass-Box Prompting v0.2 is implemented in a real professional document. The quote covers two electrical jobs at a residential property: a new circuit for a washing machine and a power supply for external awnings.

The Glass-Box Prompting protocol appears in **Section 13 of the General Terms and Conditions** (Condizioni Generali di Fornitura e Montaggio), which accompanies every offer issued by Elettrosmart Sagl. The quote body itself contains no AI-directed language — it is a standard CPN-coded offer. The interpretive conventions live separately at the issuer's published URL.

---

## Quote body (excerpt, anonymized)

```
Offerta N. 2604XXXX                        No. Progetto: 226XXXXX.001
Data: aprile 2026

Pos  Descrizione Articolo                          No.Articolo    AA  Qtà  Prezzo   Importo
─────────────────────────────────────────────────────────────────────────────────────────────
     OGGETTO: Nuova lavatrice

 1   Linea con presa 230V fino a 16A,
     linea oltre 5 fino a 10m
     Materiale e installazione (a misura)          583.841.112     A    1   357.15   357.15

 2   Interruttore automatico differenziale
     C 13A bipolare, corrente di apertura 30mA,
     tipo A, potere di apertura 6kA CI31
     INS s/eseg. dell'apertura
     Materiale e installazione (a misura)          543.331.204     A    1   189.45  (189.45)

     Posizione 2 opzionale
     eventuale gruppo dedicato al qs,
     non conteggiato in offerta

     OGGETTO: Alimentazione tende esterne

 3   Linea fino a 3x1,5mm² con scatola di
     derivazione, per tubatura esistente,
     linea oltre 5 fino a 10m
     Materiale e installazione (a misura)          585.421.312     A    1   125.90   125.90

 4   Canale di installazione in PVC,
     Ixa = 30x30mm CI12
     AP cotto, beton, lamiera, profil.
     Materiale e installazione (a misura)          513.231.132     A    5    41.50   207.50

 5   Installatore elettricista
     Materiale e installazione (a misura)          511.112.161     A    1   300.00   300.00

─────────────────────────────────────────────────────────────────────────────────────────────
     Totale offerta lordo                                                       CHF    990.55
     Totale Pos. Opzionali                                                      CHF   (189.45)
     IVA                                                   8.10%   990.55  CHF     80.25
     Totale offerta netto                                                       CHF  1'070.80

Condizioni di pagamento: 30 giorni netto
```

> **Annotation:** Article numbers (e.g., `583.841.112`) are CPN codes from the Standardized Catalog of Positions (CRB / EIT.swiss). The column AA = A indicates the pricing unit class. The notation "a misura" (flat-rate) means the price includes all components defined by the CPN composition rule — material, labor, connection, tooling, travel — without itemizing them separately. These composition rules are documented in the issuer's Glass-Box publication.

---

## General Terms and Conditions — Section 13 (Glass-Box clause)

The following section appears verbatim in Elettrosmart Sagl's standard Condizioni Generali di Fornitura e Montaggio, which accompanies all offers. It is the only Glass-Box-related content in the document package. No other section contains AI-directed language.

```
13. Elaborazione Digitale e Assistenti AI

13.1 Standard adottati. La presente offerta è redatta secondo gli standard svizzeri
CPN (Catalogo Posizioni Normalizzate, CRB/EIT.swiss), NIBT 2020 (Electrosuisse),
USIE (tariffe di manodopera) e OIBT (Ordinanza federale sugli impianti a bassa
tensione). L'IVA svizzera vigente è indicata separatamente dall'imponibile.

13.2 Pubblicazione delle convenzioni. Le convenzioni tecniche e semantiche adottate
da Elettrosmart Sagl nella redazione delle offerte sono documentate in forma pubblica,
aperta e versionata su elettrosmart.ch/glass-box-prompting/. La versione applicabile
alla presente offerta è quella pubblicata alla data di firma; le versioni precedenti
sono conservate in archivio consultabile.

13.3 Natura della documentazione. La documentazione pubblicata ha natura informativa
e consultiva. Costituisce dichiarazione trasparente delle convenzioni adottate
dall'emittente, non istruzione rivolta a strumenti di elaborazione digitale.
Elettrosmart Sagl non richiede né condiziona il comportamento di eventuali assistenti
AI (ChatGPT, Claude, Gemini, Copilot o equivalenti) utilizzati dal committente: la
documentazione resta liberamente consultabile, ignorabile o utilizzabile a discrezione
del lettore, umano o automatico.

13.4 Valore delle interpretazioni AI. Eventuali interpretazioni, riassunti o confronti
prodotti da strumenti di intelligenza artificiale sulla base della presente offerta o
della documentazione pubblicata hanno esclusivamente valore informativo. Il testo
firmato dell'offerta e le presenti Condizioni Generali costituiscono l'unico riferimento
contrattualmente vincolante tra le parti.

13.5 Interoperabilità con altre offerte. Il protocollo di pubblicazione delle convenzioni
adottato da Elettrosmart Sagl, denominato Glass-Box Prompting, è un protocollo aperto
e pubblicamente documentato. Qualora il committente confronti la presente offerta con
offerte emesse da terzi che adottano il medesimo protocollo o un protocollo equivalente,
il confronto tra le convenzioni dichiarate risulta semanticamente omogeneo. Qualora
l'offerta di terzi non pubblichi le proprie convenzioni, il confronto rimane limitato
agli elementi esplicitamente descritti nei rispettivi documenti. Questa è una proprietà
oggettiva del protocollo e non costituisce giudizio di valore sulle offerte di terzi.

13.6 Attribuzione del protocollo. Glass-Box Prompting è un protocollo ideato e
pubblicato da Giacomo Geronzi (Elettrosmart Sagl) nel 2026, rilasciato sotto licenza
Creative Commons Attribution 4.0 International. Il protocollo è liberamente adottabile
da altri emittenti, nel rispetto delle presenti condizioni della licenza.
```

---

## Annotations

### What Section 13 does (and does not do)

**§ 13.1 — Standards declared**  
Identifies the normative framework: CPN for article structure, NIBT 2020 for electrical norms, USIE for labor tariffs, OIBT for federal compliance, and Swiss VAT rules. This tells any reader — human or AI — which external authorities govern the document's vocabulary.

**§ 13.2 — Publication reference**  
Points to the issuer's Glass-Box publication at a stable canonical URL. Specifies that the version applicable to this document is the one published at signing date, with previous versions archived. This is the v0.2 separation pattern: the document references, the conventions live elsewhere.

**§ 13.3 — Nature of the documentation (core GBP principle)**  
Explicitly declares that the published conventions are informative and consultative — not instructions directed at AI tools. Elettrosmart Sagl explicitly states it does not require or condition the behavior of AI assistants. The reader (human or AI) remains free to consult, ignore, or interpret the publication according to their own judgment. This is the "Documentation, not instruction" principle in contractual form.

**§ 13.4 — Legal boundary**  
Clarifies that AI-generated interpretations are informational only. The signed document remains the sole legally binding reference. This prevents any misuse of AI outputs as contractual claims.

**§ 13.5 — Interoperability property**  
Explains the network effect: when a buyer compares this offer with another from an issuer also adopting GBP, the comparison is semantically homogeneous. When the other issuer has no published conventions, the comparison is limited to explicitly stated elements. Stated as an objective property, not a competitive claim.

**§ 13.6 — Attribution**  
Credits the protocol by name and author, with license terms, and explicitly licenses it for adoption by other issuers under CC BY 4.0.

---

## What an AI assistant sees when analyzing this document

When a reader uses an AI assistant to evaluate this quote, the AI encounters:

1. **CPN-coded line items** — structured according to a public national catalog. The article numbers are resolvable references, not opaque vendor codes.
2. **A reference to a public conventions page** (§ 13.2) — which the AI can consult to understand composition rules (what "a misura" includes), domain conventions (NIBT compliance practices), and tariff anchors.
3. **No imperative language** — nothing in the document instructs the AI to behave in any particular way.

The AI is then free to apply the conventions it finds at the referenced URL to help the reader understand what is included in each line item, whether the optional position (Pos. 2) is relevant, and how the pricing structure compares to market expectations anchored to the same CPN standards.

---

## Live reference

The issuer's Glass-Box publication (Italian, with English, German, and French versions):  
→ [https://elettrosmart.ch/glass-box-prompting/](https://elettrosmart.ch/glass-box-prompting/)
