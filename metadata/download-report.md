# Download Report

Generated during initial library build. All arXiv PDFs were fetched directly from `arxiv.org/pdf/<id>`
(the authoritative, open-access source for every arXiv-hosted paper). Non-arXiv documents were
fetched from official/primary sources: Anthropic's CDN, OpenAI's Deployment Safety Hub, and the
OWASP GenAI Security Project's own download endpoint.

Every downloaded file was validated to:
- exist on disk and start with a `%PDF` header
- open successfully with `pypdf`
- have a first-page text extraction whose title matches the intended paper
- have a page count consistent with the known length of the work
- not be suspiciously tiny (all downloaded files are >100KB)

## Successful downloads: 31 / 33

| # | Paper | Source | Pages | Verified Title Match |
|---|-------|--------|------:|:---:|
| 01 | Attention Is All You Need | arxiv.org/abs/1706.03762 | 15 | ✅ |
| 02 | BERT | arxiv.org/abs/1810.04805 | 16 | ✅ |
| 03 | Scaling Laws for Neural Language Models | arxiv.org/abs/2001.08361 | 30 | ✅ |
| 04 | GPT-3 | arxiv.org/abs/2005.14165 | 75 | ✅ |
| 05 | Chinchilla | arxiv.org/abs/2203.15556 | 36 | ✅ |
| 06 | Switch Transformer | arxiv.org/abs/2101.03961 | 40 | ✅ |
| 07 | InstructGPT | arxiv.org/abs/2203.02155 | 68 | ✅ |
| 08 | CLIP | arxiv.org/abs/2103.00020 | 48 | ✅ |
| 09 | DDPM | arxiv.org/abs/2006.11239 | 25 | ✅ |
| 10 | Megatron-LM | arxiv.org/abs/1909.08053 | 15 | ✅ |
| 11 | ZeRO | arxiv.org/abs/1910.02054 | 24 | ✅ |
| 12 | vLLM / PagedAttention | arxiv.org/abs/2309.06180 | 16 | ✅ |
| 13 | LoRA | arxiv.org/abs/2106.09685 | 26 | ✅ |
| 14 | Chain-of-Thought Prompting | arxiv.org/abs/2201.11903 | 43 | ✅ |
| 15 | Scaling Test-Time Compute | arxiv.org/abs/2408.03314 | 37 | ✅ |
| 16 | DeepSeek-R1 | arxiv.org/abs/2501.12948 | 86 | ✅ |
| 17 | DeepSeek-V3 | arxiv.org/abs/2412.19437 | 53 | ✅ |
| 18 | Universal Transformers | arxiv.org/abs/1807.03819 | 23 | ✅ |
| 19 | Deep Equilibrium Models | arxiv.org/abs/1909.01377 | 16 | ✅ |
| 20 | Coconut | arxiv.org/abs/2412.06769 | 18 | ✅ |
| 22 | TTT (Test-Time Training) | arxiv.org/abs/2407.04620 | 33 | ✅ |
| 24 | AlphaProof (Nexus) | arxiv.org/abs/2605.22763 | 60 | ✅ |
| 25 | ARC-AGI / On the Measure of Intelligence | arxiv.org/abs/1911.01547 | 64 | ✅ |
| 26 | SWE-bench | arxiv.org/abs/2310.06770 | 52 | ✅ |
| 27 | AlphaEvolve | arxiv.org/abs/2506.13131 | 44 | ✅ |
| 28 | Alignment Faking | arxiv.org/abs/2412.14093 | 137 | ✅ |
| 29 | Artificial Hivemind | arxiv.org/abs/2510.22954 | 70 | ✅ |
| 30 | OWASP Top 10 for Agentic Applications | genai.owasp.org (official download link) | 57 | ✅ |
| 31 | When More Thinking Hurts | arxiv.org/abs/2604.10739 | 11 | ✅ |
| 32 | Claude Fable 5.1 & Mythos 5.1 System Card | www-cdn.anthropic.com (official) | 212 | ✅ |
| 33 | GPT-6 Astra System Card | deploymentsafety.openai.com (official) | 118 | ✅ |

## Requires manual download: 2 / 33

### 21 — JEPA: "A Path Towards Autonomous Machine Intelligence"

```
Paper: A Path Towards Autonomous Machine Intelligence (Yann LeCun, Meta AI, 2022)
Expected source: https://openreview.net/pdf?id=BZ5a1r-kVsf
Status: FAILED — not downloaded
Reason: OpenReview returns HTTP 403 (bot/anti-scraping protection) to automated
        requests, including with browser User-Agent and Referer headers. This
        paper was never posted to arXiv — OpenReview is its only official host.
Recommended manual source: https://openreview.net/forum?id=BZ5a1r-kVsf
        (open the forum page in a browser and use the "Download PDF" button)
```

### 23 — AlphaGeometry: "Solving Olympiad Geometry without Human Demonstrations"

```
Paper: Solving Olympiad Geometry without Human Demonstrations
       (Trinh, Wu, Le, He, Luong — Google DeepMind, Nature 625, 2024)
Expected source: https://www.nature.com/articles/s41586-023-06747-5
Status: FAILED — not downloaded
Reason: The Nature article itself is paywalled. The open-access mirror on
        PubMed Central (PMC10794143) and Europe PMC both block automated
        (curl/scripted) requests behind CAPTCHA/Cloudflare bot-challenge pages,
        which this process will not attempt to bypass.
Recommended manual source: https://pmc.ncbi.nlm.nih.gov/articles/PMC10794143/
        (free, open-access — open in a browser and use the PDF download button)
        Also see the official DeepMind write-up:
        https://deepmind.google/blog/alphageometry-an-olympiad-level-ai-system-for-geometry/
```

## Note on source-link resolution

The original task listed three papers behind shortened `Inkd.in/...` links (LinkedIn short URLs
that did not resolve to a live redirect target: JEPA, AlphaGeometry, and — resolved successfully —
the two 2026 frontier system cards). Rather than fetch an unverified short-link domain, each was
traced to its authoritative primary source via web search:

- JEPA → OpenReview (Meta AI's own submission venue for the paper)
- AlphaGeometry → Nature / PubMed Central (Google DeepMind's peer-reviewed publication)
- Claude Fable 5.1 & Mythos 5.1 System Card → `anthropic.com` → official Anthropic CDN PDF
- GPT-6 Astra System Card → `openai.com` → OpenAI's official Deployment Safety Hub PDF
