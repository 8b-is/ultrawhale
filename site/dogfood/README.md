---
license: mit
task_categories:
  - text-generation
  - question-answering
language:
  - en
tags:
  - ultrawhale
  - vaked
  - fine-tuning
  - alignment-research
  - dogfeed
  - telemetry
  - open-dataset
  - multi-model
  - agentic
  - structural-honesty
  - free-models
pretty_name: "ultrawhale-dogfood — the open vaked dogfeed dataset · the honest feed"
size_categories:
  - n<1K
configs:
  - config_name: dogfeed
    data_files: "dogfeed-*.jsonl"
    default: true
    description: "Human↔LLM interaction pairs from the ultrawhale M3 dogfeed loop"
  - config_name: telemetry
    data_files: "telemetry-consolidated.jsonl"
    description: "Anon structural metadata from Vaked sites (no content, no PII)"
---

# see https://huggingface.co/datasets/PeetPedro/ultrawhale-dogfood for full dataset card
# Auto-synced by hf-publish.yml CI

# the honest feed — human↔LLM pairs that trained the sovereign quant.
# structural honesty, from love, from within. prove it, don't assert it.
