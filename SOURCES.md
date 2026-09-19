# Sources

Authoritative source used for every document in this library, and how it was resolved.

## Resolution rules applied

1. arXiv papers → downloaded directly from `arxiv.org/pdf/<id>` (arXiv's own PDF endpoint).
2. Google DeepMind papers → arXiv when posted there, otherwise the DeepMind blog/Nature publication.
3. Anthropic material → Anthropic's own CDN (`www-cdn.anthropic.com`).
4. OpenAI material → OpenAI's Deployment Safety Hub (`deploymentsafety.openai.com`) / `cdn.openai.com`.
5. OWASP material → `genai.owasp.org`'s own download endpoint.
6. Benchmark papers (ARC-AGI, SWE-bench) → the original arXiv paper.
7. No third-party paper-mirror or aggregator site was used for any document.
8. No paywalled or access-controlled content was bypassed; where a canonical source required
   interactive bot-verification (OpenReview, PubMed Central), the item was left for manual
   download rather than circumvented — see `metadata/download-report.md`.

## Note on shortened links in the original request

Three items in the original research list were given as `Inkd.in/...` shortened URLs (a
non-resolving variant of LinkedIn's `lnkd.in` shortener). Rather than fetch an unverified,
non-canonical short-link domain, each was traced independently to its authoritative primary
source via web search — see `metadata/download-report.md` for the resolution notes on JEPA and
AlphaGeometry, and the table below for the two system cards, which resolved successfully.

## Full source table

| # | Document | Authoritative Source |
|---|----------|----------------------|
| 01 | Attention Is All You Need | https://arxiv.org/abs/1706.03762 |
| 02 | BERT | https://arxiv.org/abs/1810.04805 |
| 03 | Scaling Laws for Neural Language Models | https://arxiv.org/abs/2001.08361 |
| 04 | GPT-3 | https://arxiv.org/abs/2005.14165 |
| 05 | Chinchilla | https://arxiv.org/abs/2203.15556 |
| 06 | Switch Transformer | https://arxiv.org/abs/2101.03961 |
| 07 | InstructGPT | https://arxiv.org/abs/2203.02155 |
| 08 | CLIP | https://arxiv.org/abs/2103.00020 |
| 09 | DDPM | https://arxiv.org/abs/2006.11239 |
| 10 | Megatron-LM | https://arxiv.org/abs/1909.08053 |
| 11 | ZeRO | https://arxiv.org/abs/1910.02054 |
| 12 | vLLM / PagedAttention | https://arxiv.org/abs/2309.06180 |
| 13 | LoRA | https://arxiv.org/abs/2106.09685 |
| 14 | Chain-of-Thought Prompting | https://arxiv.org/abs/2201.11903 |
| 15 | Scaling Test-Time Compute | https://arxiv.org/abs/2408.03314 |
| 16 | DeepSeek-R1 | https://arxiv.org/abs/2501.12948 |
| 17 | DeepSeek-V3 | https://arxiv.org/abs/2412.19437 |
| 18 | Universal Transformers | https://arxiv.org/abs/1807.03819 |
| 19 | Deep Equilibrium Models | https://arxiv.org/abs/1909.01377 |
| 20 | Coconut | https://arxiv.org/abs/2412.06769 |
| 21 | JEPA | https://openreview.net/forum?id=BZ5a1r-kVsf (manual download required) |
| 22 | TTT (Test-Time Training) | https://arxiv.org/abs/2407.04620 |
| 23 | AlphaGeometry | https://www.nature.com/articles/s41586-023-06747-5 (manual download required) |
| 24 | AlphaProof (Nexus) | https://arxiv.org/abs/2605.22763 |
| 25 | ARC-AGI | https://arxiv.org/abs/1911.01547 |
| 26 | SWE-bench | https://arxiv.org/abs/2310.06770 |
| 27 | AlphaEvolve | https://arxiv.org/abs/2506.13131 |
| 28 | Alignment Faking | https://arxiv.org/abs/2412.14093 |
| 29 | Artificial Hivemind | https://arxiv.org/abs/2510.22954 |
| 30 | OWASP Top 10 for Agentic Applications | https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/ |
| 31 | When More Thinking Hurts | https://arxiv.org/abs/2604.10739 |
| 32 | Claude Fable 5.1 & Mythos 5.1 System Card | https://www.anthropic.com/claude-fable-and-mythos-5-1 |
| 33 | GPT-6 Astra System Card | https://openai.com/index/gpt-6-astra/ |
