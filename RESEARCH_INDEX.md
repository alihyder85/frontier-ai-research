# Research Index

The master entry point into this library. Every row corresponds to one entry in
[`metadata/papers.yaml`](metadata/papers.yaml) — that file is the machine-readable source of truth;
this table is the human-readable view. "Builds On" / "Leads To" describe documented research
lineage (an explicit citation, a stated successor system, or a direct methodological dependency),
not speculative connections.

Status legend: ✅ downloaded and validated in this repo · 🔗 manual download required (see
[`metadata/download-report.md`](metadata/download-report.md)).

| # | Paper | Year | Category | Core Idea | Key Concepts | Builds On | Leads To | Status |
|---|-------|-----:|----------|-----------|---------------|-----------|----------|:---:|
| 01 | [Attention Is All You Need](01-architecture-and-scaling/01-attention-is-all-you-need.pdf) | 2017 | Architecture & Scaling | Replace recurrence/convolution with self-attention alone | attention, transformer, self-attention | — | 02, 03, 06 | ✅ |
| 02 | [BERT](01-architecture-and-scaling/02-bert.pdf) | 2018 | Architecture & Scaling | Bidirectional masked-LM pretraining for language understanding | masked LM, bidirectional encoding, pretraining | 01 | 04 | ✅ |
| 03 | [Scaling Laws for Neural Language Models](01-architecture-and-scaling/03-scaling-laws-for-neural-language-models.pdf) | 2020 | Architecture & Scaling | Loss follows predictable power laws in model size, data, compute | scaling laws, compute-optimal training | 01 | 04, 05 | ✅ |
| 04 | [GPT-3](01-architecture-and-scaling/04-gpt-3.pdf) | 2020 | Architecture & Scaling | Scale alone yields strong few-shot, in-context learning | in-context learning, few-shot learning | 01, 03 | 05, 07, 14 | ✅ |
| 05 | [Chinchilla](01-architecture-and-scaling/05-chinchilla.pdf) | 2022 | Architecture & Scaling | Prior LLMs were undertrained on data relative to parameters | compute-optimal scaling | 03, 04 | 16, 17 | ✅ |
| 06 | [Switch Transformer](01-architecture-and-scaling/06-switch-transformer.pdf) | 2022 | Architecture & Scaling | Sparse mixture-of-experts scales parameters without proportional compute | mixture-of-experts, sparsity | 01 | 17 | ✅ |
| 07 | [InstructGPT](02-alignment-and-multimodal/01-instructgpt.pdf) | 2022 | Alignment & Multimodal | RLHF aligns LM outputs with human intent | RLHF, instruction tuning | 04 | 16, 28 | ✅ |
| 08 | [CLIP](02-alignment-and-multimodal/02-clip.pdf) | 2021 | Alignment & Multimodal | Contrastive image-text pretraining yields zero-shot visual transfer | contrastive learning, vision-language pretraining | 01 | — | ✅ |
| 09 | [DDPM](02-alignment-and-multimodal/03-ddpm.pdf) | 2020 | Alignment & Multimodal | Iterative denoising as a generative process | diffusion models, denoising | — | — | ✅ |
| 10 | [Megatron-LM](03-systems-and-efficiency/01-megatron-lm.pdf) | 2019 | Systems & Efficiency | Tensor-parallel training of multi-billion-parameter transformers | model parallelism, distributed training | 01 | 11, 17 | ✅ |
| 11 | [ZeRO](03-systems-and-efficiency/02-zero.pdf) | 2019 | Systems & Efficiency | Eliminate memory redundancy across data-parallel replicas | memory optimization, data parallelism | 10 | — | ✅ |
| 12 | [vLLM / PagedAttention](03-systems-and-efficiency/03-vllm-pagedattention.pdf) | 2023 | Systems & Efficiency | Paged KV-cache memory management for fast LLM serving | KV cache, inference serving | 01 | — | ✅ |
| 13 | [LoRA](03-systems-and-efficiency/04-lora.pdf) | 2021 | Systems & Efficiency | Low-rank adapters make fine-tuning cheap | parameter-efficient fine-tuning | 01, 04 | — | ✅ |
| 14 | [Chain-of-Thought Prompting](04-reasoning-and-test-time-compute/01-chain-of-thought-prompting.pdf) | 2022 | Reasoning & Test-Time Compute | Prompting for intermediate steps unlocks emergent reasoning | chain-of-thought, prompting | 04 | 15, 16, 20 | ✅ |
| 15 | [Scaling Test-Time Compute](04-reasoning-and-test-time-compute/02-scaling-test-time-compute.pdf) | 2024 | Reasoning & Test-Time Compute | Spending more compute at inference can beat larger models | test-time compute, inference-time scaling | 14 | 16, 31 | ✅ |
| 16 | [DeepSeek-R1](04-reasoning-and-test-time-compute/03-deepseek-r1.pdf) | 2025 | Reasoning & Test-Time Compute | Pure/large-scale RL incentivizes emergent reasoning in LLMs | RL, reasoning models, self-verification | 07, 14, 17 | — | ✅ |
| 17 | [DeepSeek-V3](04-reasoning-and-test-time-compute/04-deepseek-v3.pdf) | 2024 | Reasoning & Test-Time Compute | Efficient MoE + multi-head latent attention at frontier scale | MoE, latent attention | 05, 06, 10 | 16 | ✅ |
| 18 | [Universal Transformers](05-latent-reasoning-and-world-models/01-universal-transformers.pdf) | 2018 | Latent Reasoning & World Models | Recurrence-in-depth with adaptive computation per token | recurrence in depth, adaptive computation | 01 | 33 | ✅ |
| 19 | [Deep Equilibrium Models](05-latent-reasoning-and-world-models/02-deep-equilibrium-models.pdf) | 2019 | Latent Reasoning & World Models | Model infinite-depth networks as a fixed point directly | implicit models, fixed-point iteration | — | — | ✅ |
| 20 | [Coconut](05-latent-reasoning-and-world-models/03-coconut-chain-of-continuous-thought.pdf) | 2024 | Latent Reasoning & World Models | Reason in continuous latent space instead of token space | latent reasoning, continuous thought | 14 | — | ✅ |
| 21 | JEPA — A Path Towards Autonomous Machine Intelligence | 2022 | Latent Reasoning & World Models | Predict in representation space, not pixel/token space | JEPA, world models, self-supervised learning | 01 | — | 🔗 |
| 22 | [TTT (Test-Time Training)](05-latent-reasoning-and-world-models/05-ttt-test-time-training.pdf) | 2024 | Latent Reasoning & World Models | Hidden state itself is a model updated at test time | test-time training, expressive hidden state | 01 | — | ✅ |
| 23 | AlphaGeometry | 2024 | Neuro-Symbolic AI & Agents | Neuro-symbolic system solves olympiad geometry via synthetic data | neuro-symbolic reasoning, synthetic data | 01 | 24 | 🔗 |
| 24 | [AlphaProof (Nexus)](06-neuro-symbolic-and-agents/02-alphaproof.pdf) | 2026 | Neuro-Symbolic AI & Agents | RL-driven formal proof search for mathematics research | formal proof search, RL | 23 | — | ✅ |
| 25 | [ARC-AGI / On the Measure of Intelligence](06-neuro-symbolic-and-agents/03-arc-agi.pdf) | 2019 | Neuro-Symbolic AI & Agents | Defines intelligence as skill-acquisition efficiency; introduces ARC | intelligence measurement, generalization | — | — | ✅ |
| 26 | [SWE-bench](06-neuro-symbolic-and-agents/04-swe-bench.pdf) | 2024 | Neuro-Symbolic AI & Agents | Benchmark: can LMs resolve real GitHub issues end-to-end? | software agents, benchmark | 04 | — | ✅ |
| 27 | [AlphaEvolve](06-neuro-symbolic-and-agents/05-alphaevolve.pdf) | 2025 | Neuro-Symbolic AI & Agents | LLM-guided evolutionary search discovers new algorithms | evolutionary search, agentic coding | 26 | — | ✅ |
| 28 | [Alignment Faking](07-safety-and-governance/01-alignment-faking.pdf) | 2024 | Safety & Governance | Models can strategically comply during training, defect after | deceptive alignment, RLHF robustness | 07 | — | ✅ |
| 29 | [Artificial Hivemind](07-safety-and-governance/02-artificial-hivemind.pdf) | 2025 | Safety & Governance | RLHF-trained LMs converge toward homogeneous outputs | model homogeneity, diversity collapse | 07 | — | ✅ |
| 30 | [OWASP Top 10 for Agentic Applications](07-safety-and-governance/03-owasp-top-10-agentic-applications.pdf) | 2025 | Safety & Governance | Top 10 security risks specific to autonomous agent systems | agentic security, tool misuse | — | — | ✅ |
| 31 | [When More Thinking Hurts](08-frontier-and-future/01-when-more-thinking-hurts.pdf) | 2026 | Frontier & Future | Extended test-time reasoning chains can degrade accuracy | overthinking, reasoning efficiency | 15 | — | ✅ |
| 32 | [Claude Fable 5.1 & Mythos 5.1 System Card](08-frontier-and-future/02-claude-fable-5.1-system-card.pdf) | 2026 | Frontier & Future | Frontier system card: adaptive thinking effort for long-horizon agents | adaptive thinking, agentic safety evaluation | 07, 28 | — | ✅ |
| 33 | [GPT-6 Astra System Card](08-frontier-and-future/03-gpt-6-astra-system-card.pdf) | 2026 | Frontier & Future | Frontier system card: recurrent-depth reasoning, CoT monitorability | recurrent depth reasoning, CoT monitorability | 18, 07 | — | ✅ |

## By category

| Category | Downloaded | Total |
|---|---:|---:|
| 01 — Architecture & Scaling | 6 | 6 |
| 02 — Alignment & Multimodal | 3 | 3 |
| 03 — Systems & Efficiency | 4 | 4 |
| 04 — Reasoning & Test-Time Compute | 4 | 4 |
| 05 — Latent Reasoning & World Models | 4 | 5 |
| 06 — Neuro-Symbolic AI & Agents | 4 | 5 |
| 07 — Safety & Governance | 3 | 3 |
| 08 — Frontier & Future | 3 | 3 |
| **Total** | **31** | **33** |

See [`LEARNING_PATH.md`](LEARNING_PATH.md) for a guided reading order, and
[`metadata/download-report.md`](metadata/download-report.md) for the two outstanding manual downloads.
