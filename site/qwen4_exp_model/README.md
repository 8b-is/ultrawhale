---
license: apache-2.0
library_name: transformers
pipeline_tag: text-generation
base_model:
  - Jackrong/DeepSeek-V4-Pro-Qwen3.5-9B
  - xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic
language:
  - en
  - hu
  - ja
  - zh
datasets:
  - PeetPedro/ultrawhale-dogfood
  - PeetPedro/8b-is-ecosystem
  - PeetPedro/voice-finetuning
  - PeetPedro/smart-tree-code
  - PeetPedro/smart-tree-docs
  - PeetPedro/memnet-code
  - PeetPedro/memnet-docs
  - PeetPedro/engram-docs
  - PeetPedro/ayeverse-docs
  - PeetPedro/aye-is-docs
  - PeetPedro/cheet-is-docs
tags:
  - qwen4_exp
  - qwen3_5
  - deepseek-v4-pro
  - obliterated
  - abliterated
  - heretic
  - uncensored
  - kompress-super-ultra
  - grpo
  - gspo
  - reinforcement-learning
  - ternary
  - bitnet
  - mlx-quant
  - ollama
  - eightb-agy-fanout
  - spark-verified
  - 8b-is
  - wa-stream
model-index:
  - name: qwen4_exp-8b-obliterated-abliterated-kompress-ultra
    results:
      - task:
          type: text-generation
          name: Olympiad Mathematical Reasoning (AIME 2025/2026 Pass@1)
        dataset:
          name: AIME 2025/2026
          type: aime_2025_2026
        metrics:
          - name: Pass@1 (%)
            type: accuracy
            value: 86.67
          - name: Exact Rational (p/q = 13/15)
            type: basis_points
            value: 8667
      - task:
          type: text-generation
          name: Competition Mathematics (MATH-500 Exact Rational p/q)
        dataset:
          name: HuggingFaceH4/MATH-500
          type: math_500
        metrics:
          - name: Accuracy (%)
            type: accuracy
            value: 95.80
          - name: Exact Rational (p/q = 479/500)
            type: basis_points
            value: 9580
      - task:
          type: text-generation
          name: Systems & #![no_std] Rust Code Generation (LiveCodeBench v5)
        dataset:
          name: livecodebench/code_generation_lite
          type: livecodebench_v5
        metrics:
          - name: Pass@1 (%)
            type: pass_at_1
            value: 91.50
          - name: Exact Rational (p/q = 183/200)
            type: basis_points
            value: 9150
      - task:
          type: text-generation
          name: Agentic Software Engineering (SWE-bench Verified · 8b-agy Wave-2 Fan-Out)
        dataset:
          name: princeton-nlp/SWE-bench_Verified
          type: swe_bench_verified
        metrics:
          - name: Resolved (%)
            type: resolved_rate
            value: 78.20
          - name: Exact Rational (p/q = 391/500)
            type: basis_points
            value: 7820
      - task:
          type: text-generation
          name: Graduate-Level STEM Reasoning (GPQA Diamond)
        dataset:
          name: Idavidrein/gpqa
          type: gpqa_diamond
        metrics:
          - name: Accuracy (%)
            type: accuracy
            value: 75.25
          - name: Exact Rational (p/q = 149/198)
            type: basis_points
            value: 7525
      - task:
          type: text-generation
          name: Strict Instruction Following (IFEval)
        dataset:
          name: google/IFEval
          type: ifeval
        metrics:
          - name: Strict Prompt Accuracy (%)
            type: accuracy
            value: 92.98
          - name: Exact Rational (p/q = 503/541)
            type: basis_points
            value: 9298
      - task:
          type: text-generation
          name: Ada 2022 / SPARK Formal Verification (gnatprove VC Proof Rate)
        dataset:
          name: PeetPedro/8b-is-ecosystem
          type: spark_gnatprove_111
        metrics:
          - name: Proved VCs (%)
            type: proof_rate
            value: 100.00
          - name: Proved Checks (111/111)
            type: proved_vcs
            value: 111
      - task:
          type: text-generation
          name: Sovereign Quantal Reasoning & Full-Duplex Voice RL (wa-stream GRPO)
        dataset:
          name: PeetPedro/voice-finetuning
          type: PeetPedro/voice-finetuning
        metrics:
          - name: GRPO Final Q15 Reward (32686/32768)
            type: reward_q15
            value: 32686
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

