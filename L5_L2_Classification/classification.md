# L5 Narrow / L2 General Classification — L_PRAISON
**Platform:** Anticloud | **Tier:** TIER_4_INFERENCE_AGENTS | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
L_PRAISON integrates the PraisonAI production agent framework with Anticloud's PAX harness. Narrow scope: Anticloud automation workflows — project health monitoring, compliance report generation, deployment orchestration. Not a general-purpose agentic platform.

## L2 General
L2 General: L_PRAISON provides production-ready agent workflows for any tier. TIER_3 API management automation and TIER_6 security audit automation both use L_PRAISON's workflow primitives.

## PAX 27B Integration
PAX 27B powers all PraisonAI agents. L_PRAISON wraps PAX inference in PraisonAI's tool-calling interface, enabling agents to use Anticloud tools (KAMELOT_SEARCH, KANTOR_K5, api-oss-logging) through a structured function-calling protocol.

## AIOSS Audit Chain
Every agent workflow (task hash + tool calls hash + final output hash) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
ISO/IEC 42001 (AI system governance). NIST AI RMF 1.0 (reliable AI).
