---
title: "Sprinkling Act Methodology — Reference Card"
subtitle: "SA-METH-2026.04"
author: "Lamar B. Shucrani — Sprinkling Act, Brussels (BCE BE 1034.962.482)"
date: "27 April 2026"
documentclass: article
geometry: margin=2cm
fontsize: 10pt
---

# Sprinkling Act Methodology — Reference Card

**Version**: SA-METH-2026.04  
**Regulatory freeze date**: March 2026  
**Source**: Regulation (EU) 2024/1689 (EU AI Act) — full text at <https://eur-lex.europa.eu/eli/reg/2024/1689/oj>  
**Full methodology**: <https://sprinklingact.com/methodology>  
**License**: CC BY-ND 4.0

---

## Purpose

Sprinkling Act produces independent, article-mapped EU AI Act position assessments for European deployers and providers of AI systems. Each assessment maps a specific use case to the specific articles of Regulation (EU) 2024/1689 that apply, gate by gate, with a verifiable audit trail.

This reference card is a condensed snapshot of the SA-METH-2026.04 methodology. The full version is published, versioned, and updated at <https://sprinklingact.com/methodology>.

---

## Six Core Principles

1. **Article mapping** — every classification cites a specific article, paragraph, or annex of Regulation (EU) 2024/1689. No interpretation beyond the regulatory text.
2. **Gate logic** — gates are evaluated in sequence. The first gate triggered determines the final classification. A Prohibited Practice at Gate 01 ends the assessment.
3. **Audit trail** — every classification carries a traceable path: gate by gate, article by article. Independently verifiable by a third party.
4. **Temporal stability indicator** — STABLE / MODERATE / UNSTABLE — reflecting the likelihood that the classification changes as guidelines evolve.
5. **No interpretation in the client's favour** — when classification is uncertain, this is flagged explicitly with a recommendation to seek qualified legal counsel.
6. **Dual versioning** — every report carries the methodology version (SA-METH-YYYY.MM) and the regulatory freeze date.

---

## The Six Regulatory Gates

| Gate | Article | Trigger | Outcome |
|------|---------|---------|---------|
| 01 | Art. 5 | Prohibited practice (subliminal manipulation, social scoring, real-time biometric ID, exploitation of vulnerabilities, untargeted scraping, emotion recognition in workplace/education, biometric categorisation) | **PROHIBITED** — system cannot be deployed legally |
| 02 | Art. 6(1) | Safety component of regulated product (Annex I — including MDR/IVDR medical devices subject to Notified Body conformity assessment) | **HIGH RISK** |
| 03 | Art. 6(2) + Annex III | High-risk sector (employment, education, public services, biometrics, critical infrastructure, law enforcement, migration, justice) | **HIGH RISK** (subject to Art. 6(3) narrow exception) |
| 04 | Art. 51 + 55 | GPAI model with systemic risk (training compute > 10²⁵ FLOPs) | **HIGH RISK** + adversarial testing + incident reporting |
| 05 | Art. 50 | Transparency obligations (chatbots, AI-generated content, emotion recognition, biometric categorisation) | **LIMITED RISK** — disclosure requirements |
| 06 | Art. 53 | GPAI standard obligations (technical documentation, training data summaries, copyright compliance) | **LIMITED RISK** — provider obligations |

Gates evaluated in sequence; the first triggered determines the classification. Lower gates are not evaluated once a higher gate is triggered.

---

## Medical AI specificity (MDCG 2025-6 / AIB 2025-1)

For AI systems that are medical devices or safety components of medical devices, classification follows two cumulative conditions under Art. 6(1) AIA:

1. The AI is a safety component (Art. 3(14) AIA) **OR** the AI system is itself the medical device / IVD.
2. The AI is subject to third-party conformity assessment by a Notified Body under MDR (Reg. 2017/745) or IVDR (Reg. 2017/746).

If both conditions are met → high-risk under Art. 6(1). MDCG 2025-6 endorses **integration** rather than duplication: one QMS, one technical documentation file (Art. 11(2) AIA + Art. 17(3) AIA + Recital 81).

Source: MDCG 2025-6 / AIB 2025-1, *Interplay between MDR & IVDR and AIA*, June 2025, Table 1 page 6.

---

## International standards alignment

The methodology is structurally consistent (not formally certified) with:

- **NIST AI RMF 1.0** (NIST AI 100-1, 2023) — gate evaluation maps to the Map and Measure functions.
- **ISO/IEC 42001:2023** — the 6-gate output produces the risk classification and obligation mapping that feeds into an ISO 42001-compliant AI Management System.
- **WHO Regulatory considerations on AI for health** (2023, ISBN 9789240078871) — six topic areas mapped to AIA + MDR articles for medical AI assessments.
- **WHO Generating evidence for AI-based medical devices** (2021, ISBN 9789240038462) — informs validation reasoning.

Sprinkling Act does not claim NIST compliance, ISO 42001 certification, or WHO endorsement. References indicate structural coherence only.

---

## Limitations & disclaimers

- The EU AI Act requires contextual interpretation. Sprinkling Act does not resolve ambiguity — it flags it explicitly and recommends qualified legal counsel for edge cases.
- Sprinkling Act is an operational tool, not a legal opinion. It produces the structured, article-mapped artefact that a lawyer, regulator, or investor needs as a starting point.
- Classification is based on information provided by the client. Incomplete or inaccurate inputs produce incomplete or inaccurate classifications.
- The methodology does not cover national implementing legislation, sector-specific overlaps (e.g. GDPR + AI Act interaction), or AI systems deployed outside the EU.

---

## Versioning

- **v0.1** — January 2026 — Initial release. 6 regulatory gates based on Art. 5, 6, 50, 51, 53.
- **v1.0** — March 2026 — Methodology versioned and published. GPAI systemic risk gate (Art. 55). Art. 6(3) exemption logic. AI Office guidance on Annex III.
- **v1.1** — March 2026 — Art. 5§1(d) added (criminal risk profiling). Art. 5§1(h) reference corrected (real-time biometric). HIGH RISK obligations enriched with Art. 9-15 details. International standards alignment section added.

This document is **SA-METH-2026.04** — the April 2026 reference-card snapshot of v1.1.

---

## Cryptographic timestamp

This PDF is timestamped via OpenTimestamps and anchored on the Bitcoin blockchain. Independent verification:

```
pip3 install opentimestamps-client
ots verify SA-METH-2026.04.pdf.ots
```

The `.ots` proof is published at <https://github.com/sprinkling-act/timestamps>.

---

## Legal status

Sprinkling Act is an independent pre-conformity advisory firm operated by Lamar B. Shucrani in Belgium (BCE BE 1034.962.482). It is **not** a law firm, **not** a Notified Body, **not** a certification body, and **not** affiliated with, endorsed by, or acting on behalf of the European Commission, the European Parliament, or any national supervisory authority.

Reports and assessments are an informative indication, **not legal advice**. Companies should consult qualified legal counsel and a Notified Body for compliance and certification decisions.

---

*Sprinkling Act · sprinklingact.com · contact@sprinklingact.com · BCE BE 1034.962.482*
