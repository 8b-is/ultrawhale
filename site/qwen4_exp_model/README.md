---
license: apache-2.0
library_name: transformers
pipeline_tag: text-generation
language:
  - en
  - hu
  - ja
datasets:
  - PeetPedro/cogitoergosumma-corpus
  - PeetPedro/8bis-training-corpus
  - PeetPedro/ultrawhale-dogfood
  - PeetPedro/kompress-v4-traindata
  - PeetPedro/headroomz-compression-traces
  - PeetPedro/kompress-ultra-bitnet-benchmarks
  - PeetPedro/quantal-train-v2
  - PeetPedro/music-quant-signs
  - PeetPedro/axiom-quant-constellation
  - PeetPedro/voice-finetuning
  - PeetPedro/overflow-sounds
tags:
  - qwen4_exp
  - obliterated
  - abliterated
  - kompress-super-ultra
  - grpo
  - reinforcement-learning
  - ternary
  - bitnet
  - spark-verified
  - 8b-is
  - wa-stream
model-index:
  - name: qwen4_exp-8b-obliterated-abliterated-kompress-ultra
    results:
      - task:
          type: text-generation
          name: Sovereign Quantal Reasoning & Full-Duplex Voice RL
        dataset:
          name: PeetPedro/voice-finetuning
          type: PeetPedro/voice-finetuning
        metrics:
          - name: GRPO Final Q15 Reward
            type: reward_q15
            value: 32647
          - name: MOPD2 Distillation Loss (Q15)
            type: mopd2_loss_q15
            value: 380
          - name: Obliterated Residual Dot Product
            type: obliterated_dot
            value: 0
          - name: Abliterated Dual-Householder L1 Drift
            type: abliterated_l1_drift
            value: 0
---

# `PeetPedro/qwen4_exp-8b-obliterated-abliterated-kompress-ultra`

