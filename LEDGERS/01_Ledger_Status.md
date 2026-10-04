# Ledger Status

**Project:** `L_PRAISON`  
**Tier:** TIER_4_INFERENCE_AGENTS  
**Identity:** Upstream `MervinPraison/PraisonAI` @ `d9453cb8e33b` (MIT)

## Chain state

| Fact | Value |
| --- | --- |
| Upstream | `MervinPraison/PraisonAI` |
| Commit | `d9453cb8e33b40665a3693c1a6ed807adacf24e3` |
| Upstream licence | MIT |
| Licence class | permissive |
| Clone size | 91.35 MB |
| Ledger | 0 blocks, chain verified |
| Current TRL | NOT YET MEASURED |
| Post-optimisation TRL | NOT YET MEASURED |
| II budget cap | 1000.0 IIU |
| Verified upstream edits | 1 |

- Blocks: **0**
- Head digest: `None`
- Chain verification: **verified**

## Independent verification

The chain is verifiable without trusting this project's tooling:

```
anticloud ledger verify
anticloud ledger export > ledger.jsonl
```

Each block carries the previous block's digest, so removing or reordering an
entry invalidates every block after it. That property is the reason the
ledger can stand in for a claim of what happened.
