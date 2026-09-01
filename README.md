# Mom & Baby Mobile Health Centers — evaluation dashboard

**Live: https://drsamnnorom.github.io/mhc-evaluation-dashboard/**

One self-contained HTML file. It opens on a lock screen; the correct
passphrase decrypts the whole dashboard in your browser and replaces the page
with it. Nothing is fetched at runtime and nothing is sent anywhere — there is
no server behind this, only a static file.

## What is in this repository

`index.html` is the evaluation report encrypted with **AES-256-GCM**, under a
key stretched from a 100-bit passphrase by **1,200,000 rounds of
PBKDF2-SHA256**. Without the passphrase the file is noise: no figures, no site
names, no page text.

**The passphrase is not in this repository and must never be put in one** —
not in this README, not in an issue, not in a commit message. It reaches
readers by a different channel from the link, or the encryption is decoration.

This is protection for a file at rest. It is not access control: anyone
holding the passphrase, or an unlocked copy saved from an open session, holds
the contents. There is no reset and no revocation.

## What the dashboard covers

Seven mobile health clinics, six categories — service locations, programme
reach, service delivery, patient demographics, and two internal categories
behind a separate PIN covering data quality and known gaps. Every figure is
the sites' own submission, published as filed.

Four rules govern every number in it:

- **A blank is not a zero.** Nothing reported and a reported nothing are
  different facts, drawn differently.
- **Every share states its denominator**, beside the share, never in a
  footnote.
- **Nothing is trended across a boundary its comparability tier forbids.**
  The 2026 survey redesign replaced most items; each metric records whether it
  survived.
- **No figure relies on colour alone.** Every chart has a table view.

## The pipeline that builds it

The code — metric registry, ETL, warehouse, renderer, brand system and
checkers — is a separate repository. No programme data is in either one.

---

Applied Research and Evaluation, March of Dimes.
