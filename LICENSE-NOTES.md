# License & Redistribution Notes

This repository is **private** and intended as a personal research library, not a redistribution
channel. Even so, each document's licensing/redistribution posture is recorded below so this stays
defensible if the repository's visibility ever changes.

## arXiv papers (items 01–20, 22, 24–29, 31)

All arXiv papers in this library were posted by their authors under arXiv's standard non-exclusive
license (each individual paper specifies CC BY 4.0, CC BY-NC-SA, or arXiv's default perpetual
non-exclusive license — check the "License" field on each paper's `arxiv.org/abs/<id>` page for the
exact terms). arXiv preprints are explicitly intended for open reading and redistribution of the
PDF as posted; downloading the PDF from arXiv's own server is standard practice and was the method
used here. No terms were bypassed.

## OWASP Top 10 for Agentic Applications (item 30)

Published by the OWASP GenAI Security Project under OWASP's standard open-content model (OWASP
project material is generally released for free reuse, typically CC BY-SA). Downloaded from
OWASP's own official download link.

## Claude Fable 5.1 & Mythos 5.1 System Card (item 32)

Anthropic publishes system cards as public documents intended for broad reading; downloaded from
Anthropic's own CDN. Anthropic retains copyright over the document text; redistribution here is as
a personal reference copy from the primary source, unmodified.

## GPT-6 Astra System Card (item 33)

OpenAI publishes system cards as public safety documents intended for broad reading; downloaded
from OpenAI's own Deployment Safety Hub. OpenAI retains copyright over the document text;
redistribution here is as a personal reference copy from the primary source, unmodified.

## Items excluded from Git (manual download required)

Two documents are **not** stored in this repository because their authoritative hosts required
interactive bot-verification that this process did not attempt to bypass:

- **JEPA** ("A Path Towards Autonomous Machine Intelligence") — OpenReview submission, Meta AI.
  Meta's non-archival position paper; OpenReview hosts it for open reading.
- **AlphaGeometry** ("Solving Olympiad Geometry without Human Demonstrations") — published in
  *Nature* (paywalled) with an open-access mirror on PubMed Central under the NIH Public Access
  Policy.

For both, only metadata and the source URL are tracked in `metadata/papers.yaml`; see
`metadata/download-report.md` for manual-download instructions. This keeps the repository's
contents limited to documents whose redistribution terms are clear and whose source was fetched
without circumventing any access control.

## General policy for future additions

Before adding a new PDF to this repository:

1. Confirm it comes from the paper's official host (arXiv, the publisher, or the organization's own
   site) — not a third-party aggregator.
2. Check whether the source explicitly restricts redistribution. If restricted or unclear, commit
   only the entry in `metadata/papers.yaml` (title, source URL, status) and leave the PDF out of Git.
3. Never bypass a paywall, CAPTCHA, or login wall to obtain a document.
