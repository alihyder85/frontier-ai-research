# Frontier AI Research

A personal, structured research library tracing the evolution from Transformers and LLM scaling to
reasoning, agents, neuro-symbolic AI, safety, and frontier AI systems. It holds the actual papers
(where redistribution terms allow), organized by research theme, alongside machine-readable
metadata, a cross-referenced index, and a guided learning path.

## Purpose

This isn't a bookmark list — it's a working library: papers land in a consistent folder structure
with deterministic filenames, get validated (not just downloaded), and are cross-linked so the
*relationships between ideas* are as discoverable as the ideas themselves. The goal is to make it
possible to answer "what should I read to understand X, and what did X make possible?" in seconds.

## Research areas

| Folder | Theme |
|---|---|
| [`01-architecture-and-scaling/`](01-architecture-and-scaling/) | Transformers, pretraining objectives, scaling laws, mixture-of-experts |
| [`02-alignment-and-multimodal/`](02-alignment-and-multimodal/) | RLHF/instruction tuning, vision-language and diffusion models |
| [`03-systems-and-efficiency/`](03-systems-and-efficiency/) | Distributed training, memory optimization, efficient inference, PEFT |
| [`04-reasoning-and-test-time-compute/`](04-reasoning-and-test-time-compute/) | Chain-of-thought, inference-time search, RL-trained reasoning models |
| [`05-latent-reasoning-and-world-models/`](05-latent-reasoning-and-world-models/) | Reasoning outside token space, recurrence-in-depth, predictive world models |
| [`06-neuro-symbolic-and-agents/`](06-neuro-symbolic-and-agents/) | Symbolic+neural hybrids, formal proof search, coding/software agents |
| [`07-safety-and-governance/`](07-safety-and-governance/) | Deceptive alignment, model homogeneity, agentic security frameworks |
| [`08-frontier-and-future/`](08-frontier-and-future/) | Current frontier system cards and open problems in test-time reasoning |
| [`metadata/`](metadata/) | `papers.yaml` (machine-readable catalog) and `download-report.md` (provenance/validation log) |

## How papers are organized

- Filenames are deterministic: `NN-short-descriptive-name.pdf`, numbered within each category folder.
- Every paper has a corresponding entry in [`metadata/papers.yaml`](metadata/papers.yaml) with its
  title, year, source URL, key concepts, and documented `builds_on` / `leads_to` relationships to
  other papers in the library (by numeric ID).
- [`RESEARCH_INDEX.md`](RESEARCH_INDEX.md) is the human-readable view of that same catalog — start there.

## How to follow the learning path

[`LEARNING_PATH.md`](LEARNING_PATH.md) sequences all 33 items into 20 stages, from deep learning
foundations through frontier reasoning systems. Each stage lists prerequisites, key concepts, a
gate-check question, and a small hands-on experiment — read linearly, or jump to the stage covering
whatever you're currently trying to understand.

## Relationship between papers

Research doesn't happen in a vacuum — Chinchilla revises GPT-3's scaling assumptions, DeepSeek-R1
builds on both InstructGPT's RLHF pipeline and DeepSeek-V3's base model, AlphaProof extends
AlphaGeometry's neuro-symbolic recipe to a new domain. These lineages are tracked explicitly as
`builds_on` / `leads_to` fields in `papers.yaml` rather than left implicit, so you can trace an idea
forward or backward through the literature.

## Source verification principles

Every document here was fetched from its **authoritative source** — arXiv's own PDF endpoint for
preprints, the publisher's site for peer-reviewed work, and the issuing organization's own site for
system cards and standards documents. No third-party paper-mirror sites were used, and no paywall,
login wall, or CAPTCHA was bypassed to obtain a document. Where a canonical source blocked automated
access, the item was left for manual download rather than substituted or faked — see
[`metadata/download-report.md`](metadata/download-report.md) for the two current exceptions, and
[`SOURCES.md`](SOURCES.md) for the full source table. Licensing/redistribution posture per document
is tracked in [`LICENSE-NOTES.md`](LICENSE-NOTES.md).

## Using this repository with AI coding/research assistants

The structure is designed to be machine-legible:

- Point an assistant at `metadata/papers.yaml` to get structured context (title, concepts,
  prerequisites, lineage) without needing to parse PDFs.
- Ask it to trace a concept's lineage by following `builds_on`/`leads_to` chains in the YAML.
- For deep questions about a specific paper's content, point it at the PDF path directly —
  `pdf_path` in the YAML gives the exact relative path.
- When adding new papers (see below), ask the assistant to extend `papers.yaml` and
  `RESEARCH_INDEX.md` together so the two stay in sync.

## Adding new research

1. Pick the right category folder (or propose a new one — see **Future extensibility** below).
2. Name the file `NN-short-descriptive-name.pdf`, continuing that folder's numbering.
3. Download from the authoritative source only (see **Source verification principles**).
4. Validate: confirm it's a real PDF, opens correctly, and the extracted title matches.
5. Add an entry to `metadata/papers.yaml` — including real `builds_on`/`leads_to` links to existing
   papers where a genuine dependency exists.
6. Add a row to `RESEARCH_INDEX.md`.
7. If redistribution terms are unclear or restrictive, commit metadata only (no PDF) and note it in
   `LICENSE-NOTES.md`.

## High-level map

```
                   FRONTIER AI
                       │
        ┌──────────────┼──────────────┐
        │              │              │
    Reasoning       Agents       World Models
        │              │              │
   Test-Time       Tool Use      Latent State
    Compute        Planning       Learning
        │              │              │
        └──────────────┼──────────────┘
                       │
                    LLMs
                       │
              Transformers
                       │
             Attention / DL
                       │
                ML Foundations
```

## Future extensibility

This library is meant to grow into a long-term AI research knowledge base, not stay a one-time
download. Planned (not yet created) top-level additions:

```
09-new-research/
10-experiments/
11-implementation-notes/
12-paper-summaries/
13-agent-projects/
14-model-evaluations/
```

Create these only when you actually have content for them — an empty folder documents nothing.

## Status

31 of 33 requested documents are downloaded and validated in this repository. 2 require manual
download due to bot-protection on their canonical hosts (OpenReview, PubMed Central) — see
[`metadata/download-report.md`](metadata/download-report.md) for direct links.