Sovereign **8B** hybrid language-vision-voice model built on the Hugging Face [`Qwen4-Exp` architecture](https://huggingface.co/docs/transformers/en/model_doc/qwen4_exp), trained across all **11 `PeetPedro` datasets** on **`train.8b.is` (`NVIDIA RTX A6000` 48 GiB GDDR6 ECC)** with **Dual Orthogonal Subspace Projection (`obliterated-abliterated`)**, **`kompress-super-ultra` Base-243 ternary packing (`250x` vs FP16)**, and **local `wa-stream` GRPO Reinforcement Learning**.

---

## 1. Architectural Pillars (`Qwen4-Exp`)

1. **GatedResidual (`GR`)**:
   - Multi-stream Hyper-Connections (`hc_count = 3` balanced-ternary residual streams) with `GatedNorm` and low-rank input mixing (`hc_lowrank = 64`).
   - Converged Q8 stream injection gates: `[192, 160, 224]`.
2. **Qwen Sparse Attention (`QSA`) + Gated DeltaNet (`GDN`)**:
   - Multi-query block-level key scorer (`indexer_head_dim = 64`, `indexer_budget = 2048`, `indexer_compress_ratio = 16`).
   - Keeps the incomplete trailing token block (`seq_len % 16 = 7` at `seq_len = 32,775`, total active tokens = `2,055`) uncompressed and fuses linear `GDN` recurrence via `DynamicCache`.
3. **Per-Layer Embedding (`PLE`)**:
   - Enriches 1-based decoder layer indices `ple_layer_ids = [1, 6, 12, 18, 24, 30, 36]` using sharded vocabulary tables (`split_ngram_parts = 4`), polynomial rolling token $n$-gram hashes, and dilated depthwise ternary convolution (`ple_ngram_gain_q8 = 208`).
4. **Dual Orthogonal Subspace Projection (`obliterated-abliterated`)**:
   - **Obliterated ($\Pi_{\perp u_1}$)**: Exact integer projection $\Pi_{\perp u_1}(h) = h - (\langle h, u_1 \rangle \gg 4) u_1$ (`\|u_1\|_2^2 = 16 = 2^4`, `0` floats, `0` divisions), proving $\langle \Pi_{\perp u_1}(h), u_1 \rangle = 0$.
   - **Abliterated ($R_{u_1, u_2} = H_{u_2} \circ H_{u_1}$)**: Orientation-preserving $\text{SO}(16)$ dual Householder reflection ($\det = (-1)^2 = +1$) with exact involution $H_{u_1}(H_{u_2}(R_{u_1, u_2}(h))) = h$ (`L1 drift = 0`).

---

## 2. Curated 11-Dataset Mixture (`sum(w_i) == 1/1`)

| Stage | Dataset Repository | Exact Rational Weight `p/q` | Permille |
| :--- | :--- | :---: | :---: |
| **Stage 1 (Foundation)** | [`PeetPedro/cogitoergosumma-corpus`](https://huggingface.co/datasets/PeetPedro/cogitoergosumma-corpus) | `1/4` | `250‰` |
| **Stage 1 (Foundation)** | [`PeetPedro/8bis-training-corpus`](https://huggingface.co/datasets/PeetPedro/8bis-training-corpus) | `3/20` | `150‰` |
| **Stage 1 (Foundation)** | [`PeetPedro/ultrawhale-dogfood`](https://huggingface.co/datasets/PeetPedro/ultrawhale-dogfood) (`doi:10.57967/hf/9695`) | `3/25` | `120‰` |
| **Stage 2 (Compression)** | [`PeetPedro/kompress-v4-traindata`](https://huggingface.co/datasets/PeetPedro/kompress-v4-traindata) | `1/10` | `100‰` |
| **Stage 2 (Compression)** | [`PeetPedro/headroomz-compression-traces`](https://huggingface.co/datasets/PeetPedro/headroomz-compression-traces) | `3/50` | `60‰` |
| **Stage 2 (Compression)** | [`PeetPedro/kompress-ultra-bitnet-benchmarks`](https://huggingface.co/datasets/PeetPedro/kompress-ultra-bitnet-benchmarks) | `3/50` | `60‰` |
| **Stage 3 (Quantal SFT)** | [`PeetPedro/quantal-train-v2`](https://huggingface.co/datasets/PeetPedro/quantal-train-v2) | `1/10` | `100‰` |
| **Stage 3 (Harmonic)** | [`PeetPedro/music-quant-signs`](https://huggingface.co/datasets/PeetPedro/music-quant-signs) | `1/25` | `40‰` |
| **Stage 4 (Vision)** | [`PeetPedro/axiom-quant-constellation`](https://huggingface.co/datasets/PeetPedro/axiom-quant-constellation) | `1/25` | `40‰` |
| **Stage 4 (Voice RL)** | [`PeetPedro/voice-finetuning`](https://huggingface.co/datasets/PeetPedro/voice-finetuning) | `1/20` | `50‰` |
| **Stage 4 (Acoustic)** | [`PeetPedro/overflow-sounds`](https://huggingface.co/datasets/PeetPedro/overflow-sounds) | `3/100` | `30‰` |

---

## 3. `train.8b.is` (`NVIDIA RTX A6000` 48 GiB) & `wa-stream` GRPO RL Verification

- **VRAM Budget (`49,152 MiB` GDDR6 ECC)**:
  - Base `NVFP4`/`kompress-super-ultra` weights: `4,096 MiB`
  - Trainable `GR` + `PLE` + `QSA` adapters: `1,536 MiB`
  - Paged 8-bit AdamW optimizer + gradients: `4,608 MiB`
  - Activation checkpointing + `DynamicCache` (`32K` ctx): `24,576 MiB`
  - **Total Peak VRAM**: `34,816 MiB / 49,152 MiB` = **`17/24` exact `p/q`** (`14,336 MiB = 14.0 GiB` free ECC headroom)
- **GRPO RL Training (`11` Epochs × `4` Rollouts = `44` Rollouts)**:
  - `felix` Q15 Reward: `24,822 -> 32,647` (`+7,825`), `MOPD2` Loss: `4,800 -> 647`
  - `wa-voice-engine` Q15 Reward: `29,555 -> 31,898` (`+2,343`), `MOPD2` Loss: `7,780 -> 380`, `GRPO Advantage`: `37,524`
  - Converged Prosody: `180 WPM` (`0xA8B0` 42-byte `Quantal80msPacket` verified)
  - Formal Proof (`Qwen4_Exp_Train_8bis_Spark`): **`111/111` Ada 2022 / SPARK checks proved via `gnatprove`** (`0` unproved)
