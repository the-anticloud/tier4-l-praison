# Deploy Guide — L_PRAISON
**Tier:** TIER_4_INFERENCE_AGENTS | **Stack:** Python 3.11, praisonai 0.x, PAX 27B, AIOSS_FORMAT, api-oss-tools
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, praisonai 0.x, PAX 27B weights, Anticloud TIER_1/TIER_3 tools accessible.

## Environment
16GB RAM. GPU for PAX. All tool calls remain local — no external APIs.

## AIOSS Integration
```bash
aioss init --module L_PRAISON --output ./l_praison.aioss
aioss append --chain ./l_praison.aioss --payload ./output.bin --module L_PRAISON
aioss verify --chain ./l_praison.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="L_PRAISON",
    aioss_chain="./L_PRAISON.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./L_PRAISON.aioss --verbose
python -m L_PRAISON.tests.smoke
```
