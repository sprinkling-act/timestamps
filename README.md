# Sprinkling Act — OpenTimestamps proofs

Cryptographic timestamp proofs (OpenTimestamps protocol) for Sprinkling Act published reports.

Each `.ots` file is a portable proof that the corresponding PDF existed at the timestamp date, anchored on the Bitcoin blockchain via decentralised calendar servers. The proof can be verified by anyone, independently of Sprinkling Act, using the open-source [OpenTimestamps client](https://github.com/opentimestamps/opentimestamps-client).

## Reports timestamped

| Report | Zenodo DOI | MD5 | Stamped on | `.ots` file |
|---|---|---|---|---|
| EU AI Act Readiness — A Structured Screening of 50 European AI Companies (April 2026) | [10.5281/zenodo.19671329](https://doi.org/10.5281/zenodo.19671329) | `a134924887bcf2450ebc30eb81850ad1` | 2026-04-27 | `eu-ai-act-readiness-report-april-2026.pdf.ots` |

The Annex (referenced from the parent report) will be timestamped once finalised and added here.

## How to verify

1. **Install the OpenTimestamps client** (Python):

   ```bash
   pip3 install opentimestamps-client
   ```

2. **Download the original PDF** from Zenodo using the DOI link above, and download the matching `.ots` from this repository. Place both files side by side.

3. **Run the verification**:

   ```bash
   ots verify eu-ai-act-readiness-report-april-2026.pdf.ots
   ```

   The client will check the proof against the Bitcoin blockchain and report the date at which the file existed.

4. **Optional — upgrade the proof first** (if it was just freshly created and the Bitcoin attestation is not yet bundled):

   ```bash
   ots upgrade eu-ai-act-readiness-report-april-2026.pdf.ots
   ```

   This pulls the latest Bitcoin attestation from the calendars and bakes it into the `.ots` file. After upgrade, no internet connection is needed for verification.

## What this proves — and what it does not

**Proves**: the PDF existed in this exact byte-for-byte form at the timestamp date. Independent of Sprinkling Act, of any third-party authority, and of any commercial relationship.

**Does not prove**: the truthfulness of the report's content, its compliance with any specific regulation, or any endorsement by a public body. OpenTimestamps is a cryptographic existence-proof, not a content-validation mechanism. The report itself is published under CC BY 4.0 and remains an independent assessment that *does not constitute legal advice* — see the report's own disclaimer.

## Why OpenTimestamps

- Free, open standard (RFC-compatible)
- Anchored on the Bitcoin blockchain (immutable, globally verifiable)
- No commercial dependency — verifiable even if Sprinkling Act ceases to operate
- Compatible with eIDAS-style independent verification needs (without claiming qualified-trust-service status)

## License

The `.ots` proof files in this repository are released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) (public domain) — they are pure cryptographic artefacts and contain no creative content.

The reports themselves are published on Zenodo under their respective licenses (CC BY 4.0 for the April 2026 report).

## Sources

- [OpenTimestamps protocol](https://opentimestamps.org/)
- [opentimestamps-client (GitHub)](https://github.com/opentimestamps/opentimestamps-client)
- [Sprinkling Act — sprinklingact.com](https://sprinklingact.com)
