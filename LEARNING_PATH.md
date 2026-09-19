# Learning Path: Foundations → Frontier AI

A progressive reading order through this library. Each stage lists what to read, what you need
already, the concepts you should walk away with, a checkpoint question to gate moving on, and a
small hands-on experiment to cement the idea. Papers are referenced by their index number from
[`RESEARCH_INDEX.md`](RESEARCH_INDEX.md).

```
Deep Learning Foundations
        ↓
Attention
        ↓
Transformers
        ↓
BERT / GPT
        ↓
Scaling Laws
        ↓
Compute-Optimal Training
        ↓
Mixture-of-Experts
        ↓
Alignment
        ↓
Efficient Training
        ↓
Efficient Inference
        ↓
Multimodal Models
        ↓
Chain-of-Thought
        ↓
Test-Time Compute
        ↓
RL-Based Reasoning
        ↓
Latent Reasoning
        ↓
World Models
        ↓
Agents
        ↓
Neuro-Symbolic AI
        ↓
AI Safety
        ↓
Frontier AI
```

---

### 1. Deep Learning Foundations
*Prerequisite stage — not a paper in this repo.* Ensure you're comfortable with: backpropagation,
gradient descent variants, softmax/cross-entropy, RNNs/LSTMs and why they struggle with long-range
dependencies. (Any standard DL course covers this; it's the on-ramp to paper 01.)

- **Key concepts**: sequence modeling, vanishing gradients, embeddings
- **Gate check**: Can you explain why RNNs struggle to model dependencies across long sequences?
- **Experiment**: Train a small char-RNN on a toy corpus and watch it fail to track long-range structure.

### 2. Attention
- **Read**: 01 — Attention Is All You Need (skim just the attention mechanism section first)
- **Prerequisites**: Stage 1
- **Key concepts**: query/key/value, scaled dot-product attention, multi-head attention
- **Gate check**: Can you derive attention weights by hand for a 3-token toy example?
- **Experiment**: Implement scaled dot-product attention from scratch in ~20 lines of NumPy.

### 3. Transformers
- **Read**: 01 — Attention Is All You Need (full paper)
- **Prerequisites**: Stage 2
- **Key concepts**: positional encoding, residual streams, layer norm placement, encoder-decoder architecture
- **Gate check**: Could you draw the full transformer block diagram from memory?
- **Experiment**: Implement a minimal transformer encoder and overfit it on a toy copy task.

### 4. BERT / GPT
- **Read**: 02 — BERT, 04 — GPT-3 (architecture section)
- **Prerequisites**: Stage 3
- **Key concepts**: masked LM vs. autoregressive LM, pretrain/fine-tune paradigm, in-context learning
- **Gate check**: Explain why BERT is bidirectional but can't generate text autoregressively, and why GPT is the reverse.
- **Experiment**: Fine-tune a small pretrained BERT on a text-classification task; separately, prompt a GPT-family model few-shot on the same task and compare.

### 5. Scaling Laws
- **Read**: 03 — Scaling Laws for Neural Language Models
- **Prerequisites**: Stage 4
- **Key concepts**: power-law loss curves, compute/data/parameter tradeoffs
- **Gate check**: Given a compute budget, could you sketch how loss should scale?
- **Experiment**: Train the same small transformer at 3 sizes and plot loss vs. parameter count on a log-log axis.

### 6. Compute-Optimal Training
- **Read**: 05 — Chinchilla
- **Prerequisites**: Stage 5
- **Key concepts**: data-parameter balance, "undertrained" large models
- **Gate check**: Why was GPT-3-scale training considered compute-inefficient in hindsight?
- **Experiment**: Given a fixed FLOP budget, compute the Chinchilla-optimal parameter/token split.

### 7. Mixture-of-Experts
- **Read**: 06 — Switch Transformer
- **Prerequisites**: Stage 6
- **Key concepts**: sparse activation, expert routing, load balancing
- **Gate check**: Why does MoE decouple parameter count from inference FLOPs?
- **Experiment**: Implement a toy top-1 MoE router over 4 experts on a small dataset.

### 8. Alignment
- **Read**: 07 — InstructGPT
- **Prerequisites**: Stage 4
- **Key concepts**: RLHF, reward modeling, instruction tuning, PPO
- **Gate check**: Trace the 3-step InstructGPT pipeline (SFT → reward model → RL) end to end.
- **Experiment**: Collect pairwise preference labels on model outputs for a toy task and train a tiny reward model.

### 9. Efficient Training
- **Read**: 10 — Megatron-LM, 11 — ZeRO
- **Prerequisites**: Stage 6
- **Key concepts**: tensor/pipeline/data parallelism, optimizer state sharding
- **Gate check**: Explain the memory savings ZeRO stage 1/2/3 each provide.
- **Experiment**: Read PyTorch FSDP docs and map its sharding stages onto ZeRO's terminology.

### 10. Efficient Inference
- **Read**: 12 — vLLM / PagedAttention, 13 — LoRA
- **Prerequisites**: Stage 9
- **Key concepts**: KV-cache fragmentation, paged memory, low-rank adapters
- **Gate check**: Why does KV-cache memory — not parameter count — bottleneck serving throughput?
- **Experiment**: Fine-tune a small model with LoRA vs. full fine-tuning and compare trainable-parameter counts.

### 11. Multimodal Models
- **Read**: 08 — CLIP, 09 — DDPM
- **Prerequisites**: Stage 4
- **Key concepts**: contrastive vision-language pretraining, diffusion-based generation
- **Gate check**: Contrast CLIP's discriminative objective with DDPM's generative one.
- **Experiment**: Use a pretrained CLIP model for zero-shot image classification on a small custom label set.

### 12. Chain-of-Thought
- **Read**: 14 — Chain-of-Thought Prompting
- **Prerequisites**: Stage 4
- **Key concepts**: intermediate reasoning steps, emergent capability, few-shot exemplars
- **Gate check**: Why does CoT help more on larger models than smaller ones?
- **Experiment**: Compare direct-answer vs. CoT prompting on a set of arithmetic word problems.

### 13. Test-Time Compute
- **Read**: 15 — Scaling Test-Time Compute
- **Prerequisites**: Stage 12
- **Key concepts**: inference-time search, verifier-guided sampling, compute reallocation
- **Gate check**: Under what conditions does spending more inference compute beat a bigger model?
- **Experiment**: Implement best-of-N sampling with a simple verifier and measure accuracy vs. N.

### 14. RL-Based Reasoning
- **Read**: 16 — DeepSeek-R1, 17 — DeepSeek-V3
- **Prerequisites**: Stages 8, 13
- **Key concepts**: large-scale RL for reasoning, self-verification, cold-start SFT + RL
- **Gate check**: What did R1 show about RL incentivizing reasoning without dense step supervision?
- **Experiment**: Read R1's ablation on RL-only vs. RL+SFT-cold-start and summarize the tradeoffs.

### 15. Latent Reasoning
- **Read**: 20 — Coconut, 18 — Universal Transformers, 19 — Deep Equilibrium Models
- **Prerequisites**: Stage 12
- **Key concepts**: reasoning outside token space, recurrence-in-depth, fixed-point computation
- **Gate check**: What's lost and gained by reasoning in continuous latent space vs. discrete tokens?
- **Experiment**: Compare token counts and wall-clock time for CoT vs. a latent-reasoning approach on the same task class.

### 16. World Models
- **Read**: 21 — JEPA *(see `metadata/download-report.md` for manual download)*, 22 — TTT
- **Prerequisites**: Stage 15
- **Key concepts**: predictive representation learning, energy-based models, test-time weight updates
- **Gate check**: Why does JEPA predict in representation space rather than pixel/token space?
- **Experiment**: Read the JEPA architecture diagram and map each module (encoder, predictor, cost) to a concrete implementation choice.

### 17. Agents
- **Read**: 26 — SWE-bench
- **Prerequisites**: Stage 14
- **Key concepts**: tool use, long-horizon task execution, real-world evaluation
- **Gate check**: What makes SWE-bench harder than single-turn QA benchmarks?
- **Experiment**: Try an open-source coding agent on 2-3 SWE-bench Lite issues and read its trajectory logs.

### 18. Neuro-Symbolic AI
- **Read**: 23 — AlphaGeometry *(manual download)*, 24 — AlphaProof, 27 — AlphaEvolve, 25 — ARC-AGI
- **Prerequisites**: Stage 17
- **Key concepts**: symbolic search + neural guidance, synthetic data generation, formal verification
- **Gate check**: How do AlphaGeometry/AlphaProof combine a neural proposer with a symbolic checker?
- **Experiment**: Solve 2-3 ARC-AGI tasks by hand and note which priors (symmetry, counting, objectness) you used.

### 19. AI Safety
- **Read**: 28 — Alignment Faking, 29 — Artificial Hivemind, 30 — OWASP Top 10 for Agentic Applications
- **Prerequisites**: Stage 8
- **Key concepts**: deceptive alignment, RLHF-induced homogeneity, agentic attack surface
- **Gate check**: Name three OWASP agentic risk categories and one concrete mitigation for each.
- **Experiment**: Thread the OWASP Top 10 categories through a project you're building — which apply?

### 20. Frontier AI
- **Read**: 31 — When More Thinking Hurts, 32 — Claude Fable 5.1 System Card, 33 — GPT-6 Astra System Card
- **Prerequisites**: Stages 13, 14, 19
- **Key concepts**: overthinking/reasoning collapse, adaptive thinking effort, recurrent-depth reasoning, chain-of-thought monitorability
- **Gate check**: Compare how the two 2026 system cards each report on reasoning-trace monitorability — what's the shared concern?
- **Experiment**: Chart the test-time-compute lineage (15 → 16 → 31) and identify the specific failure mode each successive paper addresses or introduces.
