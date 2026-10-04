# Developer Cookbook — L_PRAISON
**Stack:** Python 3.11, praisonai 0.x, PAX 27B, AIOSS_FORMAT, api-oss-tools
**Domain:** PraisonAI: production-ready agentic AI framework with PAX 27B for Anticloud automation

## Define and run a PraisonAI workflow
```python
from l_praison import PraisonAnticloud

# Define tools PAX can call
tools = [
    {"name": "search_corpus", "description": "Search Anticloud corpus", "function": kamelot_index.search},
    {"name": "lookup_fact", "description": "Lookup fact in KANTOR_K5", "function": kantor_kb.lookup},
    {"name": "query_logs", "description": "Query api-oss-logging", "function": logger.query}
]

praison = PraisonAnticloud(
    pax_model="./pax-27b-q4.gguf",
    tools=tools,
    aioss_chain="./praison.aioss"
)

result = praison.run(
    task="Generate a complete compliance report for TIER_7 covering HIPAA and GDPR",
    max_steps=15
)
print(result.output)
print(f"Tool calls: {result.tool_call_count}")
print(f"Chain: {result.chain_hash}")
```

## YAML workflow definition
```yaml
# praison_workflow.yaml
task: "Audit TIER_8 RF projects for NIST compliance"
agents:
  - name: researcher
    role: "Research RF project specs"
    tools: [search_corpus, lookup_fact]
  - name: auditor
    role: "Evaluate NIST compliance"
    tools: [query_logs]
  - name: reporter
    role: "Generate compliance report"
```

```python
result = praison.run_from_yaml("./praison_workflow.yaml")
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