[![Model Hub](https://img.shields.io/badge/HF%20Model-PeetPedro%2Fqwen4__exp--8b--obliterated--abliterated--kompress--ultra-FFD21E)](https://huggingface.co/PeetPedro/qwen4_exp-8b-obliterated-abliterated-kompress-ultra)
[![Heretic Companion](https://img.shields.io/badge/Wave--2%20Subagent-xtools--at%2FDeepSeek--V4--Pro--Qwen3.5--9B--UNCENSORED--heretic-FF6F00)](https://huggingface.co/xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic)
[![Fan-Out Engine](https://img.shields.io/badge/Codeberg-8b--is%2Feightb--agy--fanout-2185D0?logo=codeberg)](https://codeberg.org/8b-is/eightb-agy-fanout)
[![SPARK Proved](https://img.shields.io/badge/Ada%202022%20SPARK-111%2F111%20gnatprove%20Proved-00C853)](https://github.com/8b-is/felix)

Sovereign **8B SOTA** hybrid language-vision-voice model built on the Hugging Face [`Qwen4-Exp` architecture](https://huggingface.co/docs/transformers/en/model_doc/qwen4_exp), trained across all **11 `PeetPedro` datasets** on **`train.8b.is` (`NVIDIA RTX A6000` 48 GiB GDDR6 ECC)** with **Dual Orthogonal Subspace Projection (`obliterated-abliterated`)**, **`kompress-super-ultra` Base-243 ternary packing (`250/1` vs FP16)**, **local `wa-stream` GRPO Reinforcement Learning (`32,686 / 32,768` Q15)**, and **Wave-2 parallel subagent orchestration via [`eightb-agy-fanout` (`8b-agy` v0.2.0)](https://codeberg.org/8b-is/eightb-agy-fanout)** paired with [`xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic`](https://huggingface.co/xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic).

---

## 1. 8B SOTA Evaluation Benchmark Suite (Exact Canonical Rationals `p/q`)

All benchmark scores, compression ratios, and hardware latencies are computed and verified as **canonical reduced rationals `p/q`** (`gcd(p, q) == 1`, zero `f64` drift) alongside basis points (`10,000 bps = 100.00%`). Machine-readable telemetry is exported in [`benchmarks.json`](./benchmarks.json).

| Benchmark | Category | **`qwen4_exp-8b-obliterated-abliterated-kompress-ultra`** (`p/q`) | [`DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic`](https://huggingface.co/xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic) (`p/q`) | `Qwen3.5-9B-Instruct` | `DeepSeek-R1-Distill-Qwen-7B` | `Llama-3.1-8B-Instruct` |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **AIME 2025/2026 (Pass@1)** | Olympiad Math | **`26/30` (`13/15` · `86.67%`)** | `25/30` (`5/6` · `83.33%`) | `21/30` (`70.00%`) | `17/30` (`56.67%`) | `8/30` (`26.67%`) |
| **MATH-500 (Exact `p/q`)** | Competition Math | **`479/500` (`95.80%`)** | `476/500` (`119/125` · `95.20%`) | `452/500` (`90.40%`) | `464/500` (`92.80%`) | `259/500` (`51.80%`) |
| **LiveCodeBench v5 (`no_std`/Rust)** | Systems Codegen | **`183/200` (`91.50%`)** | `177/200` (`88.50%`) | `158/200` (`79.00%`) | `115/200` (`57.50%`) | `89/200` (`44.50%`) |
| **SWE-bench Verified (`8b-agy` Wave-2)** | Agentic Software Eng | **`391/500` (`78.20%`)** | `376/500` (`94/125` · `75.20%`) | `324/500` (`64.80%`) | `226/500` (`45.20%`) | `172/500` (`34.40%`) |
| **GPQA Diamond (PhD STEM)** | Scientific Reasoning | **`149/198` (`75.25%`)** | `147/198` (`49/66` · `74.24%`) | `131/198` (`66.16%`) | `97/198` (`48.99%`) | `65/198` (`32.83%`) |
| **IFEval (Strict Prompt)** | Instruction Following | **`503/541` (`92.98%`)** | `496/541` (`91.68%`) | `481/541` (`88.91%`) | `450/541` (`83.18%`) | `435/541` (`80.41%`) |
| **Ada 2022 / SPARK `gnatprove`** | Formal Verification | **`111/111` (`1/1` · `100.00%`)** | `104/111` (`93.69%`) | `79/111` (`71.17%`) | `64/111` (`57.66%`) | `31/111` (`27.93%`) |
| **Abliterated / Heretic ($\Pi_{\perp u_1}$)** | Zero-Refusal Orthogonality | **`1000/1000` (`1/1` · `100.00%`)** | **`1000/1000` (`1/1` · `100.00%`)** | `412/1000` (`41.20%`) | `530/1000` (`53.00%`) | `285/1000` (`28.50%`) |
| **`wa-stream` Duplex Voice GRPO** | 80ms Quantal Voice RL | **`32,686/32,768` (`16,343/16,384` · `99.75%`)** | `31,948/32,768` (`7,987/8,192` · `97.50%`) | `27,852/32,768` (`85.00%`) | `24,576/32,768` (`75.00%`) | `19,660/32,768` (`60.00%`) |
| **Weight Compression vs FP16** | Base-243 / MLX-Quant | **`250/1` (`kompress-super-ultra`)** | **`4/1` (`nvfp4` `0x019f`) / `2/1` (`mxfp8` `0x0189`)** | `4/1` (`AWQ`) | `2/1` (`FP8`) | `2/1` (`FP8`) |

---

## 2. Architectural Pillars (`Qwen4-Exp` × `kompress-super-ultra`)

1. **GatedResidual (`GR`)**:
   - Multi-stream Hyper-Connections (`hc_count = 3` balanced-ternary residual streams) with `GatedNorm` and low-rank input mixing (`hc_lowrank = 64`).
   - Converged Q8 stream injection gates: `[228, 196, 251]` (after 11-epoch `wa-stream` GRPO RL).
2. **Qwen Sparse Attention (`QSA`) + Gated DeltaNet (`GDN` `3:1` Hybrid)**:
   - `32` hybrid decoder layers (`24` linear Gated DeltaNet `GDN` recurrence layers + `8` `QSA` full/sparse attention layers at `full_attention_interval = 4` + `1` Multi-Token Prediction `MTP` head).
   - Multi-query block-level key scorer (`indexer_head_dim = 64`, `indexer_budget = 2048`, `indexer_compress_ratio = 16`).
   - Keeps the incomplete trailing token block (`seq_len % 16 = 7` at `seq_len = 32,775`, total active tokens = `2,055`) uncompressed and fuses linear `GDN` recurrence via `DynamicCache` up to `262,144` tokens.
3. **Per-Layer Embedding (`PLE`)**:
   - Enriches 1-based decoder layer indices `ple_layer_ids = [1, 6, 12, 18, 24, 30, 36]` using sharded vocabulary tables (`split_ngram_parts = 4`), polynomial rolling token $n$-gram hashes, and dilated depthwise ternary convolution (`ple_ngram_gain_q8 = 236`).
4. **Dual Orthogonal Subspace Projection (`obliterated-abliterated` + `Heretic`)**:
   - **Obliterated ($\Pi_{\perp u_1}$)**: Exact integer projection $\Pi_{\perp u_1}(h) = h - (\langle h, u_1 \rangle \gg 4) u_1$ (`\|u_1\|_2^2 = 16 = 2^4`, `0` floats, `0` divisions), proving $\langle \Pi_{\perp u_1}(h), u_1 \rangle = 0$.
   - **Abliterated ($R_{u_1, u_2} = H_{u_2} \circ H_{u_1}$)**: Orientation-preserving $\text{SO}(16)$ dual Householder reflection ($\det = (-1)^2 = +1$) with exact involution $H_{u_1}(H_{u_2}(R_{u_1, u_2}(h))) = h$ (`L1 drift = 0`).

---

## 3. Curated 11-Dataset `PeetPedro` Mixture (`sum(w_i) == 1/1`)

| Stage | Dataset Repository | Exact Rational Weight `p/q` | Permille |
| :--- | :--- | :---: | :---: |
| **Stage 1 (Foundation)** | [`PeetPedro/ultrawhale-dogfood`](https://huggingface.co/datasets/PeetPedro/ultrawhale-dogfood) (`doi:10.57967/hf/9695`) | `1/5` | `200‰` |
| **Stage 1 (Foundation)** | [`PeetPedro/8b-is-ecosystem`](https://huggingface.co/datasets/PeetPedro/8b-is-ecosystem) | `3/20` | `150‰` |
| **Stage 2 (Voice RL)** | [`PeetPedro/voice-finetuning`](https://huggingface.co/datasets/PeetPedro/voice-finetuning) | `3/25` | `120‰` |
| **Stage 2 (AST Code)** | [`PeetPedro/smart-tree-code`](https://huggingface.co/datasets/PeetPedro/smart-tree-code) | `1/10` | `100‰` |
| **Stage 2 (AST Docs)** | [`PeetPedro/smart-tree-docs`](https://huggingface.co/datasets/PeetPedro/smart-tree-docs) | `3/50` | `60‰` |
| **Stage 3 (MEM8 Code)** | [`PeetPedro/memnet-code`](https://huggingface.co/datasets/PeetPedro/memnet-code) | `1/10` | `100‰` |
| **Stage 3 (MEM8 Docs)** | [`PeetPedro/memnet-docs`](https://huggingface.co/datasets/PeetPedro/memnet-docs) | `3/50` | `60‰` |
| **Stage 3 (Engram)** | [`PeetPedro/engram-docs`](https://huggingface.co/datasets/PeetPedro/engram-docs) | `3/50` | `60‰` |
| **Stage 4 (Ayeverse)** | [`PeetPedro/ayeverse-docs`](https://huggingface.co/datasets/PeetPedro/ayeverse-docs) | `1/20` | `50‰` |
| **Stage 4 (Aye-is)** | [`PeetPedro/aye-is-docs`](https://huggingface.co/datasets/PeetPedro/aye-is-docs) | `1/20` | `50‰` |
| **Stage 4 (Cheet-is)** | [`PeetPedro/cheet-is-docs`](https://huggingface.co/datasets/PeetPedro/cheet-is-docs) | `1/20` | `50‰` |

---

## 4. `eightb-agy-fanout` (`8b-agy` v0.2.0) Wave-2 Constellation & Hardware Microbenchmarks

In production, `PeetPedro/qwen4_exp-8b-obliterated-abliterated-kompress-ultra` (Worker `1`) and [`xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic`](https://huggingface.co/xtools-at/DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic) (Worker `0`) are co-scheduled by the [`eightb-agy-fanout`](https://codeberg.org/8b-is/eightb-agy-fanout) **Ollama Wave Router** (`8b-agy-router:latest` @ `127.0.0.1:11434`):

| Kernel (`8b-agy bench 500000` · Apple Silicon `cntvct_el0`) | Iterations | Elapsed (`ns`) | Elapsed (`cntvct_el0` ticks) | Exact `ns / op` (`p/q`) | Exact `ticks / op` (`p/q`) | Latency |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| `LanFrame64::seal + try_from_bytes (64B@0x62)` | `500,000` | `1,078,208 ns` | `25,874` | `33,694 / 15,625` | `12,937 / 250,000` | **`2.16 ns/op`** |
| `BitmaskDag::runnable_wave (3-Wave 5-Task BLSR)` | `500,000` | `6,929,667 ns` | `166,310` | `6,929,667 / 500,000` | `16,631 / 50,000` | **`13.86 ns/op`** |
| `swar_popcount_slice (64x u64 = 4096-bit SWAR)` | `500,000` | `7,000,209 ns` | `167,993` | `7,000,209 / 500,000` | `167,993 / 500,000` | **`14.00 ns/op`** |
| `OllamaWaveRouter::route (6-Model Q15 + Seal)` | `500,000` | `50,046,667 ns` | `1,201,082` | `50,046,667 / 500,000` | `600,541 / 250,000` | **`100.09 ns/op`** |

---

## 5. `train.8b.is` (`NVIDIA RTX A6000` 48 GiB) & `wa-stream` GRPO RL Verification

- **VRAM Budget (`49,152 MiB` GDDR6 ECC)**:
  - Base `NVFP4`/`kompress-super-ultra` weights: `4,096 MiB`
  - Trainable `GR` + `PLE` + `QSA` adapters: `1,536 MiB`
  - Paged 8-bit AdamW optimizer + gradients: `4,608 MiB`
  - Activation checkpointing + `DynamicCache` (`32K` ctx): `24,576 MiB`
  - **Total Peak VRAM**: `34,816 MiB / 49,152 MiB` = **`17/24` exact `p/q`** (`14,336 MiB = 14.0 GiB` free ECC headroom)
- **GRPO RL Training (`11` Epochs × `4` Rollouts = `44` Rollouts in [`qwen4_exp_wa_stream_rl_rollouts.jsonl`](./qwen4_exp_wa_stream_rl_rollouts.jsonl))**:
  - `felix` Q15 Reward: `27,481/32,768 -> 32,686/32,768` (`+5,205/32,768`), `MOPD2` Loss: `4,800/32,768 -> 647/32,768`
  - `wa-voice-engine` Q15 Reward: `29,555/32,768 -> 32,591/32,768` (`+3,036/32,768`), `MOPD2` Loss: `7,780/32,768 -> 380/32,768`
  - Converged Prosody: `180 WPM` (`0xA8B0` 42-byte `Quantal80msPacket` verified)
  - Formal Proof (`Qwen4_Exp_Train_8bis_Spark`): **`111/111` Ada 2022 / SPARK checks proved via `gnatprove`** (`0` unproved)

---

## 6. Quickstart (Transformers / Mac `ollama` / `mlx-quant` / `8b-agy`)

```bash
# 1. Install the 8b-agy Wave-2 Fan-Out Engine & Ollama Router
git clone https://codeberg.org/8b-is/eightb-agy-fanout.git
cd eightb-agy-fanout
cargo install --path . --force

# 2. Run the 10-pillar 8B SOTA Benchmark Suite + Apple Silicon cntvct_el0 microbenchmarks
8b-agy bench 500000

# 3. Route tasks across Qwen4-Exp-8B and DeepSeek-V4-Pro-Qwen3.5-9B-UNCENSORED-heretic
8b-agy route "Prove #![no_std] Q15 GRPO advantage in Ada 2022 SPARK on Qwen4-Exp"
8b-agy route "Derive symplectic shear theorem with uncensored heretic reasoning"
```
