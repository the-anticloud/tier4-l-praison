# HF_Leaderboard_Lab_Results

**Project:** `L_PRAISON`  
**Tier:** `TIER_4_INFERENCE_AGENTS`  
**Slug:** `MervinPraison/PraisonAI`  
**Commit:** `d9453cb8e33b`  
**Run:** `2026-09-30T15:07:07.146295+00:00`  

## Isolation Environment

| Field | Value |
| ----- | ----- |
| Platform | `win32` |
| Python | `3.12.10` |
| HF model | `distilbert-base-uncased` |
| HF load time | `4.42s` |
| Inference device | `cpu` |

## Results

**Framework:** [HuggingFace Open LLM Leaderboard (proxy via distilbert-base-uncased)](https://huggingface.co/docs/leaderboards/en/open_llm_leaderboard/archive)

**Model used:** `distilbert-base-uncased`

### Inference Latency (Classification)

| Metric | Value |
| ------ | ----- |
| Avg latency | **57.98 ms** |
| Min latency | 43.67 ms |
| Max latency | 93.01 ms |
| Samples | 5 |

### Real Tokenization Results

| Field | Value |
| ----- | ----- |
| Token count | **41** |
| Tokenization latency | 0.51 ms |
| Classification label | `LABEL_0` |
| Classification score | 0.5846 |
| Classification latency | 61.01 ms |
| Status | **PASS** |

**Input text tokenized:**
```
L_PRAISON (MervinPraison/PraisonAI) — 6715 files, 975404 source lines, licence MIT, primary language ['Python']
```

**First 20 tokens:**
```
['[CLS]', 'l', '_', 'pr', '##ais', '##on', '(', 'mer', '##vin', '##pr', '##ais', '##on', '/', 'pr', '##ais', '##ona', '##i', ')', '—', '67']
```

> Full MMLU/HellaSwag/TruthfulQA/ARC/Winogrande/GSM8K require dedicated GPU.
> These results are CPU inference proxy metrics using distilbert-base-uncased.

---
_Anticloud Benchmark Suite — isolation log — 2026-09-30T15:07:07.146295+00:00_