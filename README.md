# Sprinkling Act — OpenTimestamps proofs

Cryptographic timestamp proofs (OpenTimestamps protocol) for Sprinkling Act published reports.

Each `.ots` file is a portable proof that the corresponding PDF existed at the timestamp date, anchored on the Bitcoin blockchain via decentralised calendar servers. The proof can be verified by anyone, independently of Sprinkling Act, using the open-source [OpenTimestamps client](https://github.com/opentimestamps/opentimestamps-client).

## Reports timestamped

| Report | Public URL / DOI | MD5 | Stamped on | `.ots` file |
|---|---|---|---|---|
| EU AI Act Readiness — A Structured Screening of 50 European AI Companies (April 2026) | Concept DOI [10.5281/zenodo.19671328](https://doi.org/10.5281/zenodo.19671328) (resolves to latest version) · v1 [10.5281/zenodo.19671329](https://doi.org/10.5281/zenodo.19671329) · SSRN Abstract ID [6652418](https://ssrn.com/abstract=6652418) | `a134924887bcf2450ebc30eb81850ad1` | 2026-04-27 | `eu-ai-act-readiness-report-april-2026.pdf.ots` |
| EU AI Act Readiness — Annex A — The Deployer Multiplier (May 2026) | Concept DOI [10.5281/zenodo.20042174](https://doi.org/10.5281/zenodo.20042174) (resolves to latest version) · v1 [10.5281/zenodo.20042175](https://doi.org/10.5281/zenodo.20042175) · SSRN Abstract ID [6816018](https://ssrn.com/abstract=6816018) | `267d890a29eda0d1c118f06fd75d5fa5` | 2026-05-06 | `eu-ai-act-readiness-report-annex-a-may-2026.pdf.ots` |
| The AI Act as a Third Structural Pole — A Constrained Retrospective on the Predictive Frame, 2015 to 2026 (Discussion Paper DP-2026-001, May 2026) | Concept DOI [10.5281/zenodo.20343243](https://doi.org/10.5281/zenodo.20343243) (resolves to latest version) · v1 [10.5281/zenodo.20343244](https://doi.org/10.5281/zenodo.20343244) · SSRN Abstract ID [6815659](https://ssrn.com/abstract=6815659) | `e15914828254f94e50dfe061439d40bd` | 2026-05-22 | `eu-ai-act-third-attractor-may-2026.pdf.ots` |
| Contribution to the European Commission stakeholder consultation on the draft Guidelines on Article 6 classification (June 2026) | Submitted 23 June 2026, contribution ID `dc8beacf-74e2-4f63-bfba-6fbf8f51ddcf`. Consultation open 19 May to 23 July 2026; the Commission states that contributions may be made publicly available. Section IV.2, horizontal issues under Article 6(2) | `ebf4149feb94489ee70ec0625469b835` | 2026-06-23 | `ec-consultation-art6-classification-contribution-june-2026.pdf.ots` |
| Sprinkling Act Methodology Card — April 2026 edition (v1.1, expanded) | Snapshot of the gate framework at v1.1. The live page now publishes the analysis method at v1.10: <https://sprinklingact.com/methodology> | `72f75b1a5238001cbe48e457b5761622` | 2026-05-06 | `sprinkling-act-methodology-april-2026.pdf.ots` |

**These documents are stamped, not maintained.** All five predate the August 2026 change of object, and they use the vocabulary of that period. The consultation contribution is the clearest case: it describes Sprinkling Act as an evaluator in AI Act pre-conformity producing position assessments, and both terms were retired in August. It is published as submitted, because that is the only form in which a seal means anything. None of them is edited to match the current position: a proof of existence at a date is worth nothing once the text it covers has been rewritten. What moved, and why, is recorded in [`methodology/TRANSITION.md`](https://github.com/sprinkling-act/methodology/blob/main/TRANSITION.md). A stamped file whose hash no longer matches its published PDF would be a defect; the point of this repository is that anyone can check that for themselves, with the commands below.

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

## Correction of 11 September 2026 — the HAL identifiers

Until this date the table above carried a HAL identifier for the first two
publications: `hal-05631107` and `hal-05631110`. Both are removed, and what
they were is recorded here rather than dropped silently.

Neither identifier resolves. `https://hal.science/hal-05631107` and
`https://hal.science/hal-05631110` both return 404, the HAL API returns no
record for either, and a search of that same API by author name returns none.
No HAL deposit exists, and none appears ever to have been made.

They are removed rather than corrected, because a filing that never happened
has nothing to correct. This is not an edit to a stamped document: the four
sealed files are untouched, as the note above requires. What changed is a
reference column in this README, which has never been part of what the seals
attest.

Nothing else moved. The Zenodo DOIs, the SSRN identifiers, the MD5
fingerprints, the seal dates and the `.ots` files are unchanged, and each stays
verifiable with the commands below, independently of this note.

This repository exists so that a claim can be checked by someone who has no
reason to trust us. A dead link in the column that attests is the one defect it
cannot afford, which is why the correction is recorded and not merely applied.

## Sources

- [OpenTimestamps protocol](https://opentimestamps.org/)
- [opentimestamps-client (GitHub)](https://github.com/opentimestamps/opentimestamps-client)
- [Sprinkling Act — sprinklingact.com](https://sprinklingact.com)
